# Značkovací jazyk XML

## Co je XML

XML (Extensible Markup Language) je obecný značkovací jazyk, který byl vyvinut a standardizován konsorciem W3C a vycházel z něj jazyk HTML. Používá se pro serializaci dat, v čemž soupeří např. s JSON či YAML. Zpracování XML je podporováno řadou nástrojů a programovacích jazyků.

Jazyk je určen především pro výměnu dat mezi aplikacemi a pro publikování dokumentů, u kterých popisuje strukturu z hlediska věcného obsahu jednotlivých částí, nezabývá se vzhledem. Prezentace dokumentu (vzhled) může být definována pomocí kaskádových stylů (CSS).

XML je standardní formát pro výměnu informací, má mezinárodní jazykovou podporu, XML dokumenty jsou informačně bohaté a konverze do jiných formátů je snadná. XML neobsahuje předdefinované tagy a všechny tagy je možné (nepovinně) definovat pomocí např. DTD (Document Type Definition).

## Syntaxe 

Na rozdíl od např. HTML je efektivita XML je silně závislá na struktuře, obsahu a integritě. Aby byl dokument považován za správně strukturovaný, musí mít nejméně následující vlastnosti:

- Musí mít právě jeden kořenový (root) element.
- Neprázdné elementy musí být ohraničeny startovací a ukončovací značkou. Prázdné elementy mohou být označeny tagem "prázdný element".
- Všechny hodnoty atributů musí být uzavřeny v uvozovkách – jednoduchých (`'`) nebo dvojitých (`"`), ale jednoduchá uvozovka musí být uzavřena jednoduchou a dvojitá dvojitou. Opačný pár uvozovek může být použit uvnitř hodnot.
- Elementy mohou být vnořeny, ale nemohou se překrývat; to znamená, že každý (ne kořenový) element musí být celý obsažen v jiném elementu.
- Jména elementů v XML rozlišují malá a velká písmena: např. `<Příklad>` a `</Příklad>` je pár, který vyhovuje správně strukturovanému dokumentu, pár `<Příklad>` a `</příklad>` je chybný.

Jednoduchý recept v XML jako příklad by mohl vypadat takto:

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!-- Poznamka je nutné přidat více receptů. -->
<recept jméno="chleba" čas_přípravy="5 minut" čas_vaření="3 hodiny">
  <titulek>Jednoduchý chleba</titulek>
  <přísada množství="3" jednotka="šálky">Mouka</přísada>
  <přísada množství="0,25" jednotka="unce">Kvasnice</přísada>
  <přísada množství="1,5" jednotka="šálku">Horká voda</přísada>
  <přísada množství="1" jednotka="kávová lžička">Sůl</přísada>
  <postup>
    <krok>Smíchejte všechny přísady dohromady a dobře prohněťte.</krok>
    <krok>Zakryjte tkaninou a nechejte hodinu v teplé místnosti.</krok>
    <krok>Znovu prohněťte, umístěte na plech a pečte v troubě.</krok>
  </postup>
</recept>
```
