# Komunikace na síťové vrstvě OSI/ISO - směrovače

## Switch

- aktivní prvek
- **propojuje síť a směřuje data tam, kde jsou potřeba**
- propojuje jednotlivé prvky
- přeposílá data tam, kde jsou potřeba (oproti hubu)
- "přepínač"
- *"silnice spojující města ve státě"*

### Propojení

- propojení "sloty"
- propojení agregací - propojit více slotů
- optikou, páteřní spoj - most (patch/uplink)

## Router

- aktivní zařízení
- **odděluje sítě, maškarádou předává data z WAN do LAN**
- routováním přeposílá datagramy k cíli
- spojuje dvě sítě
- *"hraniční přechody spojující různé země"*

### NAT

- **síťová maškaráda**; překlad síťových adres
- upravuje síťový provoz přes **router** přepisem výchozí nebo cílové IP - adresy
přístup pro více PC z LAN do internetu pod jednou veřejnou IP

## Firewall

- síťové zařízení
- řízení a zabezpečování síťového provozu
- "kontrolní bod"
- definuje pravidla pro komunikaci mezi sítěmi, které od sebe odděluje
- hlídá provoz mezi LAN a zbytkem světa; mezi PC a LAN
- brání paketům průchod
  - dovnitř i ven
- filtrace paketů
- speciální programy
  - např. Conada, PrivateFirewall, SuitPro aj.
  - správa pravidel firewallu
  - přidání, editace, mazání pravidel
- 

### Protokoly

- HTTP - 80
- HTTPS - 443
- FTP - 21
- SSH - 22
- MAIL (POP3 - 110, IMAP - 143, SMTP - 25)
- TCP
  - pro přenos toku bajtů
  - aplikace na PC mohou vytvářet spojení
    - obousměrné přenášení dat

## MAC

- ve stejné části sítě NESMÍ BÝT dvě NIC se stejnou MAC adresou
- 48 bitů - hexadecimální zápis
- význam
  - komunikace s nejbližším síť. prvkem
  - MAC používají switche i routery
  - HW identifikace stanice PC/síť. prvku
    - komu poslat data
- lze komunikaci zakázat/povolit pro konkrétní stanici (router)
- zjištění MAC adresy - příkaz `ipconfig`
 
### ARP

- protokol
- přiřadí IP adresu k MAC adrese

### RARP

- opačná funkce
- přiřadí MAC adresu k IP adrese

