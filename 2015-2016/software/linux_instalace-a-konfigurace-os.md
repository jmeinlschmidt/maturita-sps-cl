# Linux: Instalace a konfigurace OS

## Popište instalaci OS, instalační média, internet

V BIOSu je nutné nastavit či vybrat typ média, ze kterého chceme instalovat, např. CD nebo USB. Je také možné využít instalační program z internetu, resp. ze sítě.

### Nastavení BIOSu, rozdělení disku 

### Vysvětlete termíny Oddíly – přípojné body (root, swap, home…): význam

Intalátor může automaticky určit rozvržení přípojných bodů, ale lze využít i ruční nastavení. 

Je dobré využít jeden oddíl pro OS (nastavuje se pro root, resp. `/`), druhý pro data a vytvořit speciální swap oddíl. Dobrou praktikou je také vytvořit speciální oddíl pro adresář `/home`.

### Popište Program pro rozdělení disků 

V programu pro rozdělení disku je obvykle vyobrazen aktuální stav rozložení disku. 

Uživatel může vytvářet nové oddíly a případně již vytvořené oddíly zvětšovat či zmenšovat, což se zpravidla neobejde bez fragmentace dat na oddílech.

## Konfigurace systému, popište způsob konfigurace OS, konfigurační soubory – jejich umístění 

Linux lze plně konfigurovat. Konfigurace lze provádět v omezeném množství pomocí GUI aplikací, anebo využít terminálu, kde lze změnit cokoli. V terminálu se pro konfiguraci využívá mnoho speciálních příkazů.

### Nastavení systému - GUI: umístění, základní nástroje

### Jak se konfigurují sítě – nastavení síťové karty (IPadresa, maska, brána, DNS - GUI)

## Instalace / odinstalování SW - vysvětlete termín repozitáře, popis, význam

Repozitář je ověřené úložiště programů, které lze nainstalovat jen pokud je na repozitář v systému reference.

Pro instalaci a odinstalaci SW lze využít softwarových center, tzn. GUI aplikací, nebo využít terminálů a příkazů jako `sudo apt-get install xxx` a `sudo apt-get remove xxx`.

### Jaká je Struktura programu v GNU/Linuxu, co jsou balíčky, příznak X

Balíčky je soubor, který má přesně definovanou strukturu a jeho název je tvořen podle jistých pravidel. Je to v podstatě instalační soubor pro program a je specifický pro distrubuci.

### Debian – popište systém balíčků, Synaptic, význam

**Synaptic** je GUI správce balíčků, který pracuje s několika ověřenými repozitáři a poskytuje uživatelsky přívětivou instalaci, odinstalaci, aktualizaci, nastavování atp.

### Debian - Instalace SW – jaký GUI program používáme pro instalaci SW, adresáře pro programy v GNU/Linuxu

Debian je dodáván s centem softwaru, což je "market" aplikací pro Debian. Je možné využít externích programů, viz Synaptic.

## Diagnostika síťové komunikace – vysvětlete činnost příkazů ifconfig, traceroute, ping, netstat, jejich základní použití  

Všechny následující příkazy se využívají pro diagnostiku či debugování sítě.

`ifconfig` vypíše informace o síťových kartách, mac adresy, ip adresy atp.

`ping` je příkaz, který zjistí, zda-li je daná ip adresa dostupná.

`traceroute` provede skoky na počítače/servery od současného místa až k danému serveru/počítači s IP.

`netstat` vypíše aktivní internetové konektivity.

## CLI  - příkazy/Debian: proveďte nastavení síťové karty – IP adresa, maska, brána, soubor /etc/fstab - význam

## CLI – příkazy/Debian: proveďte aktualizaci, instalaci z repozitářů, odinstalaci SW (program mc) 

Aktualizace repozitářů a programů lze provést pomocí `sudo apt-get update`, instalace repozitářů pomocí `sudo add-apt-repository` (v Debianu je nutné nejprve nainstalovat balíček `software-properties-common`) a odinstalace programů pomocí `sudo apt-get remove`.
