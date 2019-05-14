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
