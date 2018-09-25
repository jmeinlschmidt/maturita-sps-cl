# Vývojové diagramy, UML a návrhové vzory

### 1. Co to je vývojový diagram?

Vývojový diagram je diagram, který slouží ke znázornění jednotlivých kroků algoritmu, nebo obecného procesu. Pomocí nich znázorňujeme jednotlivé kroky algoritmu. 

Kroky se znázorňují pomocí symbolů, které jsou vzájemně propojeny pomocí orientovaných šipek. Symboly reprezentují procesy a šipky reprezentují tok řízení.

### 2. Kde najde využití vývojový diagram?

Kdekoli v informatice, obzvláště v programování pro analýzu, návrh nebo dokumentaci.

### 3. Jaké základní konstrukce se vyskytují ve vývojovém diagramu?

- mezní značka
- zpracování
- větvení
- poznámka
- spojka
- vstup a výstup hodnot

### 4. Co je značkami ve vývojovém diagramu a čím se značky propojují?

Značky jsou ve formě geometrických obrazců/symbolů a propojují se pomocí šipek.Běžné značky mají jeden vstup (ze shora) a jeden výstup (ze zdola).

### 5. Mezní značka ve vývojových diagramech a využití.

Ovál.

Označuje počátek a konec diagramu a většinou jsou dvě - počáteční a ukončující.

### 6. Značka pro zpracování nebo činnost a její využití.

Obdélník.

Značka slouží pro zadání příkazů a představuje výpočty, operace nebo činnost programu.

### 7. Značka pro ruční zadání vstupních dat a její využití.

Obdélník s levou stranou kratší.

Značka slouží pro zadání hodnot od uživatele (z klávesnice).

### 8. Značka pro načtení a výpis hodnot a kdy se používá?

Rovnoběžník.

Značka umožňuje načtení hodnot do algoritmu nebo zobrazení výsledku výpočtu.

### 9. Značka rozhodovací blok a kdy se používá? 

Kosočtverec.

Značka slouží k větvení programu na základě podmínky. 

### 10. Značka příprava a kdy se používá?

Označuje část programu, která se využívá pro zahájení cyklu o známém počtu průchodů. Stejnou značku je nutno uvést i na konec cyklu.

### 11. Značka spojky a kdy se používá?

Značka umožňuje propojit dvě části diagramu. Využívá se v případech, kdy diagram není možné nakreslit souvisle. Spojky jsou označeny číslem.

### 12. Značka předem definovaná činnost

Obdélník s dvojitou levou a pravou stranou.

Používá se pro příkaz nebo podprogram, který je definovaný v jiném diagramu. 

### 13. Jaký je rozdíl mezi použitím značek předem definovaná činnost a zpracování?

- zpracování

Zajímá nác, **co** máme vykonat. Je nám jedno, jak se vykoná.

- předem definovaná činnost
 
Zajímá nác, **co** a **jak** se vykoná. Činnost se definuje v jiném diagramu.

### 14. Značka tisk

Používá se pro výstup programu, např. tiskový dokument na tiskárně.

### 15. Zakreslete jako diagram posloupnost příkazů ze strukturovaného programování

### 16. Zakreslete jako diagram úplný podmíněný příkaz ze strukturovaného programování

### 17. Zakreslete jako diagram neúplný podmíněný příkaz ze strukturovaného programování

### 18. Zakreslete jako diagram cyklus s podmínkou před příkazy ze strukturovaného programování

### 19. Zakreslete jako diagram cyklus s podmínkou za příkazy ze strukturovaného programování

### 20. Zakreslete jako diagram cyklus s parametrem ze strukturovaného programování

### 21. Do jaké značky zapisujeme podmínku? Jak se tato značka jmenuje?

Podmínka se zapisuje do značky větvení, která se značí kosočtvercem.

### 22. Co to je UML?

Unifikovaný modelovací jazyk.

Využívá se pro grafické znázornění či popis programů, tj. jeho algoritmu, struktury, chování atp. Neobsahuje však postup, jak se má používat.

### 23. Kdy a kde najde využití UML?

Využívá se pro vizualizaci, dokumentaci, navrhování a specifikaci. Využívá se kdekoli, kde potřebujeme popsat proces zpracování dat/informací, systémové funkce, konkrétní příkazy, schéma databáze nebo programové komponenty.

### 24. Lze použít UML jako programovací jazyk a jak?

Speciální SW dokáží podle UML vygenerovat kód a vazby programu.

### 25. Co nás zajímá u detailního popisu pomocí UML?

Popsat celý systém a všechy jeho části tak, aby programátor neměl potřebu hlubšího přemýšlení nebo další konzultace.

### 26. Jak se rozdělují UML diagramy?

- **strukturální** (tříd, komponent)
- **chování** (aktivit, užití)
- **interakce** (sekvenční, komunikace)

### 27. Uveďte tři typy různých UML diagramů a jejich využití.

- **diagram aktivit**

Diagram chování, který zobrazuje, jak probíhají procesy aktivit v SW systému (např. registrace uživatele).

- **diagram komponent**

Strukturní diagram, který zobrazuje větší části SW systému.

- **sekvenční diagram**

Diagram interakce, který zobrazuje proces jako posloupnost jednotlivých akcí a jejich návaznosti.

### 28. Co to je UML diagram tříd?

Popisuje třídu a její vazby mezi ostatními třídami. Datová pole a metody mohou být rozlišeny modifikátorem přístupu. U některých tříd stačí pouze jejich název, tj. jejich vnitřní struktura je nepodstatná.

### 29. Jak se zakresluje v UML diagramu třída (metody, dat. pole, viditelnost položek)?

- `+` - public
- `-` - private
- `#` - protected
- `/` - derived
- `_` - static
- `~` - package

### 30. Jaké existují propojení tříd popsané pomocí UML (4. typy) a popište je.

Třídy se propojují pomocí asociací. U asociací nás zajímá, o jaký vztah se jedná a mezi kolika objekty třídy nebo třídami existuje.

Jsou podobné relacím v databázích. Existují 4 typy:

- jednosměrná
- obousměrná
- agregace (složení)
- odvozená
