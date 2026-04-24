## Statak (DataStat mini viewer)

Jednoduchá statická HTML aplikace pro procházení dat z DataStat API (ČSÚ).

## Co aplikace umí

- vyhledání datové sady přes substring match bez ohledu na diakritiku (plovoucí dropdown),
- načtení detailu sady a přepínání `Sestava` mezi:
  - `Celá sada`,
  - předdefinovanými výběry (`vybery`),
- lazy načítání dat (primárně přes vybranou sestavu, bez nuceného načítání celé velké sady),
- interaktivní tabulku s volbou os `Řádky` / `Sloupce` a filtry dimenzí,
- blokaci kolizí os (stejná dimenze nejde vybrat zároveň do řádků i sloupců),
- bezpečné chování pro `(vše)` u ne-osových dimenzí (fallback na validní kód položky),
- line chart přes Chart.js, který vždy odpovídá aktuální tabulce:
  - série lze zapínat/vypínat klikem v legendě,
  - volba `Ukotvit osu Y na 0` (defaultně vypnuto),
- průběžně aktualizovaný permalink + tlačítko `Kopírovat odkaz`,
- české texty UI + `Accept-Language: cs` pro API volání,
- footer s jasným uvedením zdroje dat a disclaimerem bez afiliace.

## Spuštění

Stačí otevřít `index.html` v prohlížeči.

## Trvalý odkaz (permalink)

Stav výběru se průběžně zapisuje do URL query parametrů, takže aktuální pohled lze sdílet odkazem.

Použité parametry:

- `d` - kód datové sady
- `dv` - verze datové sady
- `s` - kód sestavy (`vyber`), pokud je zvolen
- `r` - dimenze na řádcích
- `c` - dimenze ve sloupcích
- `f` - JSON objekt filtrů (`{ dimenze: kodPolozky }`)

## Chart.js a bezpečnost načítání

Chart.js je načítaný z CDN jako připnutá verze s kontrolou integrity:

- `https://cdn.jsdelivr.net/npm/chart.js@4.5.1/dist/chart.umd.min.js`
- `integrity="sha384-jb8JQMbMoBUzgWatfe6COACi2ljcDdZQ2OxczGA3bGNeWe+6DChMTBJemed7ZnvJ"`
- `crossorigin="anonymous"`

Tím se zabrání použití nečekaně změněného souboru při načítání z CDN.

## API odkazy

- High-level docs: [https://csu.gov.cz/zakladni-informace-pro-pouziti-api-datastatu](https://csu.gov.cz/zakladni-informace-pro-pouziti-api-datastatu)
- Katalog sad: [https://data.csu.gov.cz/api/katalog/v1/sady](https://data.csu.gov.cz/api/katalog/v1/sady)
- Swagger (katalog): [https://data.csu.gov.cz/api/katalog/v1/swagger-ui/index.html](https://data.csu.gov.cz/api/katalog/v1/swagger-ui/index.html)
- Swagger (dotaz/data): [https://data.csu.gov.cz/api/dotaz/v1/swagger-ui/index.html](https://data.csu.gov.cz/api/dotaz/v1/swagger-ui/index.html)
