# 20/25 - GNU/Linux – struktura, zavádění OS
## Zadání
-	GNU/Linux – struktura, zavádění OS
- Význam OS, Informační systém, druhy OS, LIVE systémy
    - multiuživatelské systémy
- Struktura OS Windows/Linux
    - jádro – složení, fukce
    - privilegovaný/neprivilegovaný režim
    - vrstvy OS, správa:
        - pamět, rozdělení, FAP,LAP, swap, systémové prostředky
        - souborové systémy – rozdělení, popis, vlastnosti
            - přístupová práva (adresáře, soubory, kvóty)
            - typy souborů v OS
            - adresářová struktura OS (významné adresáře W/L) 
    - procesy, 
    - komunikace
    - GUI, CLI/CMD
    - základní systémový SW pro správu OS

## Vypracováno

### 1. Úvod

#### 1.1 Význam OS

Základní funkce
1. ovládání PC
2. abstrakce HW (rozhraní pro programy)
3. správa prostředků / systémových zdrojů a přidělování (RAM, CPU, prostor na disku atd.)

#### 1.2 Počítačový systém

Základní části
1. hardware (zdroje - resources)
2. software
    - operační systém
    - aplikační programy
3. uživatelé (nejslabší článek)

#### 1.3 Multitasking (multiúlohové OS)

Je to souběžný běh více programů
1. skutečný multitasking - více CPU, vykonávají úlohy nezávisle na sobě
2. preemptivní (přerušovaný) multitasking - rychlá, přerušovaná činnost jednoho CPU

#### 1.4 Multiuživatelské systémy (multi-user OS)

Více uživatelů na 1 PC
- každý má svůj profil
- vlastní místo na disku

#### 1.5 Druhy OS

- Desktop
- Mobilní zařízení
- Servery
- Live systémy (v reálném čase)
    - pro řízení strojů atd.
    - velmi rychlé reakce
    
### 2. Jádro

#### 2.1 Složení

Čím lehčí jádro, tím rychlejší, menší atd.

Kernel (jádro)
- vykonává neustále dokola instrukce v privilegovaném režimu (*= chráněném režimu*)
- kontroluje např.
    - stav procesoru
    - stav paměti
    - stav I/O operací
    - stav a požadavky IRQ (* = Interrupt Request*)
    - stav a přidělování strojového času jednotlivým úlohám
    - vyhodnocuje jejich prioritu a může ji měnit
- stavy procesů
    - běžící (je mu přidělen strojový čas)
    - připravený (zatím mu nebyl přidělen strojový čas)
    - čekající (spící, blokovaný nebo čeká na spouštěcí událost)
- poskytuje API (DirectX, OpenGL)
- označené jako **ring 0** (*= plný přístup k hardwaru, **privilegovaný režim***), ostatní programy mají ring > 0 (**neprivilegovaný režim**), pro přístup musí žádat jádro
- jádro v adresáři `/boot`
- druhy jader
    - monolitické jádro (ovladače zakomponovány do jednoho celku)
    - modulární jádro (ovladače v modulech, lze přímo za běhu vyndavat a přidávat)
    - **jádro linuxu - něco mezi, umožňuje vkládat moduly**


### 3. Souborový systém

#### 3.1 Pravidla pro ukládání souborů na pevný disk
- kde na pevném disku je soubor uložen
- jak se jmenuje a v jakém adresáři
- kdo má jaká přístupová práva
- každý oddíl musí mít vlastní souborový systém

#### 3.2 Kořenový adresář
- `/` root adresář (pouze jeden)
- `/boot` obsahuje jádro `vmlinuz-xxx` a GRUB - zavaděč (boot loader) pro GNU/Linux
- `/bin` základní spustitelné soubory nutné pro běh systému, pouze čtení (root může)
- `/sbin` systémové spustitelné soubory
- `/etc` obdoba registrů, ASCII textové konfigurační soubory
- `/lib` knihovny (*jako DLL ve Windows*)
- `/lib/modules` moduly pro kernel
- `/root` domovský adresář roota
- `/dev` seznam všech dostupných zařízení a soubory jak se k nim má OS připojit
    - myši
    - klávesnice
    - dvd
    - usb
    - cd/ďvd
    - konzole
    - tiskárny atd.
- `/media` přímá vazba k `/dev` - zobrazuje obsah zařízení (soubory)
- `/mnt` slouží k připojení diskových oddílů jiných OS
- `/tmp` adresář temp, při restartu se vymaže, může být v RAM
- `/proc` RAM disk, obsahuje informace o OS
    - procesy
    - HW
    - přerušení, moduly, paměti
    - aktuální stav
- `/var` proměnná data specifická pro každý systém
- `/var/log` logovací soubory jádra, systémových a ostatních programů
- `/usr` programové balíčky, aplikace
- `/home` domovské adresáře uživatelů

#### 3.3 Značení
- `/` root
- `.` aktuální adresář
- `..` nadřazený adresář
- `~` tilda - domovský adresář

#### 3.4 Rozdělení
1. tradiční souborové systémy
2. žurnálovací souborové systémy
3. síťové souborové systémy
4. virtuální souborový systém

Tradiční souborové systémy (bez žurnálování)
- `ext2` - běžný souborový systém linuxu
- `minix` - první souborový systém podporovaný linuxem
- `MS-DOS/VFAT` - souborový systém MS-DOS (FAT16, FAT32)
- `exFat` - 64-bit verze FAT (z roku 2009)
- `ISO9660` - souborový systém CD-ROM

Žurnálovací souborové systémy
- ukládání probíha ve 3 krocích
    1. nejprve OS zapíše do žurnálu, co bude ukládat
    2. pak uloží metadata na disk
    3. po úspěšném zápisu vymaže záznam ze žurnálu
- výhoda při pádu - stav je zapsán v žurnálu, lze tak pokračovat v zápisu
- `ext3` - plně kompatibilní s `ext2`
- `ext4` - nové funkce oproti `ext3`, kompatibilní
- `ReiserFS` - zahrnut v linuxovém jádře od roku 2001, lepší práce s malými soubory
- `NTFS` - souborový systém Windows

Síťové souborové systémy
- `NFS` (Sun)
- `SMB` (Windows) - slouží ke sdílenému přístupu
    - soubory
    - tiskárny
    - sériové porty atd.
    
Virtuální souborové systémy
- abstraktní vrstva nad konkrétními FS
- cílem poskytnout aplikacím stejný přístup k různým souborovém systémům
- prováděno prostřednictvím jednotného API

#### 3.5 Soubory Linuxu
- obyčejný soubor
    - rozlišují se velká a malá písmena
    - `.soubor` skrytý soubor
- adresář (v terminologii Windows - *složka*)
    - **seznam adresářů a souborů které obsahuje**
- symbolický odkaz
    - odkaz na jiný soubor, řeší jádro linuxu
    - smazání, kopírovaní, změna se dotkne pouze odkazu, nikoli původního souboru
- pevný odkaz
    - stejný jako symbolický, ale smazáním se smaže i původní soubor
- znakové zařízení
    - práce s nimi je zachycena jádrem
    - komunikují po znacích - USB, tiskárna, scanner, klávesnice atd.
- blokové zařízení
    - práce s nimi je zachycena jádrem
    - komunikují po blocích (*např. přečti ten a ten sektor*)
    - HDD, CD/DVD atd.
- pojmenovaná roura (pipe)
    - způsob jakým si procesy předávají informace
    - výskyt v `/tmp`
- socket
    - soubor reprezentující síťové spojení

#### 3.6 Symbolika znakových zařízení
- konzole
    - `/dev/console` skutečná konzole
    - `/dev/tty` virtuální konzole
        - `/dev/tty1` první virtuální konzole
        - `/dev/tty2` druhá virtuální konzole
    
Symbolika blokových zařízení
- IDE zařízení
    - `/dev/hda` zařízení na prvním řadiči
        - `/dev/hda1` první oddíl
        - `/dev/hda2` druhý oddíl
    - `/dev/hdb` zařízení na druhém řadiči
- SATA zařízení na prvním řadiči
    - `/dev/sda`
        - `/dev/sda1` první oddíl
        - `/dev/sda2` druhý oddíl
    - `/dev/sdb` zařízení na druhém řadiči
- CD mechaniky
    - `/dev/scd0`
    - `/dev/scd1`

#### 3.7 Přístupová práva
- každý uživatel unikátní `UID`
- každá skupina unikátní `GID`
- soubor v linuxu patří uživateli, který jej vytvořil (vlastnictví se dá změnit)
- soubor v linuxu náleží ke skupině, kde je i uživatel (skupina lze taky změnit)
- ostatní atributy souboru
    - datum a čas vytvoření/změny
    - vlastník UID, skupina GID
    - uživatelská práva

Uživatelská práva
1. čtení - `r` **4**
2. zápis - `w` **2**
3. spouštění (vstup do adresáře) - `x` **1**

Definují se zvlášť pro
1. uživatele
2. skupinu
3. ostatní

`-rw-rw-r-- 1 harrach ahoj 482503 zář 14 23:14:59 vystup.pdf`

- `-` mód souboru
    - `-` normální soubor
    - `d` adresář
    - `c` znakové zařízení
    - `b` blokové zařízení
    - `l` symbolický odkaz
- `rw-rw-r--` přístupová práva
- `1` počet odkazů na soubor
- `harrach` uživatel (vlastník)
- `ahoj` skupina
- `482503` velikost v bytech
- zbytek datum zmeny a nazev

```
Příklad
755

Vlastník může vše, ostatní pouze čtení a spouštění atd.
```

- `chmod` change mode
- `chown` change owner
- `chgrp` change group

#### 3.8 Uživatelé a skupiny
- adresář `/home`, vše ostatní velmi omezený přístup
- `/etc/passwd` login, uid, gid, jméno uživatele, adresář atd.
- `/etc/shadow` zahashovaná hesla
- `/etc/group` informace o skupinách, kdo kam patří
- vykonání příkazu s právy roota
    - `sudo`
    - `su`
- `adduser <uzivatel>` přidání uživatele
- `deluser <uzivatel>` odebrání uživatele
- `addgroup <skupina>` přidání skupiny
- `delgroup <skupina>` odebrání skupiny
- `adduser <uzivatel> <skupina>` přidání uživatele do skupiny
- `cat /etc/group | grep <uzivatel>` zjištení, v jaké skupině je uživatel (pipe - roura)

### 4. Paměť

#### 4.1 Rozdělení
1. **FAP** - fyzický adresní prostor (fyzická operační paměť)
2. **LAP** - logický adresní prostor (obohacený o **SWAP**)
    - buď samostatný oddíl (např. některé distribuce Linuxu, rychlejší)
    - nebo soubor (např. Windows)
    
#### 4.2 Práce s paměti
- démon `kswapd`
- je-li proces dlouho neaktivní, přesune z RAM do swapu
- pokročilá činnost
    - vytvoření swapu mkswap `/dev/hda3`
    - používání swapu swapon `/dev/hda3`
    - vypnutí swapu swapoff `/dev/hda3`
- jinak OS proces sestřelí

### 5. Procesy
- identifikovány PID
- rodičem všech procesů je `/sbin/init` (PID 1, je zodpovědný za nastartováni celého systému)
- procesy řídí jádro (přiděluje čas a systémové prostředky)
- čas CPU - podle `niceness` (slušnost)
    - nabývá hodnot od -20 do 19
    - -20 = nejvíce času CPU
- jen root může procesům nastavit méně než 0

#### 5.1 Signály
- mění chování procesů
- `TERM` (požádá o vypnutí)
- `KILL` (bez milosti sestřelí proces)

#### 5.2 Démoni
- procesy běžící na pozadí
- uživatel je nemá pod kontrolou
- konfigurační soubory zpravidla v `/etc/init.d`

### 6. GUI a CLI
- GUI pro GNU/Linux - unixový standard X Windows System
    - označení `X11` nebo `X`
    - X Server obsahuje X klienty
    - **nezávislé komponenty**
        - X Server (pouze X Server má přístup k ovladačům grafiky)
        - knihovna Xlib
        - **WindowManager (X klient)**, programy přes něj posílají své požadavky
    - spadne-li X Server, je k dispozici pouze příkazová řádka
    - X Server je možné znovu spustit
    
#### 6.1 Volby grafického prostředí
- dle HW slabší PC (tj. jednoduché prostředí) nebo naopak (3D prostředí)
- typy GUI
    - KDE 4, KDE 3 (TDE) - 3D grafika, efekty, HW náročnější
    - GNOME 3, GNOME 2, Classic - přívětivé prostředí
    - Unity (nadstavbe Ubuntu) - nový kabát
    - xfce, lxde - *minimální nároky na HW*
    
### 7. Komunikace (síťové prostředí)
Využívá se i na počítači, kde není žádné internetové připojení, přes tzv. loopback `127.0.0.1`
- data neopustí počítač
- pro mnoho programů naprosto nezbytné

#### 7.1 Druhy připojení
- ethernet
    - identifikujeme `ethX` (např. `eth0`)
    - nastavujeme `ifconfig` a `route`
- wifi 
    - identifikujeme `wlanX` (např. `wlan0`)
    - nastavujeme `iwconfig`


#### 7.2 Servery
- naslouchají na portech
- konfigurujeme `/etc/init.d`
- potřeba nastavit firewall

### 8. Základní SW pro správu OS

#### 8.1 Správce balíčků
- package manager
- jeden program může mít více balíčků (dependencies, závislosti)
- Debian - Advanced Packaging Tool - `apt-get` nebo `apt`
- `apt-get update`
- `apt-get install`
- `apt-get remove`
- `apt-get upgrade`

### 9. Zavádění GNU/Linux
1. zapnutí PC
    - BIOS/UEFI - diagnostika HW, kontrola periferií
    - načte bootloader (zavaděč) v MBR (512 B)
2. bootloader GNU/Linux
    - vejde-li se do MBR, název **LILO** (Linux Loader)
    - pokud se nevejde - bootloader pouze odkáže na místo na disku
        - hlavní zaváděcí program GRUB
        - načte do paměti a spustí
3. kernel
    - detekuje hardware
    - připojí root adresář
    - spustí program `/sbin/init`
    - z `/etc/inittab` zjistí, jaký runlevel spustit
4. run levely
    - startovací skripty
    - určují které služby sputit
    - `/etc/rcX.d` (X - číslo run levelu)
    - obsahuje symbolické odkazy na `/etc/init.d`
    - GNU/Linux celkem 6 bootovacích úrovní běhu
        - `0` vypnutí počítače
        - `1` jednouživatelský systém
        - `2-5` individuální dle distribuce
        - `6` restart počítače
