### HR People Analytics Dashboard

### Overview

- An end-to-end HR analytics project covering data extraction, cleaning, and visualisation for a 22,000+ employee workforce dataset. Data was pulled from a
MySQL database, cleaned and validated in Python, and visualized through an interactive Power BI dashboard to surface workforce composition, hiring trends, and diversity metrics.

#### Tools & Technologies
#### Database: MySQL

- Extraction & Cleaning: Python (PyMySQL, SQLAlchemy, Pandas)
- Visualization: Power BI (DAX measures,calculated columns)
- Core Skills: Data Cleaning & Transformation, KPI Design, Data Visualization, DAX

### Dataset

A single-table HR dataset ( HR ) containing 22,214 employee records, including demographic details, department, job title, location, hire date, and termination date.

### Data Cleaning Steps

- Converted birthdate , hire_date , and term_date from text to proper datetime format

- Resolved a timezone inconsistency on term_date (stripped an unintended UTC tag to match other date columns)

- Identified and reclassified 1,053 records with invalid future-dated terminations as Active employees (verified against age and role data —ruled out retirement as an explanation)

- Validated null values across all columns: 
birthdate : ~61% missing- non-blocking, as Age was fully populated and used instead
term_date : nulls confirmed as expected (represents currently active employees, not a data gap)
Confirmed zero duplicate records

#### Dashboard Contents
  5 KPIs (built with custom DAX measures):

- Total Headcount
- Average Age
- Remote vs. HQ Employee %
- Turnover Rate
- Average Tenure (years)

##### Visualizations:

- Hiring trend line chart (by year)
- Gender distribution donut chart
- Bar charts: employees by state, by department, by race

#### Key Insights

- Hiring volume has remained stable (1,050–1,150/year) from 2001–2019, with no clear growth or decline trend

- Gender distribution is close to balanced (Male 50.8%, Female 46.5%, Non-Conforming 2.7%)

- Engineering is the largest department by a significant margin (~30% of total headcount)

- Workforce is heavily concentrated in Ohio, consistent with a single-headquarters operating model

- Turnover rate (12.95%) paired with a strong average tenure (14.49 years) suggests a generally stable, long-tenured workforce

#### Repository Structure

---> HR_cleaned.csv # Cleaned dataset (excluded from repo. see note below)

-----> HR_Analytics_Report.pdf #Full written analysis, insights, and
recommendations

--------> HR_Dashboard.pbix #Power BI dashboard file

------------> README.md #This file

#### How to Reproduce

1. Extract the source data from your own MySQL instance using Python (PyMySQL/SQLAlchemy), see cleaning steps above for the required transformations.

2. Load the cleaned CSV into Power BI Desktop.

3. Recreate the DAX measures listed under Dashboard Contents, or open
HR_Dashboard.pbix directly if included.

#### Notes

- No real database credentials or connection strings are included in this repository.

- Raw/cleaned data files are excluded by default - add your own via .gitignore if publishing this repo.

- This project was completed as part of a data analytics certification (DataMites, IABAC-accredited).

#### Author
- Ajith Kumar
- GitHub: github.com/Aj-Jude-Dot