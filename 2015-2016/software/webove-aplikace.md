# Webové aplikace

### 1. Co to jsou webové aplikace?

Aplikace, které jsou poskytovány ve webovém prohlížeči.

### 2. Popiště princip funkce webové aplikace typu klient-server?

Klient (prohlížeč uživatele) vykresluje uživatelské prostředí, se kterým může také real-time manipulovat. Server generuje obsah pro klienta a zpracovává další informace, jako např. přihlášení.

### 3. Jaké existují platformy - serverové řešení pro webové aplikace (uveďte tři)?

- PHP
- ASP
- Node.js

### 4. Kdo (jaká aplikace) je klientem u webové aplikace běžící na serveru (uveďte čtyři různé).

- uživatel
- webový prohlížeč
- uživatelská část aplikace
- interpret webového prohlížeče

### 5. Uveďte webové technologie použitelné ve webových aplikacích na straně serveru nebo u klienta.

Na straně klienta:

- jQuery
- Angular
- React

Na straně serveru:

- Nette
- Laravel
- Symfony

### 6. K čemu slouží HTTP u webových aplikací, a popište základní principy fungovaní.

Internetový protokol sloužící pro přenos hypertextových dokumentů. Obvykle využívá port 80. Je bezstavový.

### 7. K čemu slouží HTML u webových aplikací, a popište základní principy fungování.

Značkovací jazyk sloužící pro popis rozložení webové stránky, resp. uživatelského rozhraní aplikace. Webový prohlížeč podle HTML kódu vytvoří DOM a vykreslí se vzhled.

### 8. K čemu slouží CSS u webových aplikací, a popište základní principy fungování.

Stylovací jazyk sloužící pro stylování, pozicování a jinou úpravu elementů. Popisuje vzhled webové stránky, resp. uživatelského rozhraní.

### 9. K čemu lze použít XML u webových aplikací, a popište základní principy fungování.

Využívá se především pro přenos strukturovaných dat ve formě textu. 

### 10. K čemu lze použít SQL u webových aplikací, a popište základní principy fungování.

Využívá se pro práci v databázi obsahující data. Pracuje se pomocí speciálních dotazů, které vrátí požadovaný výsledek.

### 11. K čemu slouží Flash u webovách aplikací.

Dnes již mrtvá technologie. Dříve se využívala na obdobné věci jako Javascript.

### 12. K čemu slouží Javascript u webových aplikací, a popište základní principy fungování.

Využívá se především pro interakci webové stránky. Pomocí Javascriptu lze vytvářet aplikace, nebo její části, které běží přímo v prohlížeči uživatele.

Lze používat také na straně serveru, např. jako Node.js.

### 13. K čemu slouží PHP u webových aplikací, a popište základní principy fungování.

Využívá se pro generování či sestavování uživatelského rozhraní stránek, tj. HTML. 

Pro spuštění PHP souborů je nutný server, který musí být přítomen jak na hostingu, tak i při vývoji v počítači vývojáře.

### 14. Popište části URL adresy (cesta ke skriptu, parametry).

Pokud máme URL adresu této podoby `www.something.com/demo_form.php?name1=value1&name2=value2`, pak:

- `www.something.com` - cesta k webové aplikaci, resp. jejímu hostingu
- `demo_form.php` - soubor s programem pro serverovou část
- `name1=value1&name2=value2` - parametry sloužící pro upřesnění programu

### 15. K čemu slouží ASP u webových aplikací.

Obdoba PHP od Microsoftu. Využívá se pro psaní serverové části aplikace. Lze využívat .NET jazyků, jako např. C# nebo VB. 

### 16. Uveďte frameworky, které lze použít na serverové části web. aplikace a související technologie.

Pro PHP lze využívat např. následující frameworky:

- Nette - český produkt
- Laravel
- Symfony

### 17. K čemu slouží jQuery u webových aplikací, a popište základní principy fungování.

Slouží pro jednoduché selektování elementů webové stránky, podobně jako v CSS, a další práci s nimi. Umožňuje např. jednoduše přidávat třídu či měnit hodnoty atributů.

### 18. K čemu slouží jQuery UI, jQuery Mobile, Sizzle, QUnit u webových aplikací.

- jQuery UI - hotová řešení, např. přepínání tabů
- jQuery Mobile - pro mobily
- Sizzel - selektování v javascriptu pomocí CSS selektorů
- QUnit - testování správné funkčnosti aplikace

### 19. Zakreslete diagram webové aplikace (strana klient a server) a použití jednotlivých technologií.

**TODO**

### 20. Vysvětlete princip fungování webové aplikace typu klient-server.

Spustíme webovou aplikací zadáním URL, to přesměruje prohlížeč na server, který zachytí požadavek a vrátí vygenerovaná data (nejčastěji sestavenou webovou stránku), podle HTML se vytvoří DOM a vykreslí se stránka.

Jelikož je HTTP (protokol využívající se na dotazování serveru) bezstavový, všechny informace se musí získávat znovu, nebo musí být ukládány v cookies (na straně klienta) nebo v sessions (na straně serveru).

### 21. Jaké technologie zvolíte, pokud chcete vytvořit webovou aplikaci bez nutnosti serverové části.

Pro aplikace bez serverové části se musí využít Javascript. Vhodné je využití frameworků ulehčující správu a chování aplikace jako např. Angular 2.

Často se také využívá preprocesorů, tj. jazyků, které mají vylepšenou syntaxi, ale pro spuštění ve webovém prohlížeči se musí zkompilovat do čistého Javascriptu. 

### 22. Uveďte dva typy požadavků, kterými se dají serveru odeslat data a v čem se liší?

- HTTP požadavek, při kterém se stránka přesměruje a je tedy nutné ji znovu načíst.
- AJAX - technologie, kdy je možné poslat dotaz (z Javascriptu) na server, a následně zpracovat informace bez nutnosti znovunačtení stránky.

### 23. Popište, jak funguje požadavet typu GET a jak jsou předávány data serveru?

Požadavek se přenáší pomocí URL adresy a je omezen zhruba na 2000 znaků. Parametry jsou viditelné, a tedy se ukládají např. do historie procházení v prohlížeči.

### 24. Popište, jak funguje požadavek typu POST a jak mohou být předány data serveru?

Požadavek se přenáší samostaně a není součástí URL. Parametry jsou skryté a neukládají se.

### 25. Co je to AJAX a jaké je využití u webových aplikací?

Ajax je technolige, která využívá dotazování ze strany Javascriptu bez nutnosti znovunačítání stránky. Využívá se pro interaktivní aplikace, které potřebují získat informace ze serveru, ale není vhodné překreslovat celou stránku.

### 26. K čemu slouží Nette Framework u webových aplikací, a popište základní principy fungování.

Slouží pro rychlé a bezpečnější vytváření webových aplikací. Je založen na MVC modelu. Má možnost generovat data v útržkách šablony a zajistit tak jednoduchou modifikaci.

### 27. Jaké jsou výhody aplikací vytvořených za pomoci Nette Frameworku?

Aplikace je jednoduchá a rychlá. Nette je open source, a tedy může každý najít chybu nebo doplnit novou funkcionalitu.

### 28. Jaká je obecně URL adresa úvodní stránky projektu v Nette Frameworku a uveďte příklad.

Úvodní adresa stránky je cesta k `www` složce na localhostu, např. tedy `localhost/muj_project/www`.

### 29. Nette - co to je sandbox, co se nachází ve složkách `app`, `vendor`, `log`, `temp` a `www`?

- sandbox - kostra projektu, výchozí struktura
- app – kód pro danou aplikaci
- vendor – externí knihovny
- log – chybové hlášky
- temp – dočasné soubory
- www – kořenová složka aplikace

### 30. Nette - v jakých souborech nastavujeme konfiguraci projektu a kde jsou tyto soubory umístěny?

konfigurace se nachází v konfiguračních souborech `config.local.neon` a `config.neon` umístěných ve složce `app/config/`.

### 31. Nette - k čemu slouží Tracy, kde nastavujeme ukládání chyb v aplikaci do logovacích souborů?

Slouží pro hledání a debugování chyb. Lze nastavit pomocí `SetDebugMode` v souboru `bootstrap.php`.

### 32. Nette - popište části návrhového vzoru MVC.

- model - práce s daty; samotný program a funkce aplikace
- view - vykreslování šablon
- controller - řídí průchod aplikací

### 33. Nette - jaký nástroj lze použít pro vytvoření a úpravu databáze v prostředí Nette a jeho URL?

Nette je poskytováno s programem Adminer, nacházející se v `www/adminer/`.

### 34. Nette - v jakém souboru a jaké údaje nastavíme, abychom konfigurovali připojení k databázi?

V `config.local.neon` nastavíme následující údaje:

- `dns` - adresa db serveru a jméno databáze
- `user` - uživatel
- `pass` - heslo

### 35. Nette - co je to `Presenter`, `HomepagePresenter`, k čemu slouží a od čeho je odvozen?

Je třída, který propojuje Model a View.

`HomepagePresenter` je třída odvozená od `BasePresenter`.

### 36. Nette - jakou třídu lze použít v Nette pro práci s databází?

Lze využít `Nette/Database/Context`.

### 37. Nette - k čemu slouží metoda renderDefault() a kdy je tato metoda zavolána Frameworkem?

Je metoda, který získá data a vloží je do šablony `default.latte`, je zavolána po otevření URL s názvem presenteru, např. `homepage/` otevře `default.latte` pro Homepage.

### 38. Nette - co to je šablona (co obsahuje), k čemu slouží a jakou koncovku mají soubory šablon?

Je soubor, který obsahuje HTML kód (většinou s latte syntaxí) a je využíván pro sestavení webové stránky.

### 39. Nette - v jaké složce nalezneme hlavní šablonu s rozložení stránky a jak se tato šablona jmenuje?

Ve složce `app/templates/`, kde je soubor `@layout.latte`.

### 40. Nette - k čemu slouží makra `include`, `block`, `foreach`, `link` v šablonách?

- `include` – vkládá definované bloky
- `block` – blok pro umístění do šablony
- `foreach` – umožní procházet data proměnné
- `link` – chytré vytváření odkazu

### 41. Nette - jak vytvoři v šabloně odkaz na domovskou stránku aplikace (`HomepagePresenter`)?

```latte
<a n:href="Presenter:akce">...</a>
```

### 42. Nette - jak zkontrolovat, zda záznam se zadaným primárním klíčem v databázi existuje?

Lze zkontrolovat pokusem o načtění v podmínce, po které se vykonají náležíté akce.

### 43. Nette - jakým názvem začínají metody, které vytváření formuláře v Presenteru? Uveďte příklad.

Např. `createComponent(ComentarForm);`.

### 44. Nette - jak nastavíme metodu, která se má spustit při odesílání formuláře?

Přidáme hodnotu do pole formuláře `onSuccess`, např. `$form->onSuccess[] = $this->nazevMetody;`.

### 45. Nette - pomocí jaké metody jakého objektu (kde?) dochází k přesměrování na jinou stránku?

Pomocí metody `redirect()` daného presentéru s parametrem ve tvaru chytré Nette adresy dojde k přesměrování. Např. `$this->redirect("Homepage:");`;

### 46. Nette - jak do projektu vložit přihlašování, jak zabezpečit aplikaci a skrýt odkazy nepřihlášeným.

Do konfiguračního souboru `config.neon` je nutné vložit `security: users: admin: secret` (uživatel `admin` s heslem `secret`). Dále je nutné vytvořit presentér pro přihlášení a případně vytvořit i podmíněné odkazy v šablony pro ne/přihlášeného uživatele, např.

```latte
{if $user->loggedIn}
  <a n:href="Post:create">Editovat příspěvek</a>
{/if}
```
