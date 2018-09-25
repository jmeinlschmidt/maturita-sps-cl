# Windows: Struktura a zavedení OS

## Vysvětlete termín souborové systémy – jejich rozdělení, druhy

Souborové systémy přinášejí způsob organizace dat ve formě souborů a adresářů. Každý soubor či adresář musí mít určeno, kde na HDD je, jaký je jeho název, v jakém adresáři se nachází a jaká má přístupová práva.

### Co je stromová struktura adresářů – důležité systémové adresáře

Stromová struktura adresářů využívá vnořených adresářů, tzn. adresář v adresáři. Tento systém se využívá pro přehlednost.

Důležitými systémovými adresáři je adresář `Windows/`, obsahující samotný systém, `Program Files`, obsahující nainstalované programy, a `Users`, obsahující data uživatelů.

### Jaké znáte Typy souborů, co jsou spustitelné soubory, rozdělení podle přípony – programy

Existují 2 základní typy souborů - binární a textové.

Spustitelné soubory jsou interaktivní soubory, které vykonávají nějaké akce. Mohou být binární i textové.

Příklad textových souborů:
- `.txt`
- `.md`
- `.bat`, `.cmd` (spustitelné)
- `.bash` (spustitelné)
- `.html`

Příklad binárních souborů:
- `.png`
- `.jpg`
- `.exe` (spustitelné)

### Vysvětlete termín Knihovny, atributy souborů, dočasné soubory – jejich umístění, význam

Knihovny se využívají pro volně přístupné funkce, které si jednotlivé programy volají a používají.

Atributy souborů určují, zda-li lze soubor číst, editovat, spouštět atp.

Dočasné soubory se vytvářejí pro ukládání aktuálních stavů programu, nebo data uložená pro příští použití.

## Jak probíhá bootování OS: 

Bootování je proces oživení počítače, kdy dochází k probuzení počítače, postupnému zavedení OS, inicializaci a konfiguraci HW.

### Popište strukturu HDD, stopy, sektory, cylindry

Povrch disku je rozdělen na stopy (soustředěné kružnice). Každá stopa je navíc příčně rozdělena na sektory.

**Stopa** - Jedna soustředěná kružnice na jednom disku.

**Sektor** - Jeden dílek stopy.

**Cylindr** - všechny stopy se stejným číslem na všech discích.

### Vysvětlete termín MBR, SBR – jejich význam, popis, tabulka rozdělení disků

MBR (master boot record) je zavaděč OS, kterému BIOS předává při startu počítače řízení.

### Jak provedeme Opravu MBR – Win7/8

V příkazovém řádku zadáme příkaz `bootrec.exe /fixmbr` a následně `bootrec /fixboot` a restartujeme počítač.

## Vyjmenujte vrstvy OS Windows, jejich základní popis  

### Vysvětlete termín Kernel – jeho význam (porovnejte s Linuxem)

Kernel je čisté jádro OS (bez programů).

### Popište Vrstvy HAL, API, GUI – jejich význam

### Co představuje Systém registrů  - význam, soubory/umístění, uživatelské registry 

Registry slouží pro nastavení OS; dříve ukládány do `.ini` osuborů.

## Jaké znáte další Základní typy souborů v OS, význam skrytých souborů, řešení bezpečnosti přístupu k souborům/adresářům 

Skryté soubory slouží pro skrytí důležitých souborů před uživatelem, který by je mohl smazat a zapříčinit tak fatální chybu. 

## Popište detailněji Bootování Windows 7/8 – vlastní průběh zavádění OS Windows, význam adresáře/disk.oddílu boot, které jsou základní zaváděné systémové soubory

## Vysvětlete termín BIOS/UEFI – význam, popis, reset BIOSu,

BIOS je základní systém řízení vstupu a výstupu. Má na starosti inicializaci a konfiguraci SW a HW a následné spuštění OS.

