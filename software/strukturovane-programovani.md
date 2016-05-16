# Strukturované programování

### 1. Program ve strukturovaném programovacím jazyce – struktura (např. Pascal).

Program se v Pascalu člení na tři části: hlavičku, definici s deklaracemi a tělo. 

### 2. Co to jsou komentáře a k čemu slouží?

Komentáře slouží k popisování částí, zejména ne na první pohled zřejmých, programu.

### 3. Jak lze rozdělit komentáře podle jejich typů?

Ukázky jsou uvedeny pro C-like jazyky, konkrétně např. C Sharp.

- řádkové

Každý řádek musí začínat `//`.

```csharp
// komentar
```

- víceřádkové

Mají počáteční (`/*`) a koncový (`*/`) uvozovače a obsah mezi nimi je považován za komentář.

```
/*
 viceradkovy
 komentar
 */
```

### 4. Co to je deklarace a definice. Jaký je mezi nimi rozdíl?

- deklarace

Deklarace říká, že se proměnná/funkce... bude v programu vyskytovat.

- definice

Definice již přímo nastavuje hodnotu proměnné či obsah fukce.

### 5. Co to jsou klíčová slova, k čemu se používají a uveďte příklady a jejich využití.

Jsou slova nebo identifikátory, které mají specifický význam v daném programovacím jazyce.

### 6. Co to je identifikátor a jaká jsou běžná pravidla pro zápis identifikátoru?

Identifikátor zastupuje hodnotu, která se za běhu programu může měnit. Proměnná je označení pro identifikátor, které uchovává určitou informaci při běhu programu.

### 7. Co to jsou programové jednotky (hlavičkové soubory)?

Programové jednotky, neboli "Unit" jsou jakési "předpřipravené" programy v Pascalu, ze kterých je možné používat procedury, funkce a proměnné, jako např. `uses crt;`.

### 8. Hlavička programu a tělo programu, k čemu slouží?

Hlavička nám určuje, o jaký typ programu jde a měla by také v podobě komentáře obsahovat informace o tom, co program dělá. 

V těle jsou umístěny samotné příkazy, které se vykonají.

### 9. Co to jsou konstanty a je jejich využití v programu.

Konstanty jsou indentifikátory, které nemění svou hodnotu. 

### 10. Co to je datový typ a co udává?

Datový typ definuje druh nebo význam hodnot, kterých smí proměnná nabývat. Také zahrnuje seznam operací, které lze s proměnnou provádět.

### 11. Uveďte rozdělení datových typů.

- celočíselné
- logické
- reálné a znakové
- výčtový typ

### 12. Kde se v programu v jazyce Pascal definují datové typy?

Definice svým identifikátorem a typem v deklarační oblasti.

### 13. Co to je hodnota a co je k hodnotě přiřazeno? Uveďte příklady hodnot.

Hodnota je vnitřek proměnné, tzn. to, co je v ní uloženo. Hodnota může mít různý datový typ.

### 14. Jak souvisí datový typ a konstanta? 

Konstanta, stejně jako proměnná, má datový typ hodnoty.

### 15. Jak a kdo určí datový typ konstanty (jaké jsou možnosti)? Jak to funguje v jazyce Pascal?

Programátor, který nastavuje datový typ a konstanty.

```pascal
const Jmeno_konstanty = hodnota;
type datovy_typ_x = ...;
```

### 16. Standartní příkazy pro vstup a výstup (výpis textu, načtení hodnoty, čekání na stisk klávesy).

- `Read(promenna);`

Čteme znaky z klávesnice a uložíme je do proměnné uvedené jako parametr.

- ReadLn(promenna);

Čteme znaky z klávesnice a uložíme je do proměnné uvedené jako parametr, vstup/výstup se však provede vždy na nový řádek, pomocí ENTERu.

- Write('Text ....',promena,konstanta,...);

Výstup na obrazovku. Může se použít pouze jedna proměnná, nebo několik oddělených čárkou.

- WriteLn('Text ....',promena,konstanta,...);

Výstup na obrazovku s následným odřádkováním. Může se použít pouze jedna proměnná, nebo několik oddělených čárkou.

### 17. Operátor a co operand.

Operátor je operace, kterou chceme provádět, například `+` nebo `-`. Operand je to, s čím pracujeme, např. proměnná.

### 18. Přiřazovací operátor a jak funguje (operandy)?

Jeden z nejčastějších operátorů, značen `=`. Slouží pro přiřazení hodnoty z pravé strany do proměnné na levé straně od operátoru.

```csharp
int skola = 1;
```

### 19. Aritmetické operátory a jak se vyhodnocují (operandy)?

Aritmetické operátory `+`, `-`, `*`, `/` a `%` představují základní matematické operace sčítání, odčítání, násobení, dělení a zbytku po celočíselném dělení.

### 20. Relační operátory, jejich vyhodnocování a kde najdou využití?

Relační operátory `<`, `>`, `<=`, `>=`, `==`, `!=` jsou definovány pro operandy všech základních datových typů a jejich výsledkem jsou logické hodnoty pravda a nepravda.

### 21. Logické operátory, jejich vyhodnocování a kde najdou využití?

Logické operátory představují dvě hodnoty, pravdu a nepravdu. Logickými operátory jsou `&&` (logický součin), `||` (logický součet) a `!` (negace).

### 22. Pomocí jakého operátoru přistupujeme k položkám pole v jazyce Pascal.

Je využito ukazatele (pointer).

### 23. Co to je podmínka?

Podmínka (if else) rozděluje (větví) kód na dvě části podle logické hodnoty podmínky na sekci pravda a nepravda.

### 24. Uveďte příklady jednoduchých podmínek.

```pascal
if cislo = 5 then write('Ahoj');
```

### 25. Uveďte příklady složených podmínek.

```pascal
if (podminka)
  telo bloku
else if (podminka)
  telo bloku
else
  telo bloku
```

### 26. Co to je proměnná, jak se s ní pracuje a jak funguje (obrázek)?

Pojmenované místo v paměti počítače. Je v ní uložena hodnota určitého datového typu.

### 27. Co to je ukazatel (pointer)?

Ukazatel je datový typ, který slouží k uložení adresy v paměti počítače. Používá je většina imperativních programovacích jazyků, jako např. C a Pascal. Syntaxí zápisu programu je rozlišeno, zda se pracuje s hodnotou adresy ukazatele anebo s hodnotou datového prvku, na který ukazuje.

### 28. Čím jsou odděleny příkazy v programovacím jazyce Pascal a i v jiných jazycích? 

Středníkem.

### 29. Jak jsou vyhodnocovány výrazy s operátor v programovacím jazyce (priorita)?

Podle priority daného operátoru, např. `*` (násobení) se vykoná dříve než `+` (sčítání) a `()` se vykonají dříve než `*`.

### 30. Jak lze změnit prioritu vyhodnocování operátorů?

Pro změnu pořadí/priority vyhodnocování lze použít kulaté závorky `()`.

### 31. Instrukce skoku.

Skok skočí na dané návěští v programu. Užívají se hlavně v nízkoúrovňových jazycích, např. v JSA.

### 32. Úplné a neúplné větvení podle podmínky (princip)?

Úplné větvení obsahuje krok pro kladnou i zápornou odpověď. V neúplné větvení chybí krok pro jednu z větví.

### 33. Větvení podle hodnoty (princip)?

Potřebujeme-li rozvětvit program např. podle hodnoty celočíselné proměnné, můžeme použít zřetězení příkazů if.

```pascal
if( x == 1 ) {
  System.out.println( "jedna" );
} else if( x == 2 ) {
  System.out.println( "dva" );
} else if( x == 3 ) {
  System.out.println( "tři" );
}
```

### 34. Cyklus s parametrem (princip).

Cyklus s parametrem je `for`, ten se používá, pokud předem víme v jakém rozsahu hodnot chceme kód vykonat.

### 35. Cyklus s podmínkou před a za příkazy (princip).

Pro cyklus s podmínkou před cyklem používáme cyklus **while**, zatímco pro cyklus s podmínkou za používáme cyklus **repeat until**.

### 36. Co to je funkce nebo procedura a čím se liší?

Procedura vykonává dané příkazy. Funkce vykonává dané příkazy a vrací hodnotu.

```pascal
procedure ukazZpravu;
begin
  showmessage('Důležitá informace'); beep;
end;

function dvakrat(cislo: integer): integer;
begin
  dvakrat:=cislo*2;
  {result:=cislo*2;}
end;
```

### 37. Co to je volání funkce a jak toto volání v programu provedeme?

Funkce je možné opakovaně volat z různých míst kódu. Pro vyvolání se používá identifikátor/název funkce. Funkce může mít parametry či argumenty, které jí jsou předávány při volání. 

### 38. Co to je parametr funkce (procedury) a k čemu jej lze použít?

Parametry jsou hodnoty předané proceduře.

```
procedure ahoj(kdo: string);
begin
  writeln('Ahoj '+kdo);
end;
```

### 39. Co to je signatura funkce (procedury)?

Jedná se o její název/identifikátor.

### 40. Co to je návratová hodnota funkce?

Návratová hodnota funkce je hodnota, která se nám vrátí po jejím provedení. Její typ se uvádí před jménem funkce. Např. funkce `main()` má vždy návratovou hodnotu typu `int`.

### 41. Kde lze v programu v jazyce Pascal definovat procedury a funkce (dvě možnosti)?

Definují se před začátkem samotného těla programu, nebo v tělech jiných procedur či funkcí. 
