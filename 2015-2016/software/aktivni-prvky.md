# Komunikace na linkové vrstvě OSI/ISO - aktivní prvky

## KABELY

- kabel (U/S)TP - kroucená dvojlinka; přímý kabel
  - oddělení elmag. kroucením
- 4 páry
- pár může přijímat, nebo vysílat
- Fast Ethernet - 1x přijímač, 1x vysílač
- Gigabit Ethernet - 4x BI (rozhoduje vysílání/příjem)

## Typy zapojení

- **A**

Amerika
1, 2, 3, 6 - zelená, oranžová

- **B**

Evropa
1, 2, 3, 6 - oranžová, zelená

## Crossover

- typ Ethernetového kabelu
- jeden konec zapojení typ A, druhý typ B
- nejčastěji se používá pro propojení 2 zařízení **stejného typu** (tedy switch-switch, PC-PC atp.)

## RJ45

- koncovka (zakončení) kabelu
- nejčastěji používaná u zapojení síťových kabelů
- **8 pozic vodičů**
- dvě podoby - samec & samice (zásuvka)

## Kategorie

### cat 5

- přenos kroucenou dvojlinkou
- šířka pásma až 100 MHz
- izolace typicky z PVC

### cat 5e

- oproti cat 5 vyšší nároky na splnění standardu
- vyšší požadovaná odolnost proti přeslechům
- využívá všechny 4 páry vodičů - vhodná na Gigabit Ethernet

### cat 6

- standardizován pro Gigabit Ethernet
- přesnější specifikace pro přeslechy a šum
- šířka pásma až 250 MHz
- max 100m, pro 10GBASE-T jen 55m

### cat 6a

- šířka pásma až 500 MHz

### cat 7

- pro větší vzdálenosti Gigabit Ethernet
- až 600 MHz

## TCP/IP

- nepopisuje protokoly TCP a IP
- kompletní rodina všech protokolů a pravidel
- TCP - kontroluje se
- UDP - nekontroluje se

## Zapouzdření dat

- vznik informace (message) pomocí aplikace
- data, data, data - rozdělení-fragmentace **message**
  - => [app header, data] - **app data**; hlavička aplikační vrstvy: protokol aplikace
  - => [tcp/udp header, app data] - **tcp segment**
  - => [IP header, tcp/udp header, app data] - **IP paket**
  - => [Eth heder, IP header, tcp/udp header, app data, eth footer] - **ethernet frame**
- "datagram"

## QoS

- rezervace a řízení datových toků v sítích
- protokoly pro QoS se snaží zajistit vyhlazení a dělení dostupné přenosové kapacity
- provoz některých služeb/uživatelů je nutno omezit
- nastavují se pravidla
  - přednosti/priority
  - maximální/minimální přenos. pásmo

## Diagnostika sítě

- v cmd příkazy ipconfig -all zobrazí veškeré informace o aktuální síti
- příkaz ping ověří, že "vidí" zařízení na dané IP adrese

### LEDky síťové karty blikají

- ovladač OS, propojení plné funkční
- zkontrolujeme nastavení sítě
  - IP adresa (neplatná IP/maska/DNS)

### LEDky síťové karty stále svítí

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

### Síťová karta

- ipconfig /all
- PC v subnetu ping, arp
- brána routeru: ping
- pc mimo náš subnet: ping tracert
  - zjistíme, kde se nám ping zastaví
  - "násobný ping" na další a další brány

### IP adresy

- určujeme 
  - privátní/veřejná
  - typ A/B/C
- maska
  - jaké části můžeme využít
  - 255.255.255.240
    - zbývá jen 16 - 2 (síť & broadcast) možných IP adres
- prefix
  - vyjadřuje počet "1" v masce (binárně)
  - pro 255.255.255.240 je prefix /28

### A

- veřejné - 0-127.x.y.z
- privátní - 10.x.y.z

### B

- veřejné - 128-191.x.y.z
- privátní - 172.16.y.z - 172.31.y.z

### C

- veřejné - 192-223.x.y.z
- privátní - 192.168.y.z

## ODSTRAŇOVÁNÍ VIRŮ

- vir - zdroj škodlivého kódu
  - internet - freeware, cracknuté programy/os, hry…
  - externí média (USB, DVD…)
  - nekontrolovatelný průnik
    - přes admin účet
  - základní ochrana
    - **UAC** - práce v uživatelském účtu
    - podobně jako v linuxu
- rozsah zavirování
  - je-li OS napaden škodlivým kódem
    - je pravděpodobné, že je napaden i “nouzový režim”
    - a zároveň soubory systému bodu obnovené - **SBO**
  - DŮSLEDEK
    - spouštění lokálního antivirového programu + nouzového režimu - **neúčinné**
    - bez kontroly souborů SBO - **neúčinné**

### POSTUP

- důsledné čištění
  - odstranit veškeré nepotřebné dočasné soubory (/temp, .bak, .log…)
    - je zdlouhavé aby antivir kontroloval vše
  - popř. odstranit nepotřebný a podezřelý SW
- SBO
  - můžeme odstranit
  - nebo zpřístupnit antivir. programu
    - zůstanou-li zavirován
- po úspěšném odvirování
  - nezapomenout zapnout SBO
    - nejrychlejší a nejméně pracný způsob jak zprovoznit poškozený / nefunkční OS Win
    - proto jej používáme a nevypínáme
  - zpřístupnění souborů SBO
