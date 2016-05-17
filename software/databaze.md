# Databáze a dotazovací jazyk SQL

## Co jsou databáze

Databáze slouží pro uchovávání většího množství informací v určité formě. V databázi lze poté vybírat data podle specifických kritérií a následně s nimi pracovat v aplikaci. Pro ulehčení a zrychlení vyhledávání se využívá tzv. index.

Databáze se využívají jak pro webové aplikace, tak i pro aplikace desktopové. Pro přístup do databáze se musí vytvořit propojení, které se po dotazování musí zase ukončit.

## SQL

SQL je jazyk využívající se pro dotazování nad databází, tzn. pravidla pro výběr položek podle různých kritérií. Lze využívat příkazů jako např.:

- `show databases` - výpis databází
- `create database jmeno_databaze` – vytvoření databáze
- `use jmeno_databaze` – výběr databáze
- `drop database jmeno_databaze` – vymazání databáze
- `create table jmeno_tabulky (definice sloupcu...);` - vytvoření tabulky databáze 
- `show tables` – výpis tabulek
- `drop table jmeno_tabulky` – smazání tabulky
- `insert into tabulka set sloupec='hodnota'` – vložení dat do tabulky
- `describe tabulka` – popis tabulky
- `update tabulka set sloupec='hodnota' where podminka` – úprava všech položek tabulky, které splňují podmínku
- `delete from tabulka where podminka` – vymazet všechny položky tabulky, které splňují podmínku
- `select sloupce from tabulky where podminka` – vybrat všechny položky tabulky, které splňují podmínku
- `select * from tabulky` – vybrat všechny položky tabulky
