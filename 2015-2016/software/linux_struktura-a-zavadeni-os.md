# Linux: Struktura a zavedení OS

## Vysvětlete účel souborových systémů, jejich rozdělení, vlastnosti

Souborový systém určuje princip zápisu a ukládání souborů, jejich velikost, délku názvů, vnořené složky atp. Využívají se druhy/skupiny.

**Data** - čistě uložené hodnoty; **informace** - interpretace dat.

Žurnálovací systémy se starají o ukládání a práci se soubory; systém transakcí. Nejrozšířenejší jsou např. FAT 32 (File Allocation Table), NTSF (New Technology File System), ext4 (fourth extended filesystem) atp.

### Popište Soubor/adresář – stromová struktura – základní adresáře systému

Soubor jsou uložená data v binární nebo textové formě. Adresář slouží pro logickou organizaci souborů. 

Linux je case sensitive, tzn. rozlišují se velikosti písmen. Např. `mujsoubor` a `MujSoubor` jsou odlišné soubory.

Stromová struktura - adresář.

### Vysvětlete termíny Přípojná místa – mountování

Mountování je připojení FS do adresářového stromu. 

Mountování se provádí automaticky, např. při startu PC či připojení USB, ale lze mountovat i ručně pomocí příkazu `mount`, např. `mount -t filesystem /dev/zarizeni /adresar`.

Unmount je opak mountování, a tedy odpojí FS. Využívá se příkazu `unmount`, např. `unmount /dev/zarizeni/`.

### Jaký je význam Uživatelských adresářů

Uživatelské adresáře slouží pro data uživatele a jeho nastavení.

## Popište průběh zavedení OS, zavaděče OS - MBR, GRUB, LILO

OS se zavádějí pomocí zavaděče, což je program sloužící pro správné zavedení OS.

**MBR** je zavaděč OS z HDD a je hlavním spouštěcím záznamem. Je umístěn v prvním sektoru pevného disku a je veliký 512 B. BIOS načte z MBR hlavní zavaděč a předá mu řízení.

**LILO** je linux loader, který je standardní součástí linuxových distribucí. Většinou je umístěn v MBR.

**GRUB** je výchozí zavaděč většiny dnešních distribucí Linuxu. Podporuje multiboot, tzn. umožňuje více OS na jednom PC s možností výběru při startu PC.

### Co znamená kořenový adresář /root – struktura adresářů důležitých pro zavedení OS

`/root` je domovský adresář superuživatele.

Pro správný chod systému je nutné zavést adresáře `/boot`, `/bin`, `/sbin`, `/etc`, `/lib/modules`.

### Vysvětlete termín adresář /dev  - popis význam

`/dev` obsahuje všechny soubory k zařízením a perifériím.

### Vysvětlete termín adresář /etc - popis význam

`/etc` obsahuje globální nastavení uživatelů a i např. sdílené programy, které mohou využívat všichni uživatelé.

## Základní struktura OS

### Vysvětlete termín jádro OS – modularita, popis

Jádro OS je zavedeno při startu do operační paměti a po celou dobu běhu koordinuje činnost všech spuštěných procesů. Anglicky se nazývá *kernel*.

**Monolitické jádro** - všechny služby OS běží spolu s hlavním vláknem jádra a tedy i ve stejné oblati paměti. Umožňuje neomezený a efektivní přístup k hardware.

**Mikrojádro** - Samotné jádro poskytuje jen základní funkčnost nezbytnou pro vykonávání služeb. Definuje jednoduchou abstrakci hardwaru se soupravou primitivních funkcí.

**Hybridní jádro** - Jádro se snaží zkombinovat rychlost a jednoduchost designu monolitického jádra s bezpečnostníi výhodami mikrojader. Některé služby běží v jádře ke zredukování režie proti mikrojádrům, ale jiné části monolitického jádra běží jako server v uživatelském prostoru.

Linux je modulární, a tedy se skládá z různých kousíčků a mohou se přizpůsobovat.

### Popište správu procesů GUI/CLI – proces, démon, ukončení/ spuštění

**GUI** - grafické uživatelské rozhraní; **CLI** - terminál/konzole.

**Proces** je běžící program, který je zavedený v paměti a využívá systémové prostředky a čas procesoru.

Stavy procesu jsou **běžící** (running), **čekající** (waiting), **blokovaný** (blocked), **připraven** (ready), **ukončen**, **odložený**. Procesy se mohou killovat, tzn. okamžitě ukončit.

Strategie procesů - Shortest-Job-First, FIFO, LIFO...

**Démon** je uživatel s většími právy pro programy. Většinou ve formě na pozadí běžící služby.

### Popište správu paměti – fyzický/ logický adresní prostor – swap, velikost 

Fyzický adresní prostor - adresa vnitřní paměti počítače, kterou používají řídící obvody pro vyzvednutí obsahu z paměťové buňky.

Logický adresní prostor - adresa s kterou pracuje proces při adresování dat nebo instrukcí z pohledu vykonávajícího aplikačního programu.

Swap je odkládací oddíl. Swappování se využívá při detekci procesu, který je momentálně v paměti nepotřebný/zbytečný a ten se uloží na disk pro pozdější vyzvednutí. 

## Jaké jsou Základní typy souborů, skryté soubory, řešení bezpečnosti přístupu k souborům/adresářům 

Skryté soubory, či adresáře, obsahují znak tečky (`.`) jako první znak v jejich názvu. Tyto soubory lze globálně zobrazit, ale většinou jsou v základu skryté.

Přístup k souborům a jejich bezpečnost se řeší změnou práv.

## Jaké znáte Druhy přístupových práv uživatele k souborům/adresářům, změna práv: GUI/CLI - chmod, chown, chgrp

Soubory a adresáře mají 3 základní práva a to čtení, zápis, spuštění. Dále obsahují informace o vlastníkovi, skupině atp.

Práva lze změnit "naklikáním" v GUI aplikaci, nebo pomocí terminálu příkazy, např. `chmod` (*change mode*) - pro změnu přístupuvých práv -, `chown` (*change owner*) - pro změnu vlastníka - či `chgrp` (*change group*) - ke změně skupiny souborů.

## Jak probíhá Komunikace mezi moduly/programy, vstup, výstup, roura, příklad jednoduchého předání výstupu na vstup programu v BASHi

V terminálu lze využívat výstup jednoho programu jako vstup pro druhý program, zpravidla se využívá znaku roury (`|`), např. `prvni_program | druhy_program`, kde levá strana od roury je vstup a pravá strana je výstup. Roury je možné používat vícekrát a lze tak docílit vícenásobného efektu předávání dat.  
