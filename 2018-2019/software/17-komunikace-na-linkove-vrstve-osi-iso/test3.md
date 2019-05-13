
### 5. ISO/OSI

#### 5.1 Referenční model

1. aplikační vrstva (FTP, SFTP, SSH, HTTP, HTTPS, DNS, DHCP, POP, IMAP, Telnet atd.) -> **aplikační data**
2. prezentační vrstva (upravení dat do podoby, kterou program vyžaduje - šifrování, serializace XML, JSON atd.)
3. relační vrstva (navazování, udržování a zavírání spojení; protokoly L2TP, SOCKS - websockety)
4. transportní vrstva (TCP, UDP) -> **čísla portů, TCP/UDP segment**
5. síťová vrstva (protokoly IP, IPSec, ARP, ICMP atd.) -> **IP adresy, paket**
6. linková vrstva (bridge, switch) -> **MAC adresy, datagram**
7. fyzická vrstva (fyzická kabeláž, přenos dat, signál atd.) -> **frame**

#### 5.2 Protokoly
- protokol - pravidla pro elektronickou komunikaci
- handshake - automatický proces vyjednávání
- síťová vrstva
    - datagramy putují sítí nezávisle na sobě
    - pořadí doručení **nemusí** odpovídat pořadí ve zprávě
    - bezpečné doručení datagramu není zaručeno (zajišťuje až **transportní vrstva**)
    - protokol IPv4 a IPv6 - adresace pomocí IP adres
    - protokol ARP (Address Resolution Protocol)
        - **přiřadí IP adresu k MAC adrese**
        - ARP dotaz nepřekročí hranice dané podsítě
    - protokol RARP (Reverse Address Resolution Protocol)
        - opačná funkce ARP (**přiřadí MAC adresu k IP adrese**)
        - využívá např. DHCP
        - RARP server obsahuje databázi MAC adres
    - protokol ICMP (Internet Control Message Protocol)
        - potřebný počítač nebo router je/není dostupný
        - `ping` - Echo Request / Echo Reply
        - `traceroute`
- transportní vrstva
    - protokol TCP (Transmision Control Protocol)
        - spojovaná služba
        - naváže spojení
        - vytvoří virtuální okruh na dobu spojení
        - okruh je plně duplexní
        - čísluje přenášené datagramy
        - znovu vyžádá ztracená/poškozená data
        - kontroluje integritu pomocí kontrolního součtu
        - přenos je **orientován na spolehlivost**
    - protokol UDP (User Datagram Protocol)
        - bez záruky na přenos dat
        - bez záruky, na pořadí doručených datagramů, že se nedoručí vícekrát, že se netratí atd.
        - vhodný na streamy dat, kde server nevyžaduje odpověď
    - RUDP (něco mezi TCP a UDP)
- aplikační vrstva
    - určeny přímo pro aplikace, říkají co s daty dělat
    - identifikovány číslem (**portem** - 0 až 65535)
        - nejběžnější služby 0 až 1023
        - registrované porty u ICANN 1024 až 49151
        - dynamické a soukromé porty 49152 až 65535 (nejsou pevně přiděleny!)
    - cílová stanice přesně adresována
        - IP adresou
        - protokolem transportní vrstvy (TCP nebo UDP)
        - portem
    - protokol FTP (File Transfer Protocol), porty 20 (pro řízení) a 21 (pro data) nezabezpečná
    - protokol SFTP (SSH File Transfer Protocol), port 115
    - protokol Telnet, ovládání vzdáleného počítače přes příkazovou řádku, port 23
    - protokol SSH, port 22
    - protokol SMTP (port 25), POP3 (port 110), IMAP4 (port 143)
    - protokol HTTP, port 80
    - protokol HTTPS, port 443
    - protokol NTP (Network Time Protocol), port 123
    - protokol DHCP, server port 68, klient port 67
    - protokol DNS, port 53
    
#### 5.3 IPv4
Internet protocol verze 4

- 32 bitové adresy
- binárně (`10000000.00001010.00000000.00000001`)
- decimálně 4 byte (128.10.0.1)
- každý byte se nazývá „okten“ / „oktet“ (z leva)
- 192.168.10.**0** - adresa sítě
- 192.168.10.**133** - adresa uzlu
- veřejné IP adresy
    - viditelné z WANu
    - celkem 2^32 (cca 4 294 967 296)
    - **docházejí**
- privátní IP adresy
    - nejsou viditelné z WANu
    - mohou se v různých LAN sítích opakovat 
    - řeší nedostatek IPv4
    - třídy
        - A: **10.0.0.0 – 10.255.255.255** (počet adres 16 777 216)
        - B: **172.16.0.0 – 172.31.255.255** (počet adres 1 048 576)
        - C: **192.168.0.0 – 192.168.255.255** (počet adres 65 536)

#### 5.4 IPv6
Internet protocol verze 6

- 128 bitové adresy
- osm 16-ti bitových polí
- `FEA1:122B:0000:0000:0000:0000:4A51:1022 = FEA1:122B::4A51:1022`
- není zatím nasazen jako standard

#### 5.5 Návrh LAN sítí
- = podsíť / subnet / subnetwork
- význam subnetu - **uzly mohou vzájemně komunikovat bez potřeby chodit přes bránu (gateway)!**
- routování - přechod mezi subnety
- maska
    - pro třídu A - 255.0.0.0 (je volný 2, 3 a 4. okten)
    - pro třídu B - 255.255.0.0 (je volný 3 a 4. okten)
    - pro třídu C - 255.255.255.0 (je volný pouze 4. okten)
- prefix (zjednodušený zápis masky)
    - maska (binárně) - `11111111. 11111111. 11111111.00000000`
    - počet jedniček - 24
    - tj. zápis např `198.114.67.0/24`
- neplatné masky např. `11111111.11111111.11110111.11000000` tj. **počet zařízení vždy sudý!**
- význam omezení 4. oktetu - bezpečnost (omezení počtu zařízení)
    - jakmile je IP adresa jednou využita, nelze ji využít jinde


Výpočet počtu zařízení podle prefixu
- 2^n - 2 (báze a broadcast)
- n = počet nul v masce
- příklad
    - `prefix /27` je 27 jedniček (tj. 32 bitů - 27 jedniček je 5 nul)
    - 2^5 je 32
    - 32 - 2 je **30 zařízení**

Příklad (50 zařízení, třída A)
1. nejbližší vyšší počet 50 je 64
2. maska 256 - 64 je 192 tj. 255.255.255.192
3. prefix pro 64 je `/26`
    - je potřeba odvodit
    - 256 ... `/24`
    - 128 ... `/25`
    - 64 ... `/26`
4. báze - třída A je **10.0.0.0 – 10.255.255.255**, takže vybereme například 10.0.100.0 (**musí končit nulou**) 
5. broadcast (poslední adresa v subnetu) 10.0.100.63
6. počet volných adres je 64 - 2 (báze a broadcast) **takže 62**

#### 6. HUB (rozbočovač)
již se nevyrábí!

- aktivní prvek počítačové sítě (chová se tak **zároveň jako repeater - opakovač**)
- **pracuje na fyzické vrstvě (layer L1)**
- data z portu posílají na všechny ostatní porty - všechna zařízení vidí všechna síťová data, zbytečné přetěžování sítě atd.

### 7. Switch (přepínač)

- **pracuje na linkové vrstvě (layer L2)**
- obsahuje CAM tabulku (Content Addressable Memory) - ke každému portu má přiřazenou MAC adresu
- princip
    1. přijde-li frame, přečtě zdrojovou MAC adresu
    2. v tabulce vytvoří záznam portu a MAC adresy
    3. podívá se na cílovou MAC adresu
    4. podívá se do tabulky CAM; pokud najde, odešle na daný port
    5. pokud nenajde, ale je propojení s dalším switchem - pošle jemu
    6. pokud nenajde a není propojen - pošle na broadcast (v L2 je to FF:FF:FF:FF)
- narozdíl od HUBu méně zatežuje síť, je bezpečnější
- lze zaútočit MAC floodingem - dojde k zaplavení MAC adresami a switch se pak začně chovat jako HUB
- metody přeposílání framů
    - Cut-through - pošle tak jak přijde (bez kontroly chyb)
    - Store-and-forward - přijme celý rámec, uloží do bufferu, ověří se kontrolní součet (případně zahodí)
- switch nijak nemění procházející data, nedochází k adresaci atd., může data pouze kontrolovat
- **některé switche pracují i na síťové vrstvě (layer L3)**

#### 7.1 Propojování switchů

Pomocí Up-Link (speciální port s vyšší propustností), nouzově pomocí normálního portu (nevhodné - vyšší nároky na průchodnost dat)

1. uplink - bude akorát více záznamů v CAM tabulce pro daný port
    - ideální zapojení do stromu
2. agregace **musí podporvat switch**
    - sváže několik portů do jednoho logického (*port trunk group*)
    - teoreticky vyšší přenosová rychlost a také bezpečnost (přerušení jednoho kabelu)
3. redundance **musí podporvat switch**
    - pokud přestane fungovat celý switch = výpadek velké části sítě (ve stromové struktuře)
    - nadbytečně propojíme switche mezi sebou
    - změna topologie ze stromu na strom+kruh
    - **nebezpečí smyček**
        - k cíli již neexistuje jedna cesta, ale několik
        - **pokud switch neumí redudanci - data budou pro jednoho hosta vyslána více porty**
        - vznikne nekonečná smyčka, zacyklení a z toho broadcastová bouře (znemožní chod celé sítě)
        - proto nastavit, že při normálním chodu, se redudantní spojení nevyužívá!
        - řesí SPT (Spanning Tree Protocol)
        - nepovolí přenos smyčkami pokud existuje nejkratší cesta
        
#### 7.2 Protokol SPT

- Spanning-tree algoritmus - vytvoření logické topologie bez smyček
- STP ustanoví kořenový uzel - root bridge – jeden switch
- vytvoří topologii s jednou nejkratší cestou ke každému uzlu
- označí port jako designated port – bude přeposílat frame (forward)
- záložní port jako non-designated port 
- redundandní spoje (non-designated port) jsou blokovány blocking state
- selže-li nejkratší spojení
    - vytvoří se nová topologie s novou nejkratší
    - redundandní spoj je povýšen na nejkratší cestu

Stavy portů (každý port jeden z pěti stavů)
1. blocking state - dočasně blokováno
2. listening state - poslouchání
3. learning state - učení
4. forwarding state - přeposílání
5. disabled state - vypnutí

Funkce portů
1. root port - pouze jeden, nejkratší cesta
2. disabled port - vypnutý, nebude použit jako záložní (např. koncové stanice)
3. designated port - port na kterých je povoleno přenášet data mezi switchi, v každém segmentu - pouze jeden port, všechny zbývající jsou jako záložní
4. non-designated port - alternativní (redundantní spoje)

### 8. Routery (směrovače, brány)

- **pracuje na síťové vrstvě (layer L3)**
- přenos dat na základě IP adres
- propojuje minimálně 2 podsítě (alespoň 2 síťové karty)
- rozhodují do jaké sítě bude paket poslát a kudy
- **brána (gateway) - adresa nejbližšího routeru (cesty do další sítě)**
- port WAN - cesta do jiné sítě
- PID (Process Identifier) - identifikátor každého procesu, komu jaký požadavek patří
- **záměna adres a pidů se nazývá NAT (Network Address Translation)**
- masquarade (síťový maškaráda), druh NATu (**dynamický NAT**)
    - z vnitřní sítě přijde IP datagram s cílem v jiné LAN
    - cílová adresa zůstává, zdrojová se změní za adresu routeru (brány) ve vnější LAN
    - to samé se děje při dalším HOPu
- informace uloženy ve směrovací tabulce
- IPv6 už NAT nepotřebuje
- pasivní vliv na bezpečnost sítě, není ale firewall!!!
     - zvenčí nelze zjistit topologii sítě, ani se připojit na zařízení
 - **statický NAT** - údaje se do směrovací tabulky zadávají ručně, při změně topologie nutno ručně přenastavit
 - **dynamický NAT** - sám zjišťuje nejlepší cesty v síti
 - směrovací protokol RIP (Routing Information Protocol)
     - určování nejkratší cesty v síti podle počtu HOPů (HOP count), maximální počet 15
     - více hopů EIGRP

#### 9. VLAN

- logické členění sítě bez ohledu na fyzickou strukturu
- **trunk port - port pro více LAN**
- switch musí umět pracovat na vrstvě L3
- switch v L3 neumí routovat pomocí IP adres, ale bude routovat pomocí MAC adres
- metody zařazení počítače do VLAN
    - podle portu (podle portu na kterém je), nejpoužívanější a nejrychlejší řešení
    - podle MAC adresy (dynamické zařazení), např. v kombinaci s RADIUS serverem
    - podle protokolu IPv4
    - podle autentizace - RADIUS server
    
#### 10. QoS

- Quality of Service
- datový tok (lze vyjádřit v kbit/s, Mbit/s atd.)
- přenosová kapacita - schopnost přenést množství dat za jednotku času
- šířka přenosového pásma (minimální/maximální přenos dat pro počítač v LAN) - nastavujeme!
- hrozí vyčerpání přenosové kapacity sítě (jeden PC zabere neúměrně datový tok), ostatní čekají ve frontě
- pomoci QoS lze nastavit priority, pravidla
- většinou nastavujeme v routeru
- lze nastavit podle
    - IP adresy
    - služby
    - atd.
- tradičně využívá provider - tzv. agregace (např. 100 mbit linka se rozdělí mezi 5 klientů, agregace 5)
    - ne každý klient využije plnou přenosovou kapacitu v jeden moment
    
#### 11. VPN

- Virtual Private Network
- připojení firemních PC odkudkoliv z internetu do firemní LAN sítě
- jako by bylo „součástí vnitřní LAN“
- připojení je zabezpečeno
- VPN server / VPN klient
- VPN server ověřuje správnost přístupu (login/heslo)
- protokoly
    - IPsec VPN
    - SSL VPN (využívá buď SSL, HTTPS nebo TLS)
    - Secure Socket Tunneling Protocol
    
#### 12. Diagnostika sítě

- v cmd příkazy ipconfig -all zobrazí veškeré informace o aktuální síti
- příkaz ping ověří, že "vidí" zařízení na dané IP adrese

LEDky síťové karty blikají

- ovladač OS, propojení plné funkční
- zkontrolujeme nastavení sítě
  - IP adresa (neplatná IP/maska/DNS)

LEDky síťové karty stále svítí

- poškozený/nevhodný TP kabel
- ovladač-driver karty korektně nefunguje
- zkontrolujeme
  - změna kabelu
  - funkčnost karty
  - ping 127.0.0.1
    - není li typ v pořádku
      - závada ovladače síťové karty
      - aktualizovat ovladače karty
      - přeinstalovat ovladače

Síťová karta

- ipconfig /all
- PC v subnetu ping, arp
- brána routeru: ping
- pc mimo náš subnet: ping tracert
  - zjistíme, kde se nám ping zastaví
  - "násobný ping" na další a další brány
