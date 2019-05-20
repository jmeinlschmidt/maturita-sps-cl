# 24/25 - Bezpečnost - záloha a obnova dat
## Zadání
-	Bezpečnost - záloha a obnova dat

## Vypracováno

### 1. Úvod
- **základní bezpečností prvek je prevence proti ztrátě dat**
- důvody zálohování dat
    - chyba HW - přílišná důvěra v neporuchovost disků
    - ochrana před zničením (viry, uživatelé, živelná pohroma)
- jak zálohovat - ručně / pomocí zálohovacího SW
- **druhy záloh**
    - plná záloha - vše tak jak je, jeden velký balík
    - rozdílová záloha - možnost zálohovat pouze změny, neplýtvá místem na disku
- výběr zálohy
    - zálohovat celý PC/server - **nepraktické**
    - uspornější - *selektivní zálohy*
        - podle typu stanice (server / koncový PC)
        - podle typu dat (databáze, konfigurační soubory)
        - podle umístění (adresáře)

### 2. Lokální PC
    - domovské adresáře uživatelů `/home`
    - pošta uživatelů `/var/mail` (zjistit dle SW)
    - data z databází
    - seznam nainstalovaného SW (balíčkovací systém)
    - extra software mimo balíčkovací systém `/opt`
    - konfigurace `/etc`
    - logy - většino nejsou nutné
    - databáze monitorovacích nástrojů `/var/lib`
    
#### 2.1 Kam ukládat
1. Do určeného adresáře (poškození disku = ztráta dat; *lepší než nic...*) 
2. Druhý logický disk (o trochu lepší než první varianta, ale pořád hrozí poškození disku)
3. Druhý fyzický disk (ochrana před poškozením prvního disku, ale pořád součást toho samého PC)
4. 
