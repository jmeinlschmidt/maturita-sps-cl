# 22/25 - GNU/Linux – instalace a konfigurace OS
## Zadání
-	GNU/Linux – instalace a konfigurace OS
-	Instalace OS W/L:
    - instalační média, předinstalační příprava 
        - struktura HDD – LBA/CHS:
        - BIOS/UEFI: MBR, PartitionTable, GPT, SBR
        - oddíly – rozdělení disků, význam
            - připojení oddílů/disků (Linux)
        - druhy instalací
    - základní poinstalační nastavení OS,
- Základní konfigurace OS:
    - Průběh/popis bootování OS, nastavení v BIOS/UEFI (SecureBoot)
    - konfigurační soubory ve Windows/Linuxu
        - důležité kofig.soubory – umístění popis
        - W: význam, struktura a údržba registrů
        - konfigurace síťové karty – nastavení parametrů sítě
    - GUI, CLI – konfigurační SW/ příkazy
    - Instalace programů, utilit v OS Windows/Linux
        - Windows Update/ repozitáře – popis, význam
        - instalace CLI (Linux – manažer balíčků)
        - SW – Licence, 
    - Uživatelské profily/Účty:
        - význam, druhy, nastavení, bezpečnost
    - SBO – popis, význam, nastavení, použití
    - Základní údržba OS – postupy

## Vypracováno

### 1. Instalační média, příprava

#### 1.1 Předinstalační příprava
- buď originální instalační DVD
- nebo využít flash, popř. vytvořit vlastní instalační médium (*programem např. RUFUS*)
- naformátovat disk, na který budeme instalovat OS
- popř. využít program pro rozdělení disku (*např. GPARTED*)
- instalační proces většinou naformátuje disk sám
- vybrat v BIOSu médium, ze kterého chceme instalovat (musí mít vlastní zavaděč - boot loader)

#### 1.2 Struktura HDD

#### 1.3 LBA vs CHS

#### 1.4 BIOS a UEFI
- rozdíl oproti BIOS, novější (je to náhrada)
- podporuje Secure Boot
- umožňujě využít GPT

GPT (GUID Partition Table)
- nahrazuje starší tabulku MPT (**Partition Table**; uložena v MBR)
    - lze adresovat maximálně 2 TB disk
    - maximálně 4 primární oddíly (jde z nich načíst OS)
    - nebo 3 primární a jeden rozšířený, těch může být až 128 (ale nelze z nich spouštět OS)
- umožňuje adresovat obrovské disky
- až 128 oddílů
- pracuje pouze s LBA
- součást UEFI

Secure Boot
- UEFI tak umožňuje načtení jen ověřených softwarových komponent
- např. nelze sputit ukradené Windows
- naopak podporuje OEM instalace (OS zakoupený s např. notebookem)
- až od Windows 8
- klíč je přímo v paměti UEFI na desce

#### 1.5 Druhy instalací

### 2. Rozdělení disků
význam,     připojení oddílů/disků (Linux)

### 3. Základní poinstalační nastavení
