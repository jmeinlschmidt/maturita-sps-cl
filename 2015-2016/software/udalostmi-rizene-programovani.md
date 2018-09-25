# Událostmi řízené programování

Pokud není uvedeno jinak, ukázky jsou v jazyce Pascal.

### 1. Co to je událostmi řízené programování?

OOP (objektově orientované programování) s událostm. Událost je změna stavu. Program se ovládá (může i jen částečně) pomocí událostí objektů, které vyvolají akci.

### 2. Na jakém principu funguje událostmi řízené programování?

Při změně stavu objektu se automaticky vyvolá událost. Událost lde také vyvolávat programově.

### 3. Jak je řešeno předávání událostí mezi objekty?

Předávání událostí provede metoda, která se provede při události.

### 4. Kde se využívá událostmi řízené programování?

Formulářové aplikace, webové aplikace.

### 5. Jaké programovací jazyky podporují událostmi řízené programování?

V podstatě všechny moderní programovací jazyky, zvláště pokud podporují tvorbu grafických či formulářových aplikací.

Např. Object Pascal, Visual Basic, C#, JavaScript...

### 6. Popiště 5 typů událostí komponent, které nesouvisí s myší (kurzorem) ani klávesnicí?

- `OnChange` - při změně vlastností objektu
- `OnCreate` - při (resp. po) vytvoření objektu
- `OnDestroy` - při (resp. před) zničením objektu
- `OnActivate` - při aktivaci objektu
- `OnFocus` - při zaměření objektu, např. inputu pro text

### 7. Popiště 3 typy událostí klávesnice, a kdy k nim dochází?

- `OnKeyDown` - při stisknutí klávesy
- `OnKeyUp` - při puštění klávesy
- `OnKeyPress` - klávesa byla zmáčknuta

### 8. Popište 8 typů událostí myši (kurzoru), a kdy k nim dochází?

- `OnClick` - při kliknutí
- `OnDblClick` - při dvojkliku
- `OnMouseDown` - při stisknutí myši
- `OnMouseUp` - při uvolnění stisknutí myši
- `OnMouseWheel` - při použití kolečka na myši
- `OnDragDrop` - při přesouvání objektu myší
- `OnMouseLeave` - když myš opustí plochu objektu

### 9. Coto je **handler** (ošetřující metoda) a k čemu slouží?

Metoda, která poslouchá danou událost na objektu a při nastání události vykoná svůj obsah. Handler metodu lze registrovat i odregistrovat.

### 10. Popište parametr **sender**, který se používá u handlerů.

Sender je speciální objekt, který obsahuje informaci o objektu, který událost vyvolal.

### 11. Co to jsou parametry událostí a jak mohou být předány?

Parametry pro upřesnění události, ke které právě došlo.

### 12. Uveďte příklad handleru stejného typu v jazyce Pascal a C#.

Pascal:
```pascal
procedure TForm1.FormMouseMove(Sender: TObject; Shift: TShiftState; X, Y: Integer);
begin
  ...
end;
```

C#:
```csharp
private void Form1_MouseMove(object sender, MouseEventArgs e) 
{
  ...
}
```

### 13. Uveďte příklad handleru pro událost posun posuvníku (ScrollBar) v jazyce Pascal a C# a odlišnosti.

Pascal:
```pascal
procedure TForm1.ScrollBar1Scroll(Sender: TObject; ScrollCode: TScrollCode; var ScrollPos: Integer);
begin
  ...
end;
```

C#:
```csharp
private void hScrollBar1_Scroll(object sender, ScrollEventArgs e) 
{
  ...
}
```

### 14. Jak připojit handler programově, příklady v jazyce Pascal a C#, popište.

Pascal:
```pascal
udalost := @handler;
```

C#:
```csharp
udalost += handler;
```

### 15. Jak odpojit handler programově, příklady v jazyce Pascal a C#, popište.

Pascal:
```pascal
udalost := nil;
```

C#:
```csharp
udalost -= handler;
```

### 16. Uveďte příklad, jak lze vyvolat (spustit) handler programově v jazyce Pascal a C#.

Pascal:
```pascal
objekt.udalost(sender, parametry);
```

C#:
```csharp
objekt.udalost(sender, objekt_s_parametry);
```

### 17. Uveďte příklad, jak lze vyvolat (spustit) událost (raise event.) programově v jazyce Pascal a C#.

???

### 18. Jak jsou reprezentovány parametry v jazycích Pascal a C#?

V jazyce Pascal jsou parametry události samostatné parametry - musí se zadávat jeden po druhém, kdežto v jazyce C# jsou parametry reprezentovány jedním speciálním objektem, např. `ScrollEventArgs`.

### 19. Jak vytvořit nové parametry události v jazyce C#?

Vytvoří se nová třída (pomocí dědičnosti) odvozená od EventArgs.

### 20. Jaký návrhový vzor (design patern) řeší událostmi řízené programování, popište princip.

Vzor Visitor. Ten umožní registraci obejktu jako odesílatele události a když událost nastane, objekt dá vědět. Používají se pojmy jako *subscribe* a *unsubscribe*.
