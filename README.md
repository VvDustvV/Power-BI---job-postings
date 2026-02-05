# Power BI Dashboard

## Introduction
This is folder with my Power BI journey. 
I went through the whole comprehensive tutorial from Luke Barousse - https://www.youtube.com/watch?v=FwjaHCVNBWA 
Dashboard - Example - job market.pbix is a file I created when learning about visualisations in Power BI. 

Better Dashboard.pbix has been created lated as an expample of usable dashboard.  
Data modulation was done through Power Query separately from the tutorial as I know this tool from excel.

___

## Skills Showcased
- **ETL - Data transformation with Power Query:**  
Preparation of raw data, assigning data types, cleaning, creating new collumns, handling blanks, dimensional modeling/normalisation
- **Visualisation:**  
Collumn charts, bar charts, line charts, cards, filters, slicers, pie charts, donut charts, KPI cards, Drill throughs, buttons,...
- **Dashboard design:**  
Designed intuitive and visually appealing dashboard with drill throughs, buttons, bookmarks, slicers, dynamic filters...

## Better Dashboard
### Visualisation
#### -- Main dashboard -- 
![Dashboard page 1](/Images/Better%20Dashboard/Dashboard%20page%201.png)
- Total count of job postings
- Star rating of median salaries in these fields 
- Median for yearly salary and hourly salary in $
- Line chart displays the trends in data job postings in 2024 
- The bar chart shows job titles and their counts in 2024  
- The scatter plot shows which titles have the highest median of hourly and yearly salaries
- The pivot table displays all these data in table (+/- Ikon shows country detail)

![Dashboard page 1 - filtered](/Images/Better%20Dashboard/Dashboard%20page%201%20-%20filtered.png)
- When clicking on job title, the drill through buttons are unblocked and we can look at the detail.
___

#### -- TITLE DETAIL DRILL THROUGH --
![Dashboard drill through](/Images/Better%20Dashboard/Dashboard%20drill%20through.png)
 
- Gauche charts show the median yearly and hourly salaries with goal being the average
- Donut charts show percentage proportions of jobs with particular benefits
- Map chart shows where were the most jobs with filtered job title posted in 2024
- Bar chart shows via which site were the jobs posted on the internet
- Tree map chart shows the proportions of schedule types of job postings
___

#### -- TITLE SALARY DETAIL DRILL THROUGH --
![TITLE SALARY DETAIL](/Images/Better%20Dashboard/Dashboard%20drill%20through%202.png)

- Bar chart shows comparison between postings with yearly and hourly rates
- Line chart shows salary trends in job bostings through year
- Cards show the rate of missing values for values with salary - there is a conditional formating set for bottom value of 80% (majority of posings is missing information about salary)
___
___

### Dimensional modeling behind Better Dashboard
#### -- RAW SCHEMA --
![RAW SCHEMA](/Images/Better%20Dashboard/Dimensional%20modeling%20part%201.png)

#### -- FINAL SCHEMA --
![FINAL SCHEMA](/Images/Better%20Dashboard/Dimensional%20modeling%20part%202.png)

- Added dimension for unique company names, unique skills and bridging table with posting ID and skills listed with each posting
- **Relationships:** many-to-one, many-to-many
