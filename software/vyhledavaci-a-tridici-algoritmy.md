# Vyhledávací a třídící algoritmy

### 1. Co to je třídící algoritmus?

Algoritmus, který seřadí seznam položek do určitého pořadí a zajišťuje seřazení podle specifického pořadí.

### 2. Jaké máme dva základní typy řazení podle typu hodnot, které řadíme?

- **číselné seřazení**

Porovnáváme dvě čísla a určíme, které je větší a které menší, či zda se nerovnají.

- **lexikografické**

Řazení symbolů nebo znakové sady (textového řetězce), každému symbolu je
přiřazena hodnota (př. ASCII tabulka).

### 3. Co musí být splněno, aby bylo možné položky označit jako seřazené?

V seřazeném seznamu má každá následující položka stejnou nebo větší/menší hodnotu než položka předcházející.

### 4. Co je výstupem třídícího algoritmu?

Výstupem jsou uspořádaná data.

### 5. Jaké rozlišujeme dva druhy seřazení podle pořadí položek v seřazené posloupnosti?

- **vzestupné**

Hodnoty jsou seřazeny od nejmenšího po největší.

- **sestupné**

Hodnoty jsou seřazeny od největší po nejmenší.

### 6. Proč jsou řadící algoritmy důležité?

Řadicí algoritmy jsou důležité pro uspořádání chaotických dat, pro rychlé vyhledávání (např. binární vyhledávání) anebo pro užití dat pro další ruční zpracování (např. žebříčky).

### 7. Co využívají řadící algoritmy pro uložení dat nebo položek, se kterými pracují?

Využívají se různé datové struktury, které se liší množstvím paměti a množstvím výpočetního času.

### 8. Čím se různé řadící algoritmy odlišují?

- podle O-notace (popis průběhu fce)
- podle místa v paměti
- způsobem procházení položek
- podle časové náročnosti (čas seřazení závisí na tom, jak jsou vstupní data uspořádána)

Časových náročností může být více typů: nejlepší/nejkratší (best), průměr/nejčastější
(awerange) a nejhorší/nejdelší (worst).

### 9. Jak lze rozdělovat řadící algoritmy (7 kategorií)?

- výpočetní a časová náročnost
- využití paměti

Záleží, zda algoritmus využívá pomocná pole nebo proměnné či kolik paměti je potřeba vzhledek na počet položek.

- rekurzivnost

Algoritmus využívá sám sebe.

- stabilita

Algoritmus seřadí libovolnou posloupnost, tzn. nedochází k záměně.

- porovnávací třídícího algoritmu
- obecná technika 

Ukládání, prohazování atp.

- přizpůsobivost 

Použít jiný typ algoritmu (př. je seřazený).

### 10. Co udává výpočetní a časová náročnost třídícího algoritmu?

Časová náročnost určuje, jak dlouho bude seřazení trvat vzhledem k počtu položek. Výpočetní náročnost určuje kolik kroků bude nutné provést, než dostaneme setříděný seznam.

### 11. Třídící algoritmy z pohledu využití paměti.

Liší se dle počtu položek určených pro seřazení.

### 12. Vysvětlete rozdělení algoritmů podle Rekurzivnosti, Stability, Obecné techniky a Přizpůsobivosti.

Viz otázka 9.

### 13. Časová a paměťová náročnost třídících algoritmů, co to je O-notace

Časová náročnost viz otázka 10.

Paměťová náročnost určuje, kolik paměti navíc bude algoritmus potřebovat pro setřídění. To závisí na počtu položek *n*. V případě náročnosti *n* potřebuje algoritmus tolik paměti kolik je položek.

O-notace popisuje průběh funkce, který se získá z naměřených hodnot. U třídících algoritmů se jedná o čas nutný pro setřídění v závislosti na počtu prvků, které jsou setříděny.

### 14. Uveďte několik různých tříd časové náročnosti třídících algoritmů a porovnejte je.

- O (n^2) – kvadratická

Bubble sort, insert sort.

Průběh třídění má podobu přímé úměrnosti, nedoběhne rychleji než v lineárním čase (nejhorší).

- O (1) – konstantní
- O (log log n) – dvojitě logaritmická (nejlepší)
- O (log n) – logaritmická
- O (n) – lineární
- O (n log n) – lineárně logaritmická => kombinace (složená, násobek)
- O (n^(1/2)) – odmocninová
- O (n!) – faktoriální (nejhorší)

### 15. Jak fungují třídící algoritmy Bubble, Insertion, Selection a uveďte jejich základní vlastnosti.

- **bubble sort**

Bublinkové třídění je jednoduchý třídící algoritmus, který opakovaně prochází seznam a porovnává vždy dvě sousedící položky, pokud nejsou ve správném pořadí, prohodí je. Pro praktické účely je neefektivní, jeliko se používá se hlavně v nenáročných aplikacích a na výukové účely.

Časová náročnost je O(n), O(n^2).

Je univerzální, pracuje s polem nebo seznamem, vyžaduje jednu pomocnou proměnnou a částečně seřazený seznam zpracuje rychleji než neseřazený.

```
procedure bubbleSort(polePolozek) {
  repeat
    for i=1 to polePolozek.Lenght do
      if polePolozek[i] > polePolozek[i-1] then
        prohodit(polePolozek[i], polePolozek[i-1])
      prohozeno = true;
  until prohozeno
}
```

- **insert sort**

Řazení vkládáním. Je založen na porovnávání.

Prochází prvky postupně a každý nesetříděný prvek zařadí na správné místo do již setříděné posloupnosti. Posloupnost se rozdělí na seřazenou (obsahuje první prvek posloupnosti) a neseřazenou část. Z neseřazené části se následně vybere 1. prvek, který se vkládá na správnou pozici v sestříděném seznamu. Postupuje se až do seřazení všechn položek.

Je jeden z nejrychlejších algoritmů. Časová náročnost je kvadratická O(n^2). Je efektivní v malých množinách a je stabilní.

````
function insertionSort(array a) 
  for i in 0 -> a.length - 2 do
    j = i + 1 neprohodí na správné místo
    tmp = a[j]
    while j > 0 AND tmp > a[j-1] do
      a[j] = a[j-1]
      j--
    a[j] = tmp
```

- **selection sort**

Neefektivní pro třídění velkého množství položek, ale je jednoduchý na naprogramování. Časová náročnost O(n^2).

Seznam položek se rozdělí na setříděnou a nesetříděnou část. Setříděná část je na začátku prázdná. Při každém průchodu je v nesetříděné části nalezena položka s minimální či maximální hodnotou (záleží na implementaci) a ta se vloží do setříděné části.

```
prvninesetridena = 0;
for(int i = 0; <= seznam.lenght-1; int) {
  int min = seznam[prvninesetridena];
  for(int j = = prvninesetridena;
  j<=seznam.lenght1;j++)
}
```

### 16. Jak funguje třídící algoritmus QuickSort a uveďte jeho základní vlastnosti.

Rychlý, nestabilní řadící algoritmus na principu rozděl a panuj o složitosti O(n^2), O(n * log n). Algoritmus podporuje rekurzi.

V zadaném poli se zvolí pivot. Pole se přehází tak, aby na jedné straně byly prvky větší než pivot a na druhé straně prvky menší. Postup se opakuje i pro rozdělené části.

```
procedure quicksort(List values)
  if values.size <= 1 then
    return values

  pivot = náhodný prvek z values

  Rozděl seznam values do 3 seznamů
    seznam1 = { prvky větší než pivot }
    seznam2 = { pivot }
    seznam3 = { prvky menší než pivot }

  return quicksort(seznam1) + seznam2 + quicksort(seznam3)
```

### 17. Jak funguje třídící algoritmus MergeSort a uveďte jeho základní vlastnosti.

Stabilní třídící algoritmus typu rozděl a panuj o složitosti O(n*log n). Pracuje na bázi slévání již seřazených částí pole za pomoci dodatečného pole velikosti n.

Dva seznamy A a B, které jsou seřazené v sestupném pořadí, se setřídí do jednoho seznamu C. V každém kroku se vždy porovnají první prvky z obou seznamů, vybere se vyšší a přesune se do C. Proces se opakuje tak dlouho, dokud nedojde k vypráznění jednoho seznamu, potom se zbytek přesune do výsledného seznamu.

### 18. Co to jsou vyhledávající algoritmy?

Vyhledávají položky podle zadaného klíče/údaje a jeho hodnoty.

### 19. V jakých datových strukturách lze vyhledávat (uveďte tři).

Nejčastěji v Poli (Array), Seznamu (List), Slovníku (Dictionary).

### 20. Co může být výstupem vyhledávacího algoritmu?

Buď první výskyt hledané položky, nebo všechny výskyty (může se jednat o více položek – seznam), index, klíč položky, samotná položka.

### 21. Pokud není nic nalezeno, co vyhledávající algoritmus může vracet?

Pokud nic nevyhledá, vrátí prázdný ukazatel `null` nebo prázdný seznam.

### 22. Pokud je vyhledávající algoritmus vytvořen jako funkce, co musí splňovat?

Pole nebo seznam, ve kterém se vyhledává nebo funkci, která vrací `true`/`false`, pokud položka odpovídá hledanému klíči a její hodnotě.

### 23. Časová náročnost vyhledávacích algoritmů.

Určuje, jak dlouho se bude trvat vyhledávání položky a čas (jak dlouho potrvá vložení nebo odstranění položky a následná příprava pro) vyhledání.

### 24. Co mohou vyžadovat zejména rychlejší vyhledávající algoritmy pro svou správnou funkci?

Mohou vyžadovat setříděný seznam, který je nutné setřídit dříve, než začne vyhledávání.

### 25. Popište lineární vyhledávání a jeho výhody a nevýhody.

Seznam prochází položku po položce. Pokud najde hledanou, přidá se od výsledného seznamu nebo sebo se provede jiná akce (vrátí se jako první výskyt). Pokud dojdeme na konec seznamu a nic se nenajde, vrátí se `null` nebo `false`.

Algoritmus nepotřebuje setříděný seznam a je jednoduchý na naprogramování. Česková náročnost je O(n), což je u velkých seznamů pomalé.

### 26. Popište binární vyhledávání a jeho výhody a nevýhody.

Zjišťuje pozici zadaného prvku v seřazeném poli a vyžaduje setříděný seznam. Pracuje se složitostí O(log2 n). Může se řešit pomocí rekurze nebo cyklu while.

V setříděném seznamu se zvolí prostřední prvek pole a porovná se s hledaným. Pokud je shodný, vratí se index prvku. Pokud je menší či větší, pokračuje se v hledání v dané části pole.

### 27. Popište vlastnosti a požadavky pro algoritmy pro vyhledávání v grafech.

Použití datové struktura graf. Vhodné pro vyhledávání souborů/složek na disku, navigace a hledání cesty (nejkratší), hledání cyklů v grafech (dopravní spojení, doručování balíků na adresy – cesta končí tam kde začala, ve skladu). Definovaný jako seznam uzlů nebo propojení/objekt – skládá se ze seznamu uzlů.

Graf je datová struktura, kde se vyhledává, může být definovaný jako seznam uzlů nebo jako objekt (měl by poskytovat metody: přidání/odebrání uzlu, vytvoření/zrušení propojení). 

Kritérium je fce/metoda, která vrací `true`/`false`, pokud je uzel nalezen (odpovídá hledanému klíči a jeho hodnotě). Algoritmy využívají rekurzi (volání sama sebe – nejkratší zápis, ale pozor na chyby) nebo zásobník.

Výstupem je konkrétní uzel a v něm uložená hodnota, seznam, vyhledání cesty atp.

### 28. Co to jsou delegáty a kde najdou využití?

Delegáty jsou předpis pro typ funkce, podobně jako datový typ určuje typ dat. Delegát určuje, jaký bude návratový typ a počet parametrů a jakého datového typu.

Používá se, když potřebujeme pracovat s funkcí jako s daty, tzn. ji uložit do proměnné. Lze pomocí nich vytvořit univerzální algoritmy, které mohou používat funkci, kterou jim dáme k dispozici.

### 29. Co to jsou generiky a kde najdou využití?

Generické datové typy (obecné – šablonové), u kterých v okamžiku vytvoření algoritmu neznáme, datový typ bude používat a konkrétní typ se za generický dosadí až okamžiku použití algoritmu v programu. Lze pomocí nich vytvářet algoritmy, které nejsou závislé na použitém datovém typu.

```
// metoda pro vyhledani prvni shody podle filtru
// muze byt jakykoliv list - T
static public int Vyhledat<T>(List<T> seznam, Filtr<T> filtr) {
  // projit seznam podle indexu polozek
  for(int i=0; i<seznam.Count; i++) {
    // zjistit, zda polozka splnuje podminky filtru (vraci true -> provede se prikaz )
    if(filtr(seznam[i])) { 
      return i;
    }
  }
  
  // nic nenalezeno
  return -1; 
}
```
