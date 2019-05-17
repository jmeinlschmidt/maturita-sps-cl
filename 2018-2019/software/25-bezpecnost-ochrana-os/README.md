# 25/25 - Bezpečnost - ochrana OS
## Zadání
-	Bezpečnost - ochrana OS
- malware, antivirový SW – postup odvirování – VŠE!!!
- firewally (W/L - iptables) – VŠE!!!

## Vypracováno

### 1. Firewall
- ochrana počítače nebo lokální počítačové sítě (před útoky z WANu)
- vnější útoky
    - zabezpečení přístupové cesty
    - monitoring vstupních cest (včas získáme informaci - např. scan portů, DDoS atd.)
- **firewall není antivir**
    - antivirový program kontroluje obsah souborů/dat, porovnává se vzorky v databázi, zpomaluje činnost počítače
    - firewall kontroluje komunikaci, kdo s kým jak komunikuje, kontroluje porty, IP adresy atd.
- vnitřní útoky
    - je možné škodit i uvnitř počítačové sítě
    - je potřeba navrhnout opatření
- firewall
    1. ochrana jednoho počítače
    2. ochrana LAN (odděluje LAN - WAN)
        - kontroluje tok, nikoli obsah!
        - může vykonávat složitější úkoly
  
1. Aplikační proxy firewall
- pracuje na **aplikační vrstvě ISO/OSI**
- umí chránit i před různými viry, škodlivým nebo nevhodným obsahem
- umí řídít přístup na základě autentizace a autorizace uživatele
- nevýhoda - *zpomaluje síťový provoz*
  
2. Paketový filtr
- pracuje na třetí a čtvrté vrstvě (**transportní a síťové**) ISO/OSI
- mnohem rychlejší než proxy, ale nemá tolik možností a bývá komplikovanější
- IP adresy, MAC adresy a porty
  
3. Stavový paketový filtr
- sleduje spojení (**relační vrstva**) ISO/OSI
- speciální varianta paketového filtru
- dokáže filtrovat na základě stavu spojení
- *ochrana proti scanování portů, zjišťování typu OS, falšování zdrojové IP adresy, DoS (Denial of Service) útoky atd.*
  
#### 1.1 Realizace firewallu
1. na společném počítači – server
    - řešení je levnější, ale nebezpečné
    - ovládnutím serveru – ovládnutí celé LAN
2. firewall na samostatném počítači
      - oddělení LAN od WAN
      - vysoká bezpečnost - aplikační úroveň
      
#### 1.2 Demilitarizovaná zóna - DMZ
- firewall na samostatném počítači pro 3 sítě
- 1. LAN, 2. WAN a 3. síť DMZ
- **DMZ – jen pro přístup z WAN (oddělena od LAN)**
    - pro služby dostupné z WAN – Web, mail, ftp
    - LAN server (LAN síť) – zcela odříznut od DMZ - ochráněn
- zvýšená bezpečnost - aplikační úroveň
 
#### 1.3 Princip firewallu
- realizuje naše pravidla co dělat s pakety
- pravidla pro manipulaci s pakety
    - obsahují podmínky
    - obsahují akce co s pakety
         - propustit paket
         - zahodit paket
         - zahodit paket s oznámením
- pravidla firewallu
    - potřebné informace pro pravidla z headeru
        - zdrojová IP adresa
        - cílová adresa
        - 0.0.0.0 (od/všem klientům)
        - čísla portů
        - příznaky
    - ukládají se do tzv. řetězů (**chain**)
    - realizují se od prvního uloženého
    - řetězce
        - INPUT - příchozí
        - OUTPUT - odchozí
        - FORWARD - pakety nejsou určeny pro toto zařízení, pouze prochází
        - *implicitně jsou řetězce prázdné*
- akce pro pravidla
    - definovány dvě základní akce pro pravidla
        - ACCEPT - povolit
        - DROP/DENNY - zahodit
        - REJECT - zamítnout (se zdvořilou odpovědí)
- příklady pro zdrojovou/cílovou adresu

```
INPUT -s 10.6.6.6/24 -j DROP
FORWARD udp -d! 10.0.0.1 -j DROP
```

- `-s` source
- `-d` destination
- `-j` akce
- `!` negace

### 2. Netfilter a iptables
- přímo součást distribuce
- přes PC lze NATovat (chová se jako router; potřeba minimálně 2 síťové karty)
- tři tabulky
    - filter (výchozí tabulka, děli se ještě na INPUT, OUTPUT a FORWARD)
    - nat
    - mandly
    - určuje se přepínačem `-t nat`
- nejznámnější příkazy
    - `--append (-A)` přidá pravidlo na konec řetězu 
    - `--insert (-I)` vloží pravidlo na začátek/místo určené číslem 
    - `--delete (-D)` odstraní pravidlo ze řetězu 
    - `--flush (-F)` odstraní všechna pravidla z řetězu
    - `--policy (-P)` definuje standardní politiku řetězu
- pakety vždy nakonci **spravovány dle politiky, implicitně vše dovoleno!**
    - `iptables -P INPUT DROP` atd.
- vymazání pravidel chainu `iptables -F INPUT`
- přidání na konec řetězu `iptables -A INPUT -p tcp -j DROP`
- přidání na začátek řetězu `iptables -I INPUT -p icmp -j ACCEPT`
- **je potřeba povolit loopback!!** `iptables -A INPUT -i lo -j ACCEPT`
- `--dport` cílový port
- `--sport` zdrojový port

#### 2.1 Tabulka NAT
- překlad síťových adres
- dělí se na řetězce
    - `prerouting` modifikace cílové adresy paketu např z WAN do LAN (statický NAT)
    - `postrouting` modifikace zdrojové adresy paketu (*maškaráda*)

#### 2.2 Tabulka Mandly
- označování paketů, spojení
- řešení QoS, rychlosti spojení, fronty atd.

#### 2.3 Stavový firewall
- rozeznává pakety podle spojení (**stavu**)
- dělí se dále na
    - `NEW` nové spojení
    - `ESTABLISHED, RELATED` již navázané
    - `INVALID` neplatné
- základní příkazy
    - `IPTABLES -A INPUT -p tcp !--syn -m state --state NEW -j DROP` zahodíme packety, které navazují spojení, ale nemají nastavený příznak SYN (synchronizace
    - `IPTABLES -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT` povolíme packety od navázaných spojení

#### 2.4 Požadavky na osobní firewall
- základ bezpečnosti
- filtrujeme pouze příchozí spojení
- povolíme loopback
- pustíme dovnitř pouze ICMP pakety, ale jejich počet omezíme
- požadavky na identifikaci (uživatel, os atd.) zdvořile odmítneme
- povolíme všechna navázaná spojení (jsou navazována zevnitř ven - output)
- dovnitř pustíme pouze spojení na určitých portech (DHCP atd.)
- uložení `iptables-save`

### 3. Zavirování
- internet, cracknutý SW, externí média, nekontrolovatelný průnik přes admin účet
- základní ochrana UAC a podobně jako v linuxu
- spuštení antiviru v běžícím OS - **neúčinné**
- spuštení antiviru v OS nouzovém režimu - **neúčinné**
- bez kontroly SBO (*Systém Bodů Obnovení*) - **neúčinné**

Možný rozsah zavirování
1.  Master Boot Record
2. Boot Record  - vlastní zavádění OS
3. Systémové soubory
4. Systém Bodů Obnovení OS

#### 3.1 Základní postup odvirování (5 částí)
- důsledné čištění
    - Odstranit nepotřebné dočasné soubory
    - Je zdlouhavé aby antivir kontroloval vše
    - popř odinstalovat přebytečný OS
- systému bodu obnovení
    - rovnou smazat (vypnout dělání záloh, najít soubory a vymazat)
    - po úspěšném odvirování zase zapnout
- Oprava MBR
    - pomocí instalačního media, vybrat oprava PC, vybrat příkazový řádek a spustit postupně
        - `bootrec.exe /fixmbr`
        - `bootrec.exe /fixboot`
        - `bootrec.exe /RebuildBcd`
- Spuštění live OS - antivir
    - Nahrát 100% nezavirovaný OS (dvd/usb)
    - Zapnout logování AV programu
        - Po odvirování zkontrolovat „log“ !!!!  
        - Některé zavirované soubory nemusí jít odstranit !!!!
    - pokud nepůjdou, nabootovat LiveLinux (jakýkoli) a udělat to z něj
- Spustit odvirovaný OS

#### 3.2 Jak pracuje ochrana UAC – popis, výhody, omezení
UAC je bezpečnostní technologie, která omezuje oprávnění aplikace na úroveň uživatele, dokud administrátor nepotvrdí zvýšení práv aplikace.

Kdykoliv chce nějaký program provést změnu PC tento nástroj nás upozorní a požádá o povolení. Ve výchozím nastavení je upozorňováno na každou změnu. Lze nastavin: Upozornit pokaždé, Upozornit, když se aplikace pokusí o změnu v PC, nebo i Nikdy.

Výhodou je zvýšení zabezpečení systému na úkor "obtěžování" uživatele s povolením.
