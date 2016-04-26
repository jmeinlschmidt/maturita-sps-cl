# Algoritmizace

### 1. Co to je algoritmizace?

Algoritmus je metoda, která slouží k vytváření/sestavování algoritmů.

### 2. Co je vstupem algoritmizace a co výstupem?

- **vstup**

Vstupem algoritmizace jsou specifické požadavky na vytvoření/sestavení algoritmu, tak, aby splňoval všechny požadované podmínky.

- **výstup**

Výstupem algoritmizace je samotný algoritmus.

### 3. Co to je algoritmus?

Algoritmus je postup, jak vyřešit či konat danou úlohu.

### 4. Jak lze algoritmus zapsat?

- **slovně**

Algoritmus lze zapsat slovně, buď formou přirozeného jazyka, kde se podrobně postup popíše, nebo pomocí tzv. pseudo kódu, který se strukturou přibližuje k zápisu v programovacím jazyce, ale místo příkazů jsou použity slova přirozeného jazyka.

- **programovacím jazykem**

Algoritmus je zapsán pomocí cyklů, funkcí atp. v daném programovacím jazyce.

- **graficky**

Algoritmus se zapisuje pomocí vývojového diagramu příkazů.

- **matematicky**

Algoritmus je zapsán vztahem mezi veličinami, soustavou rovnic, maticemi atp.

### 5. Jaké jsou vlastnosti algoritmu?

- **alespoň jeden vstup**

- **resultativnost**

Každý postup je přesně definován.

- **obecnost** 

Algoritmus neřeší konrétní problém (musí řešit zadanou úlohu pro různé přípustné hodnoty).

- **konečnost** 

Algoritmus musí skončit v libovolném počtu kroků, ten může být libovolně velký.

- **srozumitelnost a přehlednost**

Pokud úlohu řeší více algoritmů, vybíráme ten nejefektivnější.

### 6. Co to jsou vyšší programovací jazyky?

Vyšší programovací jazyky mají blíže k přirozenému jazyku a používají se běžná slova (např. if, when, class...), čímž jsou srozumitelnější.

Poskytují také abstrakci nad tím, jak funguje procesor počítače. Zabývají se více tím, jak obecně implementovat algoritmus, než-li jak jen provést pro daný procesor počítače.

Umožňují využívat např. datových typů a datových struktur, čímž lze program lépe strukturovat a lze jej vytvářet přehledněji.

### 7. Co to jsou nižší programovací jazyky?

Nižší programovací jazyky mají blíže k počítači a jejich syntaxe spíše připomíná instrukce. Neposkytují žádnou nebo malou abstrakci od toho, jak funguje procesor počítače. 

### 8. Uveďte příklady nižších a vyšších programovacích jazyků a zdůvodněte.

- **vyšší**

Např. Java, C#, Javascript, Pascal...

- **nižší**

Např. JSA, C...

### 9. Jaký je rozdíl mezi vyššími a nižšími programovacími jazyky?

Viz. otázky 6 a 7.

### 10. Jak vzniká program?

Nejprve je nutno napsat zdrojový kód programu, tedy kód např. v jazyce C#. Daný kód se poté zkompiluje či je překládán interpretem do strojového kódu, se kterým následně pracuje procesor počítače.

### 11. Co to je překladač?

Překladač je program, který ze zdrojového kódu vytvoří spustitelný soubor, nejčastěji obsahující strojový kód. 

### 12. Co to je interpret?

Interpret je program, který zdrojový kód překládá postupně během běhu programu.

### 13. Co to je strojový kód?

Strojový kód je posloupnost strojových instrukcí prováděných CPU. 

### 14. Jaký je rozdíl mezi interpretovanými a kompilovanými prog. jazyky?

- **interpretovaný**

Pro spuštění programu je nutný interpret, tedy program vykonávající jednotlivé příkazy programu. Většinou je paměťově náročnější.

- **kompilovaný**

Zdrojový kód je nutné přeložit pouze jednou, poté lze spouštět bez nutnosti externího programu.

### 15. Popište v krocích vývojový cyklus software.

- **požadavky**

Řeší se, jakou úlohu bude program řešit, kde bude využíván a pro koho bude určen.

- **specifikace**

Popisování funkčnosti požadovanéhoprogramu. Využívá se pomůcek jako grafů, obrázků atp.

- **architektura**

Navrhuje se, jak bude program fungovat jako celek. Program se rozděluje na moduly či vrstvy. Závislé na programovacím jazyce.

- **návrh**

Detailní popis všech částí programu. Závislé na programovacím jazyce.

- **vytvoření**

Vytvoření samotného programu podle předešlých kroků.

- **testování a ladění**

Program se testuje, zda-li je funkční a vše funguje beze chyb. Pokud program nesplňuje požadavky, je nutné ho upravit.

- **použití**

Pokud vše funguje, program je možno poskytnout uživatelům.

### 16.  Jak algoritmizujeme úlohu pro strukturovaný programovací jazyk?

Jakýkoli algoritmus lze zapsat pomocí těchto příkazů:

- posloupnost příkazů
- neúplný podmíněný příkaz
- úplný podmíněný příkaz
- cyklus s podmínkou před posloupností
- cyklus s podmínkou za posloupností
- cyklus řízený parametrem

### 17. Jak algoritmizujeme úlohu pro objektově orientovaný jazyk?

Je nutno rozložit logiku programu na jednotlivé spolu provázané objekty.

### 18. Jaký je rozdíl mezi algoritmizací ve strukturovaném programovacím jazyce a objektově orientovaném jazyce?

- **strukturovaně**

Program se člení do funkcí či procedur.

- **objektově**

Program se člění do objektů, které dále mají metody s různým modifikátorem přístupu.

### 19. Jaké používáme konstrukce u algoritmizace ve strukturovaném programovacím jazyce?

Viz. 16.

### 20. Jaké používáme konstrukce u algoritmizace objektově orientovaném programovacím jazyce?

Využívá se objektů a tříd. Objekty se mohou dále modifikovat pomocí dědičnosti, skládání, zapouzdření atp.

### 21. Co to jsou návrhové vzory?

Návrhové vzory představují řešení návrhu programu. Jedná se o vyzkoušený postup, ne o knihovnu či kus kódu. Řeší návrh, ne konkrétní problém.

### 22. Jaký je vztah mezi návrhovými vzory a algoritmizací?

Algorizace bere v potaz návrhový vzor, kterým se musí řídit, aby se zachovala jednotnost v rámci programu. Návrhový vzor je jakousi šablonou pro algoritmizaci.
