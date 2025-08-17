# Vaccination-Coverage-Dashboard

Dataset Source: https://catalog.data.gov/dataset/vaccination-coverage-among-adults-18-years-dc087


Tools Used: Pandas(Python library), Jupyter Notebook IDE, Tableau

## Process

### Objective 
- To visualise vaccination coverage trends over time, across geographies and demographic dimensions and year-over-year changes

### Before Starting: Background Information

- 'NR' or '*' in Estimate column means that data was not collected. 
- The dataset is pre-processed, requiring no additional data cleaning before analysis

Brief look-through of dataset in Excel:

- Removed FIPS column
- Used Filter to confirm that there are no errorneous values in each column

<img width="400" height="150" alt="image" src="https://github.com/user-attachments/assets/c7a1551a-8123-472d-a882-d487be7af475" />

### 1. Data Wrangling:  Querying and Manipulation with Pandas 

Used Pandas in Jupyter Notebook IDE to obtain the various tables:

- Table 1: Average estimate (%) by Survey Year and Vaccine as average_est_vacc
  
- Table 2: Average Estimate by Geography and Survey Year as est_by_geog

   We map each state(Column: 'States/Local Areas') map to their HHS Region(Column: 'HHS Region/National') to enable hierarchical drill-down in Tableau (HHS Region level -> Expand to view at State level)

- Table 3: Average estimate by age group and Survey Year, as average_est_dimtype
  
- Table 4: Average estimate by race/ethnicity as average_est_dim

- Table 5: Year on year percentage change in Average Estimate by Vaccine, as average_est_yoy
 
 
 
<img width="500" height="230" alt="image" src="https://github.com/user-attachments/assets/cd91e8ef-b82c-45d8-949a-d3f1e5e7002e" />

(Full code and comments in vaccination_coverage.ipynb)


### 2. Building Dashboard with Tableau 

File: Vaccination_Coverage_Dashboard.twb

Features/Visuals: Line graph, Filed map, Filter/Slicer, Hierarchical drill-down, Table with KPI indicator/shape & color encoding

Page 1: Line Graph, Filled Map


<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/618d124d-b2f9-40c1-bb73-68912a3c7546" />


Hierarchical drill-down available for Line graph and Map; can also hover over regions on the map to view Average Estimate:


<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/fd4548a1-c386-4c86-9157-fe95bb96e01d" />

Page 2: Line graph, Table


<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/e70bce78-4c9a-49ef-aed7-08719170f01f" />


### Insights and Conclusions 

- Vaccination coverage for all 3 vaccines(Pneumococcal, Tetanus, Zoster(Shingles)) has generally increased from 2008 to 2023
  
- Trend in vaccination coverage over the years is relatively similar across geography, race/ethnicity and age group; Notable drop from 2019 to 2020 but subsequently increased
    
- Coverage has slightly decreased from 75.78% in 2009 to 68.80% in 2023 for adults 18 to 49 years old

- Year-on-year changes show that vaccination coverage is generally strong and growing. Occasional declines occur, but they are short-lived, typically resolving within one to two years, indicating overall program resilience
