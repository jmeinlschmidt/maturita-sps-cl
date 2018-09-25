# Bezpečnost: Záloha a obnova dat

## Popište Význam zálohování dat - základní příčiny ztráty dat, rozdělení

Zálohování dat provádím z toho důvodu, kdyby se něco stalo s tím souborem/oddílem, kde mám uložené důležité informace, abych o ně nepřišel. Příčina: opotřebení, vyhoření, hacker(vir) Zálohování se dá rozdělit do dvou skupin: zálohování celých disků nebo oddílů a zálohování souborů a složek.

### Jaké znáte Základní rozdělení a výběry typu záloh

### Popište Zálohování lokálního počítače – zálohovací média, typy, výhody/nevýhody 

### Popište Firemní zálohování serverů – zálohovací média, rozdělení, výhody/nevýhody

## Vysvětlete termín Zálohovací cykly – firemní zálohování 

### Základní týdenní strategie – popis   

### Základní roční strategie – popis

## Popište Zálohovací SW – co jsou to kompletní zálohy, význam

### Popište Způsob vytvoření a obnovy OS z bitového obrazu disku, Rescue CD/USB 

Postupuje se jako při instalaci. Zvolí se možnost Opravit tento počítač, kde lze vybrat obnovu ze zálohy a systém prohledá všechny dostupné lokální pevné disky a pokusí se sehnat informace o uložených bitových kopiích.

### Které znáte Integrované nástroje operačních systémů (Windows/Linux)  

### Jaké znáte GNU/proprietární zálohovací software 3. stran 

Pro zálohování, resp. přímo verzování, je vhodné použít Git, což je nejpoužívanější software pro zálohování a verzování především při vývoji programů.

## Vysvětlete a popište termín Strategie odděleného zálohování OS a uživatelských dat – řešení v GNU/Linux, Windows, význam, výhody

## Windows7/8: vysvětlete termíny diskové oddíly, Rescue oddíl, význam, použití; adresář User, popis, význam, možnosti přesměrování adresáře na jiný diskový oddíl 

## Jak provádíme Ruční/automatickou zálohu dat – rozdíly, výhody/nevýhody, využití programu MS Sheduler, Cron/GNU Linux

Automatická záloha dat využívá programů, které automaticky verzují data, kdežto ruční záloha dat zpočívá v kopírování souborů s daty na zálohovací médium či místo.

Automatické zálohovací metody mají mnoho výhod, ať už jen pravidelné a automatické (tzn. nemusím nic dělat, udělá se to samo) zálohování či verzování.

## Vyjmenujte hlavní rizika poškození nebo ztráty dat

Hlavní rizika poškození nebo ztráty dat je právě ztráta informací, která jsou uloženy v datech. Data je vhodné zálohovat nejrůznějšími metodami, zejména zálohováním na cloud servery jako Dropbox, Mega nebo Google Disk, kde je větší jistota, že data zůstanou neporušena. 

Je vhodné také zálohovat na flash disk či CD při každé velké úpravě dat.

### Stručnou Definice škodlivého software

Škodlivý program je takový program, který se chová mimo očekávání uživatele, tj. např. krade, maže, nahrává, stahuje... data.

### Vysvětlete Princip základní integrované ochrany OS Linux/Windows (root/administrátor) – rizika administrátorských účtů, UAC - windows

**UAC** je bezpečnostní technologie, která zvyčuje bezpečnost omezením oprávnění aplikacím na úroveň uživatele, dokud administrátor nepotvrdí zvýšení práv aplikace. 

Tento nástroj nás také upozorní kdykoli chce program provést změnu v PC.

### Popište SW ochranu – firewall/antivirové programy, rozdíl, použití

Antivirové systémy slouží pro identifikaci, odstranění a eliminaci PC virů a jiného škodlivého SW.

Nejpoužívanějšími a nezjznámějšími programy jsou **Avast!**, **AVG**, **McAfee** a **ESET**. Všechny programy se liší schopností identifikovat e eliminovat škodlivé SW, což závisí především na databázi virů a aplikovaném algoritmu.

### Jaký je význam funkčního systému Windows Update

Windows Update přináší bezpečností záplaty, vylepšení systému atp. Je vhodné jej používat, protože odbourává (nebo by alespoň měl) potencionálně slabá místa systému.
