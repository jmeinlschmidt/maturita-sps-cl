# 2/25 - Tabulkové procesory
## Zadání
-	Tabulkové procesory

## Vypracováno
- je program, který zpracovává informace obsažené v tabulce -> jedná se o matici
- v jednotlivých tabulkách mohou být uložena data či vzorce pro práci s těmito daty
- dnes se využívají hodně v kancelářských balících (př. Excell)
- zprvu zejména pro finanční operace, ale dnes pro široké množství výpočtů
- nejrozšířenější je Excell a Calc

xxx

- Prostředí tabulkového procesoru
    - prostředí je obdobné jako u textového
        - obsahuje hlavní nabídku, panely nástrojů, …
    - soubor se skládá ze sešitu, který obsahuje několik listů
        - listy lze libovolně odstraňovat, přidávat, přejmenovávat
        - pomocí těchto záložek můžeme v sešitu listovat
        - dokument může mít obvykle i více než 255 listů
        - listy jsou rozděleny na buňky
    - základem prostředí a jeho hlavní složkou jsou buňky
        - ty jsou uspořádány do řádků (označeny čísly) a sloupců (označeny písmeny)
        - každá buňka má své označení
        - nachází se zde i záložka pro zadávání vzorců
    - z informací uložených v buňkách může být zhotoven graf

 

- Základní operace s buňkami
    - buňky můžeme formátovat
    - základní operací je zapsat do ní hodnotu –> editace buňky
    - další operací jsou vzorce
    - výběr řádku/sloupce
        - CTRL + myš –> nespojitá oblast => výběr více buněk s jiným umístěním
        - SHIFT + myš –> spojitá oblast => výběr buněk (těstě u sebe)
    - kopírování –> zkopíruje formát i obsah buňky
    - buňky můžeme slučovat

- Formát buňky (ohraničení, zarovnání, hodnota)
    - Ohraničení
        - můžeme nastavit rámeček buňky nebo skupiny kuněk
        - používáme pro oddělení, ale hlavně pro zvýraznění
        - využíváme k tomu buď panel pro rychlý přístup, nebo Formát Buňky – Ohraničení
    - Zarovnání
        - užíváme pro zarovnání obsahu buněk
        - můžeme nastavit zalomení textu, jeho přizpůsobení k buňce, …
        - můžeme nastavit směr textu
        - jeho zarovnání – vodorovně, svisle
        - pomocí Formát buněk – Zarovnání, nebo rychlý přístup na panelu
    - Hodnota
        - umožňuje nastavit datový ty hodnoty, který je v buňce uložen
        - obecný	– zápis ve stavu, v jakém byl do tabulky zapsán
        - čísl    - – lze nastavit počet des. míst, oddělení tisíců mezerou, záorná čísla 		   červeně atd.
        - měna	– podobně jako číslo, ale zde je možno nastavit symbol měny
        - datum	– nastavuje g´formát data
        - čas		– nastavuje formát času
        - procenta	– přidá znak % a zvýší řád čísla o 100 (vynásobí)
        - text
        - vlastní	– definuje dle vlastní potřeby
        - matematický – zobrazuje velká čísla pomcí zkráceného zápisu (př. 1,53E+05)

- Definice řady
    - stačí napsat několik čísel řady a roztáhnout –> program řadu vyhodnotí, odvodí vzorec a vypíše námi požadovaný počet dalších členů

- Vzorce a funkce 
    - Vzorce
        - nejzákladnější vzorec je řada: stačí napsat několik čísel řady a roztáhnout –> program řadu vyhodnotí, odvodí vzorec a vypíše námi požadovaný počet dalších členů
        - vzorce také můžeme definovat přímo pro buňku
        - zápis vzorce se ukončí ENTERem
    - Funkce
        - jsou předem definované výpočty, které lze ve vzorcích používat
        - jméno funkce (atgument) –> argument je většinou vložená oblast (myší nebo ročně pomocí rozmezí adres)
        - příkladem funkce
            - SUMA()	– sečte čísla ve sloupci
            - PRŮMĚR()	 – vypočte aritmetický průměr
            - MIN()	– zjistí nejmenší hodnotu
            - RANK()	– vrací pořadové číslo položky seznamu
            - jsou i funkce pro vložení data, času

- Podmínka KDYŽ
    - užívá se v logických funkcích, při testování hodnot a vzorců, je možno ji vnořovat
    - podmínka –> proveď stanovenou akci v opačném případě proveď jinou akci
    - zadává s pomocí Vložit funkci – Když
        - Když(podmínka;A;B)	– A se zapíše, když je podmínka splněna, jinak se zapíše B
        - př.  =KDYŽ(A2<=100;"V rámci rozpočtu";"rozpočet překročen")
            - Pokud je číslo rovno nebo menší 100 zobrazí se text V rámci rozpočetu. Když ne, zobrazí se v Rozpočet překročen

- Podmíněné formátování
    - používá se pro formátování pomocí podmínky
    - podmínky lze nastavit až tři
    - př. pokud je hodnota buňky určité hodnoty/rozsahu –> nastaví se předem určený formát
        - nastaví se barva písma, ohraničení a podkladu, typ písma, velikost
 

- Kopírování vzorce
    - vzorec kopírujeme metou CTRL+C a následně ho vložíme do požadované buňky

- Absolutní a relativní adresování
    - používá se například pro práci se vzorci –> adresy buněk
    - Absolutní
        - adresa se definuje bez možnosti jakékoliv pozdější automatické změny
        - spočívá v příznaku $ 
            - pokud sloupce –> $A3
            - pokud řádek –> A$3
            - sloupec i řádek –> $A$3
    - Relativní
        - adresy/odkazy na buňky se mění podle toho, jak se mění samotná buňka
        - pokud buňka kam vzorce odkazují přesuneme jinam, automaticky se na ní definují všechny odkazy

- Grafy a jejich úpravy
    - slouží nám pro grafické zobrazení hodnot
    - vytvoříme je tak, že označíme tabulku do bloku, a klikneme na tlačítko graf, nebo přes Vytvořit –> Graf => otevře se nám průvodce grafem
    - můžeme si vybrat jaký typ grafu chceme
    - definujeme, co bude na vodorovné ose a co na svislé –> jaký sloupec hodnot
        - přes vybrat data –> přidat
    - Úpravy:
        - můžeme změnit styl grafu
        - úpravu nadpisu a názvů os
        - měnit barvy
        - upravit legendu
        - popisky a hodnoty gryfu

- Práce s listy, zámky, propojení
    - Listy
        - tvoří sešit, což je celý soubor –> standard jsou 3
        - listy lze libovolně odstraňovat, přidávat, přejmenovávat
        - pomocí těchto záložek můžeme v sešitu listovat
        - dokument může mít obvykle i více než 255 listů
        - listy jsou rozděleny na buňky
    - Zámky
        - používáme třeba, když nechceme, aby se obsah buňky nedal změnit
        - nastavujeme na dané záložce, ale projeví se až po uzamknutí listu: Revize –> Změny –> Uzamknout list/sešit –> Heslo
        - lze nastavit i skrytí vzorců => nastaví se akce, které uživatel může provádět
            - heslo zakáže uživateli tyto operace provádět
        - např. když vytváříme dokument pro jiné uživatele
    - Propojení
        - slouží k propojení částí dokumentů/sešitů
        - Sešitů
            - př, když chceme vložit hodnoty z 1 do 2.
            - vybereme buňku v jiném sešitu, zkopírujeme (CTRL+C)
            - v našem sešitu vložíme propojení  
        - Listů
            - tvorba vzorce pomocí myši (= a klik do jiného listu)
            - tvorba vzorce Ctrl+C, pak Vložit jinak–>Propojení

- Předtisková příprava
    - nástroj Náhled před tiskem –> Vzhled stránky
    - kontrola nastavení a rozmístění jednotlivých prvků na listu
        - vzhled stránky – formát, okraje
    - pomocí Oblast tisku vybereme jen políčka, která chceme tisknout (lze zadat přímo, nebo vybrat)
    - můžeme přidat hlavičku v případě rozsáhlých tabulek –> Opakovat řádky
    - dobré předem zkontrolovat, zda bude tabulka čitelná
    - nutné i být na listu, ze kterého chceme tisknout
    - sekce Tisk:
        - zde nás zajímá počet kopií
        - jaké stránky chceme tisknout
        - vybrat tiskárnu pro tisk
