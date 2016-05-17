# Kaskádové styly CSS

## Co je CSS

CSS (Cascading Style Sheets) vzniklo kolem roku 1997 pro formátování a grafickou úpravu webových stránek. Styly se tvoří pomocí selektorů, to je pravidlo pro výběr HTML elementů, a jejich bloků kódu. Pokud je využito více pravidel zahrnující stejný element, je použita vlastnost se selektorem s větší důležitostí, nebo při stejné důležitosti zvítězí poslední zapsaný styl. Styly se povětšinou píšou do samostatného `.css` souboru.

V CSS se mohou stylovat barvy, typy písma, pozicovat ale také nastavovat styly pro události elementů jako např. změnit styly při `:hover`, tj. když je myš na elementu.

## Syntaxe

Základní syntaxí v CSS je definování bloku stylů pro daný selektor.

```css
selektor {
  vlastnost: parametr;
  vlastnost: parametr;
  ...
}
```

Hodnoty barev lze zapisovat v několika formátech. Jednak lze použít anglický název pro barvu (např. `red` pro červenou), jednak hexazápis (např. `#ff0000` pro červenou), jednak RGB (např. `rgb(255, 0, 0)` pro červenou) atp.

## Selektory

Základním selektorem je selektor pro element, který se zapisuje jménem dané značky (bez špičatých závorek), tzn. např. `div` či `img`.

Dále můžeme selektorem vybrat identifikátor (atribut `id`) pomocí mřížky, tzn. `#jmeno-identifikatoru`, nebo třídu (atribut `class`) pomocí tečky, tzn. `.jmeno-tridy`.

Obecné atributy, resp. elementy, které tyto atributy obsahují, lze vybírat pomocí hranatých závorek, tzn. `[img]`.

```css
#menu {
  vlastnost: hodnota;
}

.polozka-v-menu {
  vlastnost: hodnota;
}

[img] {
  vlastnost: hodnota;
}
```

Do selektorů lze zapsat speciální znaky, např.:

- `,` - odděluje více selektorů (tzn. styly se aplikují na oba selektory)
- `>` - vybírá pouze přímého potomka
- `+` - vybírá element, který se nachází za daným elementem

## Základní CSS vlastnosti

Vlastnosti a jejich hodnoty jsou většinou slova (americké) angličtiny, tzn. např. pro nastavení červené barvy textu použijeme `color: red;`.

Základními vlastnostmi jsou:

- `color` - barva písma 
- `background` - pozadí elmentu
- `font` - písmo
- `border` - rámeček
- `padding` - vnitřní odsazení elementu
- `margin` - vnější odsazení elementu

## Jednotky

CSS nabízí práci s různými jednotkami rozdělených do 2 typů - relativní a absolutní. Absolutní jednotky jsou jednotky, které se zobrazí vždy a všude stejně. Oproti tomu relativní jednotky jsou závislé na nějaké "proměnné", např. šířce elementu/stránky, velikosti textu atp.

Absolutní jednotky jsou např. `px`. Relativní jednotky jsou např. `%`, `rem`, `em`.
