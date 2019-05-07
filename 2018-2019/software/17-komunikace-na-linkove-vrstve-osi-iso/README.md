# 17/25 - Komunikace na linkové vrstvě OSI/ISO - aktivní prvky
## Zadání
-	Komunikace na linkové vrstvě OSI/ISO
- Aktivní prvky
- Společná norma znalostí pro všechny okruhy
    - Kabeláž – typy, kategorie, normy, zapojení
    - WiFi:
        - 802.11 - 2,4/5GHz – kanály, 
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
    
### 2. WiFi
- šíření signálu
    - unicast - dvoubodový přenos (point-to-point)
    - broadcast - všem stanicím
    - multicast - skupinově (do určených stanic)
- dvoubodový přenos
    - simples - jednosměrný
    - half-duplex - obousměrný střídavý (vždy právě jeden směr)
    - full-duplex - obousměrný současný
    
### 3. Přenos signálu
- vodič
    - elektrické vodiče
        - kroucená dvojlinka (anglicky Twisted Pair - **TP**) - UTP, STP, SFTP atd.
        - koaxiální kabel
    - optické vodiče (využívá se určité pásmo, např. 1260-1650 nm, každé pásmo jiný útlum, vzdálenost útlum atd., lze mít více pásem v jednom vodiči - potřeba použít rozbočovač)
        - jednovidové (anglicky Single Mode - **SM**) - delší vzdálenosti
        - vícevidové (anglicky Multi Mode - **MM**) - kratší vzdálenosti
- signál

### 4. ISO/OSI referenční model
1. aplikační vrstva (FTP, SFTP, SSH, HTTP, HTTPS, DNS, DHCP, POP, IMAP, Telnet atd.) -> **aplikační data*
2. prezentační vrstva (upravení dat do podoby, kterou program vyžaduje - šifrování, serializace XML, JSON atd.)
3. relační vrstva (navazování, udržování a zavírání spojení; protokoly L2TP, SOCKS - websockety)
4. transportní vrstva (TCP, UDP) -> **čísla portů, TCP/UDP segment**
5. síťová vrstva (protokoly IP, IPSec) -> **IP adresy, paket**
6. linková vrstva (bridge, switch) -> **MAC adresy, datagram*
7. fyzická vrstva (fyzická kabeláž, přenos dat, signál atd.) -> **frame**

### 5. Kabeláž - kroucená dvojlinka
Důvod kroucení - vzájemné vyrušení el. mag pole, snížení přeslechů, snížení rušení. Mb/s  Mbps (per second) Gb/s Gbps. !!! G**B**/s  = 8 x G**b**/s  !!!

- typ vodiče
    - drát (jeden kus mědi, nelze ohýbat příliš často, láme se)
    - licna (hodně malých drátků - lepší pro propojení, lze ohýbat, namáhat, neláme se, ale větší útlum - jen na menší vzdálenosti)
- použití
    - venkovní (ochrana proti UV, odolnější plášť, vyztužené - umožňuje zavěšení)
    - vnitřní
- kategorie ISO/IEC 11801
    - CAT 1 (telefonní linky, max 100 kHz)
    - CAT 2 (digitální přenos zvuku, max 1 MHz)
    - **TIA/EIA popisuje až následující kategorie**
    - CAT 3
        - až 16 MHz
        - převážně v 90. letech pro telefonní linku
        - 10BASE-T
        - 100BASE-T4 při využití 4 párů
    - CAT 4 (velmi rychle nahrazena CAT 5, často se ani neuvádí)
        - až 20 MHz
        - 10BASE-T
        - 100BASE-T4 při využití 4 párů
    - **TIA/EIA popisuje následující**
    - CAT 5
        - až 100 MHz
        - 10BASE-T and 100BASE-TX při využití dvou párů (díky tomu lze teoreticky udělat 2x100BASE-TX); každý pár pro jeden směr - full duplex (max 100 m)
        - 1000BASE-T při využití 4 párů (vzdálenost není definována)
        - využívá se 8P8C konektor (RJ45)
    - CAT 5e
        - zhruba stejné parametry jako CAT 5
        - vyšší nároky na výrobu, nižší impedance, menší přeslechy atd. => větší šance, že se povede dosáhnout 1000BASE-T
        - využívá se 8P8C konektor (RJ45)
    - CAT 6
        - až 250 MHz
        - 10/100/1000BASE-T do 100 m
        - 10GBASE-T do 55 m
        - využívá se 8P8C konektor (RJ45)
    - CAT 6a
        - až 500 MHz
        - vznik 2009
        - 10/100/1000/10GBASE-T do 100 m
        - menší útlum než CAT 6, tj. zvládne to samé, ale na delší vzdálenost
        - využívá se 8P8C konektor (RJ45)
    - **následující popisuje pouze ISO/IEC 11801, nikoliv TIA/EIA**
    - CAT 7 (třída F)
        - až 600 MHz (při využití konektorů GG45, ARJ45, nebo TERA)
        - vznik 2002
        - 10/100/1000/10GBASE-T do 100 m
        - GG45, ARJ45, nebo TERA konektory využivá velmi málo hardwaru (specializovaný hardware, vysoká cena)
        - kompatibilní s 8P8C konektorem (RJ45), ale nedochází k využití maximální frekvence; vzhledem k tomu je cenově výhodnější využít CAT 6a (pokud není potřeba extra stínění)
    - CAT 7a (třída Fa)
        - až 1000 MHz
        - vznik 2010
        - záměr pro budoucí podporu 40Gbase-T
        - měření potvrdilo podporu 40Gbase-T do 50 m
        - a 100 GbE do 15 m
        - oficálně však 40Gbase-T nepodporuje
        - nejsou komerční zařízení, co by CAT 7a podporovala
    - CAT 8 (třída I a třída II)
        - až 2000 MHz
        - Třída I (CAT 8.1) - plně kompatibilní s CAT 6a (pomocí 8P8C konektoru - RJ45)
        - Třída II (CAT 8.2) - plně kompatibilní s CAT 7a (pomocí konektoru TERA nebo GG45)
