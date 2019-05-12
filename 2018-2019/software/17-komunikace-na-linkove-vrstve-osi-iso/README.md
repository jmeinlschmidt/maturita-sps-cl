# 17/25 - Komunikace na linkové vrstvě OSI/ISO - aktivní prvky
## Zadání
-	Komunikace na linkové vrstvě OSI/ISO
- Aktivní prvky
- Společná norma znalostí pro všechny okruhy
    - Kabeláž – typy, kategorie, normy, zapojení
    - WiFi:
        - 802.11 - 2,4/5GHz – kanály
        - Half/Full duplex, CSMA/CA - kolize
        - antény
        - módy WiFi přenosů
        - šifrování
    - ISO/OSI – rozdělení/ protokoly
        - IPv4/IPv6
        - návrh LAN sítí (!!!!!!)
    - Switche: - VŠE!!!
    - Routery: - VŠE!!!
    - Nastavení a zabezpečení WiFi routerů: - VŠE!!!
    - VPN, VLAN, QoS
    - Bezpečnost WiFi přenosů – VŠE!!!

## Vypracováno

### 1. Úvod
- počítačová síť - způsob propojení počítačů (workstations)
- topologie sítí - způsob propojení uzlů (nodes)
- typy počítačových sítí podle rozlohy
    - PAN (Personal Area Network) - nejmenší počítačová síť, bluetooth, řádově jednotky metrů
    - LAN (Local Area Network) - uavřená síť v rámci organizace
    - MAN (Metropolitan Area Network) - město a okolí (cca do 160 km)
    - WAN (Wide Area Network) - síť největšího rozsahu, internet
- topologie sítí - druhy zapojení
    - kruh (ring)
    - hvězda (star)
    - strom (tree)
    - mesh
    - úplná síť (propojený každý uzel s každým)
    - páteřní síť (backbone) - mezi kontinenty, wan
- aktivní prvky (obecně) - zesilují, zpracovávají, vyhodnocují signál
    - hub
    - switch
    - router
    - repeater
    - bridge
    - access point
    - poe
- síťová karta - jedinečná MAC adresa (Media Access Control) - linková vrstva
      
### 2. Přenos signálu
- vodič
    - elektrické vodiče
        - kroucená dvojlinka (anglicky Twisted Pair - **TP**) - UTP, STP, SFTP atd.
        - koaxiální kabel
    - optické vodiče (využívá se určité pásmo, např. 1260-1650 nm, každé pásmo jiný útlum, vzdálenost útlum atd., lze mít více pásem v jednom vodiči - potřeba použít rozbočovač)
        - jednovidové (anglicky Single Mode - **SM**) - delší vzdálenosti
        - vícevidové (anglicky Multi Mode - **MM**) - kratší vzdálenosti
        - **není rušení el. mag. polem! - je to světlo**
- signál

### 3. Kabeláž

Kroucená dvojlinka - TP (twisted pair).

Důvod kroucení - vzájemné vyrušení el. mag pole, snížení přeslechů.

```
Mb/s  Mbps (per second) Gb/s Gbps
GB/s  = 8 x Gb/s.
```

#### 3.1 Rozdělení
- typ vodiče
    - drát (jeden kus mědi, nelze ohýbat příliš často, láme se)
    - licna (hodně malých drátků - lepší pro propojení, lze ohýbat, namáhat, neláme se, ale větší útlum - jen na menší vzdálenosti)
- použití
    - venkovní (ochrana proti UV, odolnější plášť, vyztužené - umožňuje zavěšení)
    - vnitřní
- stínění
    - U/UTP (anglicky Unshielded Twisted Pair) - nestíněné
    - U/FTP (anglicky Foiled Twisted Pair) - fólie okolo každého páru
    - F/UTP - fólií okolo celého kabelu
    - S/UTP - pletení okolo celého kabelu
    - SF/UTP - fólie a opletení okolo celého kabelu
    - F/FTP - fólie okolo celého kabelu a fólie kolem každého páru
    - S/FTP - opletení okolo celého kabelu a fólie kolem každého páru
    - SF/FTP - fólie a opletení okolo celého kabelu a fólie kolem každého páru
    
#### 3.2 Kategorie
- CAT 1 (telefonní linky, max 100 kHz)  (třída A)
- CAT 2 (digitální přenos zvuku, max 1 MHz)  (třída B)
- CAT 3  (třída C)
    - až 16 MHz
    - převážně v 90. letech pro telefonní linku, lze se s ní setkat dodnes
    - 10BASE-T
    - 100BASE-T4 při využití 4 párů
    - standardně UTP
    - **TIA/EIA-568-B**
- CAT 4 (velmi rychle nahrazena CAT 5, často se ani neuvádí)
    - až 20 MHz
    - 10BASE-T
    - 100BASE-T4 při využití 4 párů
    - standardně UTP
- CAT 5
    - až 100 MHz
    - 10BASE-T and 100BASE-TX při využití dvou párů (díky tomu lze teoreticky udělat 2x100BASE-TX); každý pár pro jeden směr - full duplex (max 100 m)
    - 1000BASE-T při využití 4 párů (vzdálenost není definována)
    - využívá se 8P8C konektor (RJ45)
    - standardně UTP
    - **TIA/EIA-568-B**
- CAT 5e (třída D)
    - zhruba stejné parametry jako CAT 5
    - vyšší nároky na výrobu, nižší impedance, menší přeslechy atd. => větší šance, že se povede dosáhnout 1000BASE-T
    - využívá se 8P8C konektor (RJ45)
    - standardně UTP nebo STP
    - **TIA/EIA-568-B**
- CAT 6 (třída E)
    - až 250 MHz
    - 10/100/1000BASE-T do 100 m
    - 10GBASE-T do 55 m
    - využívá se 8P8C konektor (RJ45)
    - standardně UTP nebo STP
    - **ISO/IEC 11801 2nd Ed. (2002), ANSI/TIA 568-B.2-1**
    - *nejčastěji instalovaný kabel ve Finsku*
- CAT 6a (třída Ea)
    - až 500 MHz
    - vznik 2009
    - 10/100/1000/10GBASE-T do 100 m
    - menší útlum než CAT 6, tj. zvládne to samé, ale na delší vzdálenost
    - využívá se 8P8C konektor (RJ45)
    - standardně UTP, F/UTP nebo U/FTP
    - **ISO/IEC 11801 2nd Ed. Am. 2. (2008), ANSI/TIA-568-C.1 (2009)**
- CAT 7 (třída F)
    - až 600 MHz (při využití konektorů GG45, ARJ45, nebo TERA)
    - vznik 2002
    - 10/100/1000/10GBASE-T do 100 m
    - GG45, ARJ45, nebo TERA konektory využivá velmi málo hardwaru (specializovaný hardware, vysoká cena)
    - kompatibilní s 8P8C konektorem (RJ45), ale nedochází k využití maximální frekvence; vzhledem k tomu je cenově výhodnější využít CAT 6a (pokud není potřeba extra stínění)
    - standardně S/FTP nebo F/FTP
    - **ISO/IEC 11801 2nd Ed. (2002); TIA/EIA nepopisuje**
- CAT 7a (třída Fa)
    - až 1000 MHz
    - vznik 2010
    - záměr pro budoucí podporu 40Gbase-T
    - měření potvrdilo podporu 40Gbase-T do 50 m
    - a 100 GbE do 15 m
    - oficálně však 40Gbase-T nepodporuje
    - nejsou komerční zařízení, co by CAT 7a podporovala
    - standardně S/FTP nebo F/FTP
    - **ISO/IEC 11801 2nd Ed. (2008); TIA/EIA nepopisuje**
- CAT 8 (třída I a třída II)
    - až 2000 MHz
    - 25GBASE-T / 40GBASE-T
    - Třída I (CAT 8.1) - plně kompatibilní s CAT 6a (pomocí 8P8C konektoru - RJ45)
        - standardně provedení F/UTP nebo U/FTP
        - **ANSI/TIA-568-C.2-1, ISO/IEC 11801-1:2017**
    - Třída II (CAT 8.2) - plně kompatibilní s CAT 7a (pomocí konektoru TERA nebo GG45)
        - standardně provedení S/FTP nebo F/FTP
        - **popisuje pouze ISO/IEC ISO/IEC 11801-1:2017, nikoliv TIA/EIA**
        
#### 3.3 Normy
- Ethernet 10BASE-T (10 Mb/s)
    - vyhrazené 2 páry (1 TX; 1 RX)
    - vodiče 1, 2, 3 a 6
- Fast Ethernet 100BASE-T4 (100 Mb/s)
    - vyhrazené všechny 4 páry (1 TX; 1 RX; 2 Bi - obousměrné, karty se dohodnou)
    - podpora PoE (Power Over Ethernet)
- Gigabit Ethernet
    - vyhrazené všechny 4 páry (1 TX; 1 RX; 2 Bi - obousměrné, karty se dohodnou)
    - podpora PoE (Power Over Ethernet)

#### 3.4 Zapojení
- Norma EIA/TIA 568A (USA) 
- Norma EIA/TIA 568B (Evropa)
- vždy se střídá dvoubarevný s jednobarevným
- crossover - využije se na jedné straně norma A a na druhé straně norma B (využití pro propojení dvou síťových zařízení, v dnešní době již není potřeba, síťová karta to pozná sama)

### 4. WiFi
Wireless Fidelity. Využití v místě, kde nelze kabel.

- šíření signálu
    - unicast - dvoubodový přenos (point-to-point)
    - broadcast - všem stanicím
    - multicast - skupinově (do určených stanic)
- dvoubodový přenos
    - simples - jednosměrný
    - half-duplex - obousměrný střídavý (vždy právě jeden směr)
    - full-duplex - obousměrný současný

#### 4.1 Kanály IEEE 802.11

- IEEE 802.11 v pásmu 2.4 GHz
    - IEEE 802.11b-1999 - až 11 Mb/s [**WiFi 1**]
    - IEEE 802.11g-2003 - až 54 Mb/s [**WiFi 3**]
- IEEE 802.11n-2009 2.4/5 Ghz - až 600 Mb/s v závislosti na počtu antén, typu modulace, pásma, šířce kanálu atd. (MIMO) [**WiFi 4**]
- IEEE 802.11 v pásmu 5 GHz
     - IEEE 802.11a-1999 - až 54 Mb/s [**WiFi 2**]
     - IEEE 802.11ac (2013) [**WiFi 5**]
         - podporuje šířky pásem 20, 40, 80 a 160 MHz
         - až 8 MIMO samostatných datových toků
         - až 4 klienty v MU-MIMO
         - hustější modulace až 256-QAM
         - až 6.77 Gb/s pro agregaci (pro MU-MIMO)
         - až 3466.8 Mb/s pro jednoho klienta (160 MHz, 4 samostatné datové toky)
     - IEEE 802.11ax (2019) [**WiFi 6**] [ještě nevyšla]
- kanály 2.4 GHz
    - Český telekomunikační úřad povoluje v bezlicenčním pásmu využívat **13 kanálů** (2412 - 2472 MHz), vzájemně posunuty o 5 MHz
        - kanál 1 - 2412
        - kanál 2 - 2417
        - atd. (*viz obrázek*)
    - Český telekomunikační úřad stanovuje maximální vysílací výkon na **20 dBm** (decibel nad miliwatten) neboli **100 mW** ve zmíněném pásmu
    - jednotlivé kanály se překrývají (šírka 22 MHz) = **vzájemné rušení**
        - kanály, které se při šířce 22 MHz nepřekrývají - 1, 6 a 11 (*viz obrázek*)
    - velmi časté zaneřádění pásma, vysílače se navzájem překrývají atd.
    - časté rušení od mikrovlnek atd.
    - výhodou je delší vlnová délka - tj. větší dosah, ale menší rychlost
- kanály 5 GHz
    - Český telekomunikační úřad povoluje v bezlicenčním pásmu využívat frekvence
        - 5150 MHz až 5350 MHz - pouze uvnitř budov (povolen vysílací výkon 200 mW střední e.i.r.p.)
        - 5470 MHz až 5855 MHz - mimo budovy (standard IEEE 802.11a) (*jiné vysílací výkony...*)
    - to se rovná více nepřekrývaných kanálů
    - vhodné do míst, kde nejsou překážky, kratší vzdálenosti
    - menší zaneřádění pásma a rušení
    - vyšší rychlosti na kratší vzdálenosti

![kanaly 2.4 GHz](https://github.com/jmeinlschmidt/maturita-sps-cl/blob/master/2018-2019/software/17-komunikace-na-linkove-vrstve-osi-iso/obrazky/obrazek-1.png "kanaly 2.4 GHz")

#### 4.2 CSMA/CA
WiFi je **half-duplex**! (definuje norma 802.11)
- full-duplex - stále výsada kabelů (část párů pro přenos jedním směrem, část druhým)
- teoreticky lze udělat full duplex (v reálném světe se standardně nevyužívá) - vyhradit jeden kanál pro přenos jedním směrem a druhý pro přenos druhým směrem (*vyžaduje další vysílač a příjmáč!*)


Pro řešení přenosu dat v **half-duplexu** se využívá protokol **CSMA (v ethernetu), CSMA/CA (ve WiFi)**, aby nedocházelo ke **kolizím** při přenosu dat v daném směru, uzly nejsou schopny naráz vysílat a příjmat.
- vysílač naslouchá: zda-li jiné uzly již nevysílají
- vysílá-li uzel: vysílač počká, než probíhající vysílání skončí
- každý uzel informuje ostatní uzly o úmyslu vysílat
- všechny uzly **vědí o vysílání dříve, než k němu dojde**


#### 4.3 Antény

Reálné ztráty signálu (útlum)
1. fyzické překážky
2. vlhkost
    - nejvíce pohlcují signál mokré listnaté dřeviny
3. interference signálu
4. konektory
5. útlum pigtailu (anténní kabel)
6. útlum bleskojistky

Kompenzance ztrát
- vyšší vysílací výkon (max do limitu dle Českého telekomunikačního úřadu)
- zisk vysílacích / příjmacích antén (max do limitu dle Českého telekomunikačního úřadu)

Fresnellova zóna
- přímá viditelnost není dostačující podmínka
- = prostor bez překážek (**elipsoid kolem spojnice vysílacích/příjmacích bodů**)

Šíření signálu
1. všesměrové (360°)
2. sektorové (30° až 180°)
3. směrové (pod 10°)

Všesměrové (360°)
- tvar zploštělé koule okolo prutové antény (donut)
- vhodný do míst s velkým počtem klientů, rozlehlá plocha
- vhodné umístění doprostřed budovy (pozor - zdi deformují signál)

Sektorové (30° až 180°)

Směrové (pod 10°)

#### 4.4 Módy bezdrátové komunikace

Jednotlivé módy
1. Ad-Hoc / Peer-to Peer Networking
2. AP (Access Point) - přístupový bod
3. WiFi router - gateway
4. Klient
5. Bridge - bezdrátový spoj
6. MultiPoint Bridge 
7. WDS (Wireless Distribution System)

Ad-Hoc / Peer-to Peer Networking
- WiFi síť neobsahuje žádný společný přístupový bod
- uzle komunikují pouze mezi sebou (klient a server zároveň)

AP – Access Point (přístupový bod)
- v uvozovkách WiFi switch
- uzle komunikují s jedním centrálním prvkem (AP)

WiFi router - gateway
- AP s NAT
- uzle komunikují s jedním centrálním prvkem (AP)

Klient
- nejčastěji používaná funkce (vždyck bude více klientů než serverů)
- přímo adaptéry PCI, PCI-e, USB apod.

Bridge - bezdrátový spoj
- specifikován v normě 802.11c 
- transparentní propojení dvou počítačových sítí
- bezdrátový spoj se tváří stejně, jako kdyby zde vedl klasický TP kabel
- nastavení režimu
    - zadáváme ethernetovou MAC adresa protějšího zařízení
    - vznikne point-to-point WiFi spoj
    - spoj je naprosto odolný proti pokusům o průnik
    - do takovéhoto spoje již nelze připojit další zařízení

MultiPoint Bridge
- režim je podobný režimu Ad-Hoc / Peer-to Peer Networking 
- všechny AP v síti - nakonfigurovány v tomto režimu
- všechny body v síti jsou pak 100% transparentně spojeny

WDS (Wireless Distribution System)
- bezdrátové propojení dvou access pointů
- lze připojit až 6 zařízení k jednomu AP
- připojením dalších klientů – rychlost rapidně klesá
- vytvořením WDS bridge – snížení reálné rychlosti na polovinu
- použitelné je pro malé sítě
    - kde nezáleží na rychlosti přenášených dat
    - lepší řešení - **repeater nebo více AP**
    
SSID - Service Set Identifier
- jedinečná identifikace AP – Textový řetězec 
- čitelný všemi wifi klienty - broadcast
- při vzájemné komunikaci - musí předávat tentýž SSID
- BSS (Basic Service set) ESS (Extended Service Set):
    - Konfigurace skupin klientů
    - AP si předávají klienta  - podpora roamingu
    - uživatelé skupiny ESS mohou volně cestovat mezi BSS
    - přičemž je zachováno trvalé připojení 

BSSID - Basic Service Set IDentifier
- MAC adresa AP

#### 4.4 Šifrování

Nezabezpečená bezdrátová síť WLAN
- vaším jménem lze konat trestnou činnost
- provádět průniky do cizích sítí (banky, armáda, státní orgány…)
- díky IP adrese zjistí poskytovatele INETu

Základní metody zabezpečení (čím více použitých metod, tím více překážek k prolomení)
1. zamezení vysílání mimo perimetr (uvnitř budovy, snížit vysílací výkon, použít sektorové antény)
2. změna výchozích přístupových údajů k nastavení AP (heslo 12 a více znaků)
3. skrytí SSID (stejně jde ale odposlechnout z komunikace mezi klienty)
    - stejně se jde připojit přes BSSID
4. vypnout DHCP (klient tak musí znát svoji IP, bázi, masku a brány podsítě)
5. filtrování MAC adres
6. **nejdůležitější** - šifrovaný přenos dat
    - WEP (již prolomeno)
    - WPA (delší šifrovaíc klíč než WEP - 128 bit)
    - WPA-TKIP (bezpečné asi jako WEP) 
    - WPA-PSK (lepší)
    - WPA2 (využívá AES, vždy vybírat varianty založené na AES!)
        - personal (malé domací sítě - pouze heslo)
        - enterprise (rozšířené autentizace - jméno/heslo) - řeší RADIUS server (protokol AAA), server buď přihlášení přijme nebo odmítne

### 5. ISO/OSI

#### 5.1 Referenční model

1. aplikační vrstva (FTP, SFTP, SSH, HTTP, HTTPS, DNS, DHCP, POP, IMAP, Telnet atd.) -> **aplikační data*
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
