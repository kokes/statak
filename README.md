## Statak (DataStat mini viewer)

Jednoduchá statická HTML aplikace bez závislostí.
Načítá data z API DataStat (ČSÚ), umí:

- vyhledat datovou sadu (fuzzy, bez ohledu na diakritiku),
- přepnout `Sestava` mezi celou sadou a předdefinovaným výběrem,
- zobrazit tabulku a měnit osy (`Řádky` / `Sloupce`) a filtry.

## Spuštění

Stačí otevřít `index.html` v prohlížeči.

## Trvalý odkaz (permalink)

Stav výběru se průběžně zapisuje do URL query parametrů.
Můžeš tedy URL zkopírovat a otevřít později / poslat dál.

Použité parametry:

- `d` - kód datové sady
- `dv` - verze datové sady
- `s` - kód předdefinovaného výběru (pokud je zvolen)
- `r` - dimenze na řádcích
- `c` - dimenze ve sloupcích
- `f` - JSON objekt filtrů (dimenze -> kód položky)

V UI je také tlačítko `Kopírovat odkaz`.

## API odkazy

- High-level docs:  
  https://csu.gov.cz/zakladni-informace-pro-pouziti-api-datastatu
- Katalog sad:  
  https://data.csu.gov.cz/api/katalog/v1/sady
- Swagger (katalog):  
  https://data.csu.gov.cz/api/katalog/v1/swagger-ui/index.html
- Swagger (dotaz/data):  
  https://data.csu.gov.cz/api/dotaz/v1/swagger-ui/index.html
