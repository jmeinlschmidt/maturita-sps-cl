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
    - elektrické vodiče (kroucená dvojlinka - twisted pair; koaxiální kabel)
    - optické vodiče (využívá se určité pásmo, např. 1260-1650 nm, každé pásmo jiný útlum, vzdálenost útlum atd., lze mít více pásem v jednom vodiči - potřeba použít rozbočovač)
        - jednovidové (anglicky Single Mode - **SM**) - delší vzdálenosti
        - vícevidové (anglicky Multi Mode - **MM**) - kratší vzdálenosti
- signál
