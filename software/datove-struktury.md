# Datové struktury

### 1. Co to jsou datové struktury?

Datové struktury jsou skupinou pro uložení hodnot a další práci s nimi. Jsou to soubory či množiny dat.

### 2. K čemu slouží datové struktury a jejich účel?

Datové struktury slouží pro sjednocení dat do logických skupin, se kterými lze dále snadno pracovat.

Následně v nich lze třídit, řadit, vyhledávat atp.

### 3. Uveďte základní datové struktury a jak se v literatuře (anglicky) označují?

Druhy datových struktur a jejich implementace závisí na konkrétním programovacím jazyce. 

- **pole** (*array*)
- **záznam** (*record*)
- **seskupení** (*union*)
- **množina** (*set*)
- **objekt** (*object*)
- **hash tabulka** (*hash table*)
- **slovník** (*dictionary*)
- **zásobník** (*stack*)
- **graf** (*graph*)

### 4. K čemu lze použít pole (Array) a jaké jsou jeho vlastnosti?

Pole umožňuje uchovat více položek se stejným datovým typem. K položkám se přistupuje pomocí indexu.

### 5. Co to je záznam (Record) a k čemu jej lze využít?

Záznam umožňuje uchovat více položek různého datového typu. Je dán pevný počet a jejich pořadí. K položkám (*fields* nebo *members*) přistupujeme podle jejich jména.

### 6. Jaký je rozdíl mezi záznamem a polem?

Pole má více položek stejného typu a přistupujeme k nim pomocí indexu, zatímco záznam obsahuje více položek různých typů, ke kterým přistupujeme pomocí jména položky.

### 7. Jaké jsou základní vlastnosti slovníku nebo Hashovací tabulky?

Slovník je flexibilnejší typ záznamu. Využívá páru **klíč-hodnota**, kde se podle klíče vyhledává hodnota. Hashovací tabulka má klíč vždy ve formě textového řetězce.

### 8. K čemu lze využít datovou strukturu seskupení (union)?

Seskupení umožňuje uchovat pouze jeden typ hodnoty v daný okamžik. 

### 9. Popište vlastnosti množiny a k čemu ji lze využít?

Množina umožňuje uchovat seskupení předem daných hodnot, kde nezáleží na pořadí a neopakují se. Hodnoty nemohou být odstraněny či vloženy programově. Využívá se pro testování, zda hodnota patří do množiny.

Označuje se také jako **výčtový typ**.

### 10. Jaké základní vlastnosti má objekt z pohledu datových struktur?

Objekt umožňuje uchovat datová pole nebo jiné objekty. Určuje, co lze s objektem delat, tzn. obsahuje metody a vlastnosti.

### 11. Co to jsou prosté pasivní kolekce hodnot, jak mohou být uloženy v paměti?

Např. záznam a pole.

Hodnoty jsou v paměti uloženy jedna za druhou.

### 12. Jaké dva principy lze využít u datových struktur k nalezení souvisejících dat?

Lze vyhledávat pomocí indexu či názvu či podle páru klíč-hodnota.

### 13. Jaká je podpora datových struktur v programovacích jazycích JSA, Pascal, C#

- **C#**

C# podporuje mnoho datových struktur. Disponuje knihovnami s předpřipravenými strukturami a třídami pro práci s nimi.

- **Pascal**

Pascal podporuje pouze některé datové struktury, např. pole.

- **JSA**

JSA nepodporuje datové struktury, nebo velmi omezeně.

### 14. Popište datovou strukturu pole (Array) a základní práci s polem.

Pole může být statické - definuje se před spuštěním programu a za běhu jej nelze měnit -, nebo dynamické - lze definovat výchozí velikost, která se přizpůsobuje požadavkům; práce s ním je pomalejší.

### 15. Co to jsou vícerozměrná pole?

V podstatě se jedná o pole v poli. Pokud mají pole stejnou velikost, označují se jako maticové pole.

### 16. Popište datovou strukturu Zásobník (Stack) a základní práci se zásobníkem.

Zásobník je abstraktní datová struktura sloužící pro dočasné ukládání jakékoli hodnoty.

Pro práci s daty využívá LIFO (LI = poslední dovnitř; FO - první ven) paměť.

Ukazatel zásobníku ukazuje na poslední vloženou položku. Položku vkládáme pomocí *push*, vyzvedáváme pomocí *pop*.

### 17. Kde najde využití zásobník a co to je zásobník volání (Call Stack)?

Zásobník lze využít tam, kde je nutno vyzvedávat či ukládat položky jednu po druhé, pro dočasné uložení hodnoty.

**Call stack** je typ zásobníku, kam se ukládají informace s návratovými adresami podprogramů.

### 18. Popište datovou strukturu Fronta (Queue) a základní práci s frontou.

Fronta je abstraktní datová struktura pro uchovávání hodnot s libovolným datovým typem.

Využívá se FIFO (FI = první dovnitř; FO = první ven) paměť.

Např. když je rychlost zpracování položek pomalejší než rychlost příjmu nových položek.

### 19. Jaké má využití Fronta?

Např. tisková fronta, uložení velkého množství zpráv pro pozdější zpracování či synchronizaci.

### 20. Popište datovou strukturu Seznam (List) a základní práci se seznamem.

Seznam umožňuje uchovat položky a znát přitom jejich pořadí pro manipulaci. 

Konečný seznam není omezený a hodnota se může vyskytovat vícekrát. Libovolnou položku je možno vytvořit, vložit, vyjmout, odstranit či seřadit.

Spojový seznam může být jednosměrný, obousměrný, lineární či kruhový.

### 21. Jaká je výhoda seznamu (List) oproti poli (Array)?

Seznam může mít kruhový tvar, lépe využívý paměť a známe pořadí položek, což umožňuje snadnější zprávu.

### 22. Popište datovou strukturu Slovník (Dictionary) a základní práci se slovníkem.

Slovník vzniká při práci s daty typu klíč-hodnota. S každou položkou můžeme provádět přidání, odstranění, vyhledávání a nahrazení.

### 23. Kde v programech najde využití Slovník (Dictionary)?

Např. katalogy pojmů či překlady.

### 24. Popište datovou strukturu Graf (Graph), jaké jsou vlastnosti grafu.

Graf umožňuje propojit objekty vazbami.

Graf má dvě části, vrcholy (*nodes*) - hodnoty a jejich údaje uložené v grafu - a hrany (*edges*) - propojení vždy dvou uzlů.

Grafy lze rozdělit na **jednoduché neorientované** (není určen směr hran), **směrové orientované** (je určen směr hran), **vážený graf** (hrany mají různou váhu, která popisuje propojení) anebo **multigraf** (více hran, které propojují stejné vrcholy; hrana může začínat a končit ve stejném vrcholu).

### 25. Kde lze využít datovou strukturu Graf?

Např. pro grafickou vizualizaci, tj. naměření či získání hodnot, průběh funkce anebo pro nalezení vzájemných vztahů mezi objekty.

### 26. Popište datovou strukturu Strom (Tree) a kde najde tato struktura využití (příklad)?

Strom je datová struktura uchovávající hodnoty a jejich vzájemnou hierarchii.

Jedná se o specifický graf, kde každý vrchol může mít pouze odlišného rodiče či potomka.

Binární strom je speciální typ, kde každý vrchol může mít maximálně dva potomky a je využíván pro rychlé nalezení hodnoty.

### 27. Jaký je rozdíl mezi stromem (Tree) a grafem (Graph)?

Strom nesmí obsahovat cykly. Uzel se ve stromu nevyskytuje 2x.

### 28. Co to je Hash tabulka a hash funkce?

Hash tabulka je obdoba slovníku, kde klíč musí být vždy textový. Využívá se asociativní pole.

Hash funkce je taková funkce, která nám ke klíče dá adresu, kde se nachází hodnota.

### 29. Co to je výrazový strom?

Výrazový strom slouží pro znázornění jakéhokoli výrazu, matematického i logického. Lze zapsat jako binární strom.

Je složen ze dvou typů uzlů. Hodnotový uzel obsahuje hodnotu, tedy operant. Uzel operace obsahuje jeden nebo dva poduzly, hodnotové nebo uzly operace.
