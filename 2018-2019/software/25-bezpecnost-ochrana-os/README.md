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
