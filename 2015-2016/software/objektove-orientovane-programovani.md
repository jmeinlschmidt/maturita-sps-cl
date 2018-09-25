# Objektově orientované programování

### 1. Objekt, jak je v OOP charakterizován.

Objekt je základní prvek OOP programu. Má vlastnosti a poskytuje operace. Objekt má vnitřní stav, který jej popisuje a odlišuje od ostatních. Vnitřní stav se ukládá do datových polí jako záznam či proměnné různého typu. Objekt je vytvářen konstruktorem.

### 2. Třída a k čemu slouží, jak se deklaruje?

Třída je předpis objektu a podle ní se objekt vytváří. Třída definuje společné vlastnosti vytvářených objektů. 

Ve třídě se deklarují **stavy** uložené v datových polích, tj. co si objekt pamatuje, a **metody**, tj. co bude moci objekt vykonávat a jak.

### 3. Datová pole objektu.

Datová pole slouží pro uložení stavu objektu, podobně jako proměnné. Určuje se datový typ a modifikátor přístupu.

### 4. Co umožnují a k čemu se používají vlastnosti objektu?

Vlastnosti objektu jsou metody, které získávají vnitřní stav objektu ale i jej měnit. Může např. kontrolovat, zda hodnota odpovídá dalším pravidlům, např. za je číslo větší než 0.

### 5. Metody objektu a k čemu slouží.

Metody objektu jsou funkce a procedury, které objekt poskytuje. Metody pracují s datovými poli objektu a s parametrem, které mohou být použity při volání. 

Mohou měnit stav objektu, vracet jeho hodnotu nebo pracovat se vstupem či výstupem.

Je doporučeno, aby stav objektu mohly měnit pouze vlastnosti a metody pak vlastnosti používaly.

### 6. Co definuje strukturu vytvářeného objektu?

Struktura definuje konstrukci objektu a kombinuje data se seznamem metod pro manipulaci s nimi.

### 7. Konstruktor a k čemu se používá.

Konstruktor je speciální metoda, která slouží pro vytváření objektu třídy. Může nastavit výchozí stav objektu a implicitní konstruktor je vytvořen překladačem. Konstruktor vrací nově vytvořený objekt, který lze přiřadit do proměnné.

### 8. Destruktor a k čemu slouží.

Destruktor je speciální metoda, která se zavolá před zánikem objektu. Může obsahovat operace, které uzavřou otevřené soubory, ukončí databázové spojení atp.

Je implicitní a není povinný.

### 9. Jak vytvoříme nový objekt?

Nový objekt vytvoříme pomocí volání metody konstruktoru.

### 10. K čemu lze využít parametry konstruktoru?

Parametry konstruktoru lze využít pro nastavení vnitřního stavu objektu.

```csharp
public Osoba ( 
  string jmeno, 
  string prijmeni, 
  string email = "",
  string telefon = "", 
  string titul = "" 
  ) {
mJmeno = jmeno;
mPrijmeni = prijmeni;
mEmail = email;
mTelefon = telefon;
mOsobaTitul = titul;
}
```

### 11. Jaký je rozdíl mezi statickými metodami (vlastnostmi, dat. poli) a metodami objektu?

Mohou být použity aniž by byla vytvořena instance třídy (její objekt).

### 12. Co to jsou modifikátory přístupu?

Modifikátory přístupu určují přístup k proměnným, datovým polím, metodám a vlastnostem. Zapisují se zpravidla před daný prvek a využívá se:

- **public**

Umožňuje plný přístup odkudkoli.

- **private**

Přístup je povolen pouze z dané třídy.

- **protected**

Přístup je povolen pouze z dané třídy a tříy odvozené.

- **static**

Jedná se o součást třídy, ne součástí konkrétního objektu.

- **abstract**

Jedná se o základní třídu, která je využívána jako šablona.

- **override**

Umožňuje rozšířit nebo změnit prováděnou metodu.

### 13. Jak provedeme použití vlastnosti objektu (příklad).

Zavoláme jí, uvedeme její název, případně parametry, na místě, kde má být použita/kde ji chceme použít.

### 14. Jak provedeme volání metody (příklad)?

Zavoláme jí, uvedeme její název, případně parametry, na místě, kde má být použita/kde ji chceme použít.

### 15. Jaký je rozdíl mezi metodou a vlastností?

- vlastnost

Jednoduché vlastnosti pracující pouze s jedním datovým polem objektu. Mohou získat pouze vnitřní stav objektu.

- metoda

Pracuje s datovými poli objektu a parametry, které mohou být použity při volání a mohou měnit stav objektu.

### 16. Co to jsou statická datová pole třídy?

Statická datová pole jsou společná pro všechny instance třídy.

### 17. Co to jsou statické metody, vlastnosti?

Statické metody jsou metody, které jsou společné pro všechny instance třídy.

### 18. Jak se deklaruje a definuje třída (datová pole, vlastnosti, konstruktor a metody) v jazyce Pascal

Třída se vytvoří pomocí `unit nazev_tridy`, pomocí `var nazev: datovy_typ` se nastaví datová pole, pomocí `procedure nazev (parametry...)` se vytvoří vlastnosti, pomocí `function nazev (parametry...)` se vytvoří metody a následně se definuje konstruktor.

### 19. Jak se definuje třída (datová pole, vlastnosti, konstruktor a metody) v jazyce CSharp (C#)

Neprve se definují knihovny pomocí `using`, následně se definuje třída `class nazev_tridy`, datová pole, vlastnosti `public datovy_typ Nazev {}`, metody `public datovy_typ nazev () {}` a konstruktor.

### 20. Skládání v OOP (příklad)?

Objekt může obsahovat další objekty, např. auto se skládá z motoru, karoserie atp. Skládání umožní vytvořit objekt složený z několika dalších objektů. Komunikace probíhá pomocí vlastních rozhraní. 

Skládání se používá pro snížení složitosti původního objektu. Cílem je efektivní práce s objektem, přehlednost a rychlé úpravy.

### 21. Dědičnost v OOP (příklad)?

Dedičnost umožňuje vytvoření nové třídy z definice již existující. Původní třída se označuje jako **rodič**, nová třída jako **potomek**. Např. nákladní auto dědí všechny vlastnosti objektu auto a přidá k němu další jako
nosnost.

### 22. Kde se používá prototypová dědičnost a jaký je princip?

Prototypová dědičnost se používá např. v Javascriptu. Princip spočívá v tvorbě nových prototypů. Máme-li třídu `VesmirnyObjekt`, třídu `Planeta` podřídíme tím, že přiřadíme konstruktoru `planeta` jako prototyp objekt `VesmirnyObjekt`.

### 23. Jaký je rozdíl mezi třídní a prototypovou dědičností?

- třídní

Potomek dědí všechny vlastnosti předka.

- prototypová

Využívá se prototyp. Prototyp slouží jako zvláštní objekt, který je přidružen každé funkci.

### 24. Abstrakce v OOP (příklad)?

Využívá se zobecnění, tj. zachycení obecné podstaty objektu nebo třídy. Cílem je zjistit, co a jak objekt bude umožňovat. Např. máme čtverec, to je pravidelný n-úhelník a ten je Tvar (abstrakce).

### 25. Polymorfismus v OOP (příklad)?

Jeden objekt má metody se stejným názvem, ale různými parametry. U objektů odvozených z různých tříd lze volat tutéž metodu se stejným významem.

### 26. Co to jsou delegáty a k čemu se používají?

Delegáty jsou předpis pro typ funkce, podobně jako datový typ určuje typ dat. Delegát určuje jaký bude návratový typ, kolik bude parametrů a jakého datového typu. Používá se, když potřebujeme pracovat s funkcí jako s daty, tj. ji uložit do proměnné.

### 27. Co to je výjimka?

Vyjímka je speciální objekt, který nese informace o chybě programu, ke které došlo.

### 28. K čemu slouží výjimka?

Slouží k zobrazení chybové hlášky v programu, když nastane chyba.

### 29. Jak lze vyvolat (vyhodit) výjimku a jak ji zpracujeme (odchytíme)?

Vyvolání vyjímky ukončí prováděný blok programu. Lze ji vyvolat pomocí `throw new typ_vyjimky`.

Vyjímka lze odchytávat pomocí bloků **try catch**. Try se provede pokud je vše v pořádku, catch pokud nastala chyba.

### 30. Uveďte alespoň čtyři typy výjimek a jejich třídy v jazycích Pascal a CSharp?

Pascal:

- `EConvertException` - převod hodnot
- `ERangeError` - hodnota mimo rozsah

C#:

- `DivideByZeroException` - dělení nulou
- `Exception` - základní výjimka

### 31. Co to je MVC architektura aplikace, popište jednotlivé části.

MVC architektura dělí aplikací do tří logických částí.

- **model**

Reprezentuje data a logiku aplikace.

- **view**

Reprezentuje výpis dat, např. HTML u webových aplikací.

- **controller**

Reprezentuje vrstvu pro kontrolu chodu aplikace, která využívá **model** pro zpracování dat, které předává do **view**.

### 32. Co to jsou a k čemu se používají generické datové typy?

Generické datové typy jsou obecné typy, které se za konkrétní typ dosazí až v okamžiku použití algoritmu v programu.

### 33. Uveďte příklady použití generických datových typů v jazyce CSharp (C#).

```csharp
// metoda pro vyhledani prvni shody podle filtru
// muze byt jakykoliv list - T
static public int Vyhledat<T>(List<T> seznam, Filtr<T> filtr){
  //projit seznam - indexy polozek
  for(int i=0; i<seznam.Count; i++) {
    //zjistit, zda polozka splnuje podminky filtru (vraci true -> provede se prikaz )
    if(filtr(seznam[i])) { 
      return i;
    }
  }
  
  //nenalezeno - pokud se nic nenajde
  return -1; 
}
```
