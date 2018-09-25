# Bezpečnost: Ochrana OS

## Popište základní principy účelného odvirování počítače

Odstranit nepotřebné dočasné soubory, odinstalovat nepotřebný nebo podezřelý SW(může se jednat o samotný vir. Odstranit systém: body obnovení nebo je zpřístupnit antiviru. Nahrát 100% nezavirovaný OS

Pomocí Live CD/USB můžeme nabootovat LiveLinux a v tom to odstranit

V TotalCMD dáme změna atributů a tam odznačit atributy ochrany a odznačit i soubory v podadresářích.

### Jaký je důvod použití Live CD/USB   

Při potencionálně napadeném systému, nebo nefunkčním systému, je dobré využít live CD/USB, které může procházet systém v plném rozsahu a není prakticky ničím omezován. 

### Jak zpřístupníme soubory Systému bodu obnovení pro odvirování

### Popište základní kroky přípravy počítače před vlastním odvirováním – důvod

## Linux: Firewall – vysvětlete princip, základní druhy

Firewall je brána, která chrání počítač před nebezpečím z internetu. Tvoří bariéru před veřejnou sítí internetu a soukromým počítačovým systémem. Není zárukou bezpečnosti, ale je první obrannou linií.

### Popište Netfilter/IPtables

**Netfilter** je framework obsažený v jádře Linuxu nabízející mnoho možností při filtrování paketů a nebo překladu síťových adres (NAT).

**IPtables** je nástroj v Linuxu, který slouží pro nastavování pravidel firewallu v jádře.

### Popište princip Ukládání pravidel pro firewall - typy řetězců     

### K čemu slouží Tabulky filter, nat, mandy - význam 

## Vysvětlete termín Standardní politika INPUT, FORWARD, OUTPUT, příklad změny standardní politiky – BASH (CLI), Základní příkazy/akce pro práci s pravidly iptables, logování v iptables, popis, význam

**INPUT** - upravuje pakety pro místní počítače. Zpracovává příchozí pakety.

**FORWARD** - zpracovává pakety směrované přes zařízení. Zpracovává pakety procházející přes zařízení.

**OUTPUT** - upravuje lokálně vytvořené pakety před jejich směrováním. Zpracovává odchozí pakety.

## Jak pracuje antivirový software, význam pravidelné aktualizace virových databází, antivirová ochrana Microsoft Windows, další freeware/proprietární antivirové programy

Antivirový software skenuje a vyhledává potencionálně nebezpečný software, hledá vzory chování typické pro známé viry, kontroluje editované soubory atp. 

## Jak pracuje ochrana UAC – popis, výhody, omezení 

UAC je bezpečnostní technologie, která omezuje oprávnění aplikace na úroveň uživatele, dokud administrátor nepotvrdí zvýšení práv aplikace.

Kdykoliv chce nějaký program provést změnu PC tento nástroj nás upozorní a požádá o povolení. Ve výchozím nastavení je upozorňováno na každou změnu. Lze nastavin: Upozornit pokaždé, Upozornit, když se aplikace pokusí o změnu v PC, nebo i Nikdy.

Výhodou je zvýšení zabezpečení systému na úkor "otravování" uživatele s povolením.
