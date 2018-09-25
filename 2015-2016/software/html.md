# Značkovací jazyk HTML

## Co je HTML

HTML (HyperText Markup Language) je jedním je základních jazyků pro tvorbu webových stránek. Neformální specifikace verze HTML 1.0 byla představena v roce 1991 a fungovala pouze v textovém režimu bez možnosti grafiky. Poslední verzí je HTML 5.

## Značky 

HTML je značkovací jazyk, nikoli programovací. Pomocí značek je popisována struktura HTML dokumentu. 

- párové značky

Element má obsah a je ohraničen otevírací (např. `<div>`) a uzavírací (`</div>`) značkou. Mezi značkami se může nacházet libovolný obsah.

- nepárové značky

Element je označen pouze jednou nepárovou značkou a nemůže mít další volitelný obsah. Typickým příkladem je např. element obrázku, pro který se využívá značka `<img />`.

## Atributy

Pomocí atributů se přidává elementům dodatečný sémantický obsah. Speciálními atributy jsou atribut `id`, označující unikátní element na stránce, a `class`, označující skupinu elementů.

Každý HTML element může mít své vlastní speciální atributy, např. pro obrázek existuje atribut `src`, který je určen pro zdroj obrázku. `<img src="img/obrazek.png" />`.

## Struktura dokumentu

Jako první v dokumentu musí být umístěn tzv. doctype, podle kterého prohlížeč určí jaké verze HTML je daný dokument. Doctype pro HTML 5 vypadá následovně `<!doctype html>`.

Po doctypu se zapisuje element pro celý dokument značkou `<html>`, která dále obsahuje 2 části. První částí je element pro hlavičku, který slouží pro nastavení meta informací. Do element `<head></head>` se zapisují informace jako popis stránky, klíčová slova, titulek stránky (`<title></title>`), autor stránky atp. Druhou částí je element pro samotný obsah viditelné části webu; element `<body></body>`.

V hlavičce se také připojují styly CSS (`<link href="styl.css" rel="stylesheet" type="text/css" />`) a soubory s Javascriptem (`<script type="text/javascript" src="skript.js"></script>`).

## Formátování

Ve starších verzích HTML bylo možné strukturu dokumentu formátovat. V moderní verzi HTML není toto formátování doporučování a místo toho je upřednosňováno stylování pomocí CSS.

CSS lze zapisovat do elementu `<style></style>` pro globální styly, nebo do atributu `style` pro stylování daného elementu.
