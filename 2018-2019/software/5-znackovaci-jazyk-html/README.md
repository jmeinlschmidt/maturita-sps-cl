# 5/25 - Značkovací jazyk HTML
## Zadání
-	Značkovací jazyk HTML

## Vypracováno
- Hyper Text Markup Language
- je značkovací jazyk pro vytváření www stránek
- dnes standard HTML 4.01
- příprava verze 5.0
- standard W3C

xx

- struktura HTML dokumentu (hlavička, tělo)
    - Hlavička
        - `<head></head>`
        - obsahuje metadata vztahující se k dokumentu
            - například: typ kódování, název dokumentace, autora, titulek, scripty, SCC, …
    - Tělo
        - `<body></body>`
        - je v něm obsažen vlastní obsah dokumentu
        - užívají se v něm značky (strukturální, stylistické, popisné)
    - Kořenový element
        - `<html></html>`
        - reprezentuje celý dokument
    - Doctype
        - `<!Doctype HTML …>`
        - je povinný
        - sděluje prohlížeči, že pracuje s HTML dokumentem
    - struktura dokumentu je pevně dána
    - je vhodné pro přehlednost odsazovat o jednu úroveň
- použití vývojového prostředí pro vytváření a úpravu dokumentů
    - Textové editory
        - nejběžnější
        - barevně oddělují jednotlivé části (př, značky, vlastnosti, celý text)
        - mohou mít nápovědu
        - například PSPad, NOTEPAD, prostředí Eclipse
        - mohou poskytovat náhled dokumentu
    - WYSIWYG editory
        - "Co vidíš, to dostaneš"
        - opak textových dokumentů
        - pracujeme s již hotovou stránkou
        - obecné pravidlo => uživatel nemusí znát jazyk HTML
        - můžeme si vytvořit stránku, jakou chceme a program vygeneruje požadovaný HTML kód
        - př. Adobe Dueamweaver nebo Microsoft Expression Web
        - jedná se o sofistikovanější program
        - obecně lze použít jakýkoliv jiný editor pracující s textem
        - parsování => postup zpracování a vykreslení HTML
- základní prvky HTML dokumentu (úrovně nadpisů, odstavec, odkazy, obrázky)
    - jsou značky:
        - Strukturální
            - rozvrhují strukturu HTML dokumentu (př. odstavce nebo nadpisy)
        - Popisné
            - popisují povahu obsahu prvku, částečně sem spadá i XML
            - př. `<title>` nebo `<address>`
        - Stylistické
            - určují vzhled prvku při zobrazení (typický příklad je tučné písmo `<b>`)
            - upouští se od nich na CSS
            - jsou orientovány především pro prohlížení na obrazovce PC => nepočítá se s jiným způsobem použití (př. mobilní zařízení)
    - Úrovně nadpisů
        - `h1` až `h6`
        - jsou mimo hlavní text
        - můžeme nastavit zarovnání pomocí atributu align
    - Odstavec
        - `<p></p>` => párový
        - slouží pro zobrazení textu obsahu stránky
        - opět lze použít align
        - využíváme pro zalomení řádku `<br>`
        - využíván samostatně, čili hlavně v oddílech `<div>`
    - Odkazy
        - odkazy používáme, abychom někam odkázaly
        - třeba na stránku, či jinou část dokumentu
        - značka `<a></a>`
        - atribut href je cíl odkazu (URL), target odkazuje kam uložit, blank je do nového okna, name je jméno záložky
            - href je nejdůležitější
        - `<a href="" … ></a>`
    - Obrázky
        - nepárový, značka `<img src="">`
        - slouží pro vložení obrázku ze souboru
        - můžeme nastavit šířku a výšku
        - atribut src odkazuje na umístění obrázku
        - často pouze gif nebo jpg
        - alt: zobrazí se ve stránce místo nenačteného obrázku (zástupný text: `alt="strom"`)
        - `align`
        - lze nastavit obtékání left nebo right
        - vše kromě src lze nahradit CSS stylem
- stavební prvky HTML dokumentu (zápis elementů a atributů, formátování textu, tabulky, seznamy)
    - definují prvky HTML
    - element je vše od začátku značky do jejího konce: `<a href="" … >`
    - mohou být vnořené: př: `<p>` v `<body>`
    - `<br>` je prázdný element
    - Atributy
        - poskytují další informace o prvcích HTML
        - jsou uvedeny vždy v počáteční značce
        - pár název/hodnota => name="value"
        - př: `<img src="URL" alt="some-text">`
        - hodnoty atributů jsou vždy v `""`
    - Formátování textu
        - zastaralé `<b><i>`
        - jednak nadpisy a odstavce
        - pomocí `<font>` => př: color, size, serif (patkové, TNR, Cambria), san-serif (bezpatkové, arial, verdana)
        - font-families => druh/rodina písma
    - Tabulky
        - `<table>`	– lze nastavit border, barva, …
        - `<tr>`	– řádek
        - `<td>`	– buňka
        - `<th>`	– hlavička
        - `border-collapse` => jednoduchý/dvojitý rámeček
    - Seznamy
        - dělí se na číslované (`<ol>`) a nečíslované (`<ul>`)
        - položky sezamu jsou `<li>`
        - popis seznamu:
            - `<dl>`
            - `<dt>`	– pojmy/jména
            - `<dd>`	– termíny
            - př. káva
		– černý, horký nápoj
```
<dl>
  <dt>První termín</dt>
  <dd>Výklad prvního termínu</dd>
  <dt>Druhý termín</dt>
  <dd>Výklad druhého termínu</dd>
</dl>
```
ss
    - menu, dir
        - zvláštní typy seznamů
    - rozložení stránky (rámy, vnořené rámy)
        - Frame
            - rozdělují stránku na samostatné oblasti
            - jsou odděleny rámečkem
            - načítají se v jednom (menu) a zobrazují ve druhém
            - `<frameset>`	– skupina rámů 
            - `<frame>`		– samostatný rám, nepárový
            - `iframe`		– vložený rám (reklamy), párový
            - nachází se v `head`
            - př:
```
	<html>
		<frameset>
			<frame src="hlavicka.html">
		</frameset>
	</html>
```
ss
        - DIV
            - rozděluje stránku na bloky
            - pro novou stránku je potřeba odkázat na identickou, ale s jiným obsahem
            - nemá žádný zvláštní význam
            - kombinuje se s CSS => barva, odlišení
            - jedná se o tzv. "blokový element"

- HTML barvy
    - kombinace RGB
    - jsou uvedeny v 16 soustavě (#00 00 00)
    - 16 000 000 různých barev, stupně šedi
    - 2 typy zápisů:
a)	#00 00 00	– nejpoužívanější
b)	rgb(0, 0, 0)
    - bezpečné barvy
        - doporučené barvy
        - 216 + 40 systémových barev (zobrazí se stejně ve všech OS)
    - pojmenované barvy
        - př. yellow, blue navy, … => 16 základních windovsáckých
    - zápis:
a)	<font color="red"> červené písmo </font>
b)	backgound-color: …
c)	color: … (u H1, p, …)
    - samostatně pomocí atributů ve značkách (atribut style="color: green;") i v CSS
