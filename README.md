# Power BI Dashboard

## Úvod
Toto je složka mapující mou cestu v Power BI. 
Prošla jsem kompletní a podrobný tutoriál od Luka Barousse – https://www.youtube.com/watch?v=FwjaHCVNBWA 
Při průchodu tutoriálem jsem vytvářela tyto power BI soubory v desktopové aplikaci:

- `Dashboard - Example - job market.pbix` je soubor, který jsem vytvořila během učení se vizualizacím v Power BI. 

- `Better Dashboard.pbix` jsem také vytvářela s tutoriálem ale již jsem si ji upravovala ji dle svých preferencí. 

Datovou modelaci jsem provedla v Power Query a **samostatně**, protože tento nástroj znám z Excelu.

___

## Prezentované dovednosti
- **ETL – Transformace dat pomocí Power Query:** Příprava surových dat, přiřazování datových typů, čištění, vytváření nových sloupců, ošetření prázdných hodnot, dimenzionální modelování/normalizace.
- **Vizualizace:** Sloupcové grafy, pruhové grafy, spojnicové grafy, karty, filtry, průřezy (slicers), koláčové grafy, prstencové grafy, KPI karty, prokliky (drill-through), tlačítka...
- **Design dashboardu:** Návrh intuitivního a vizuálně atraktivního dashboardu s využitím prokliků, tlačítek, záložek (bookmarks), průřezů, dynamických filtrů...

## Better Dashboard
### Vizualizace
#### -- Hlavní dashboard -- 
![Dashboard page 1](/Images/Better%20Dashboard/Dashboard%20page%201.png)
- Celkový počet nabídek práce
- Hvězdičkové hodnocení mediánu platů v těchto oborech
- Medián pro roční a hodinovou mzdu v $
- Spojnicový graf zobrazuje trendy v počtu nabídek práce v oblasti dat v roce 2024
- Pruhový graf ukazuje názvy pozic a jejich počty v roce 2024  
- Plotový graf zobrazuje, které pozice mají nejvyšší medián hodinových a ročních platů
- Kontingenční tabulka zobrazuje všechna tato data v tabulce (ikona +/- zobrazuje detail podle země).

![Dashboard page 1 - filtered](/Images/Better%20Dashboard/Dashboard%20page%201%20-%20filtered.png)
- Při kliknutí na názvy pozic se odblokují tlačítka pro detailní analýzy.
___

#### -- DETAIL POZICE --
![Dashboard drill through](/Images/Better%20Dashboard/Dashboard%20drill%20through.png)
 
- Měřidla ukazují medián ročních a hodinových platů, přičemž cílovou hodnotou je průměr uvedených nabízených platů.
- Prstencové grafy ukazují procentuální podíl pozic s konkrétními benefity.
- Mapa ukazuje, kde bylo v roce 2024 zveřejněno nejvíce nabídek
- Pruhový graf ukazuje, přes který portál byly pozice na internetu inzerovány
- Stromová mapa ukazuje podíly typů úvazků u nabídek práce.
___

#### -- DETAIL PLATU POZICE --
![TITLE SALARY DETAIL](/Images/Better%20Dashboard/Dashboard%20drill%20through%202.png)

- Pruhový graf ukazuje srovnání mezi inzeráty s roční a hodinovou sazbou
- Spojnicový graf ukazuje platové trendy v inzerátech práce v průběhu roku
- Karty ukazují míru chybějících platových hodnot u inzerátů – je nastaveno podmíněné formátování pro spodní hranici 80 % (většině nabídek chybí informace o platu).
___
___

### Dimenzionální modelování v Better Dashboard
#### -- PŮVODNÍ SCHÉMA (RAW) --
![RAW SCHEMA](/Images/Better%20Dashboard/Dimensional%20modeling%20part%201.png)

#### -- FINÁLNÍ SCHÉMA --
![FINAL SCHEMA](/Images/Better%20Dashboard/Dimensional%20modeling%20part%202.png)

- Přidána dimenze pro unikátní názvy firem, unikátní dovednosti (skills) a propojovací tabulka (bridging table) s ID inzerátu a dovednostmi uvedenými u každé nabídky.
- **Vztahy:** many-to-one (mnoho k jedné), many-to-many (mnoho k mnoha).
- **Sloupce:** ID_postings, ID_skills, ID_company_name
- **Rychlá míra:** Salary Star Rating, HOURLY_SALARY_MISSING_VALUES, YEARLY_SALARY_MISSING_VALUES
