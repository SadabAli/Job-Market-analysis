# PRDA-04: Job Market Analysis

## Project Overview
**Job Market Analysis** is a Power BI project that analyzes **742 job-market records across 42 features** to understand job distribution, salary patterns, industries, companies, job titles, education requirements, and company characteristics.

The project uses **Power Query** for data cleaning and transformation, **DAX** for KPI calculations, and **Power BI** for interactive visualization and business analysis.

## Business Questions
1. Which states have the highest number of job postings?
2. What are the average minimum and maximum salaries by state?
3. What is the average salary by state?
4. Which industries have the highest number of job postings?
5. Which companies have the maximum job openings?
6. Which job titles have the most job postings?
7. What is the average salary of the most common job titles?
8. How does average salary vary by education requirement?
9. How does average salary vary across company revenue groups?
10. What is the distribution of job postings by company ownership type?
11. Is there a visible relationship between company rating and average salary?
12. How are job records distributed according to company founding year?

## Dataset
- **Rows:** 742
- **Features:** 42
- **Tool:** Microsoft Power BI
- **Data Preparation:** Power Query
- **Analysis:** DAX
- **Salary Unit:** USD thousands (K)

Important fields include Job Title, Company Name, Rating, Location, Headquarters, Founded, Type of Ownership, Industry, Sector, Revenue, Lower Salary, Upper Salary, Avg Salary(K), skill indicators, seniority, and Degree.

The source dataset uses **-1 for unavailable information**. Numeric -1 values were converted to null and categorical -1 values were represented as NA/Not Available.

## Data Cleaning & Preparation
Power Query was used to:
- Remove the empty `FIELD4` column.
- Clean `Company_Name` by removing trailing rating text.
- Convert Python, Spark, AWS, Excel, SAS, MATLAB, R, Power BI, Tableau, Azure, and SQL fields to numeric 0/1 indicators.
- Convert unavailable numeric `-1` values to null.
- Convert unavailable categorical `-1` values to `NA`.
- Split Location and Headquarters into city and state fields.
- Retain `Lower_Salary`, `Upper_Salary`, and `Avg_SalaryK` as numeric salary fields.
- Keep Revenue as categorical ranges rather than creating artificial numeric values.

## DAX Measures

```DAX
Job Count = COUNTROWS(Sheet1)

Average Salary = AVERAGE(Sheet1[Avg_SalaryK])

Average Lower Salary = AVERAGE(Sheet1[Lower_Salary])

Average Upper Salary = AVERAGE(Sheet1[Upper_Salary])

Companies Hiring = DISTINCTCOUNT(Sheet1[Company_Name])
```

## Key Performance Indicators

| KPI | Value |
|---|---:|
| Total Job Postings | **742** |
| Companies Hiring | **343** |
| Average Minimum Salary | **74.75K USD** |
| Average Salary | **101.48K USD** |
| Average Maximum Salary | **128.21K USD** |

## Power BI Visualizations

The dashboard contains 12 analytical visualizations:

1. Top 10 States with Most Jobs — Bar Chart
2. Top 10 Job Titles with Most Jobs — Bar Chart
3. Top 10 Companies with Maximum Job Openings — Bar Chart
4. Top 5 Industries by Job Postings — Bar Chart
5. Average Salary by State — Bar Chart
6. Average Minimum & Maximum Salary by State — Clustered Column Chart
7. Average Salary of Top Job Titles — Bar Chart
8. Average Salary by Education Requirement — Column Chart
9. Average Salary by Company Revenue Group — Bar/Column Chart
10. Job Postings by Company Ownership Type — Donut Chart
11. Company Rating vs Average Salary — Scatter Chart
12. Job Postings by Company Founding Year — Line Chart

## Key Findings

- The dataset contains **742 job records** from **343 distinct companies**.
- California has the largest job-record count among the displayed top states, followed by Massachusetts and New York.
- Biotech & Pharmaceuticals is the largest displayed industry by job postings.
- Data Scientist is the largest displayed job-title category.
- MassMutual, Reynolds American, and Takeda Pharmaceuticals appear among the highest-opening companies in the displayed ranking.
- Overall average salary is **101.48K USD**.
- Average minimum salary is **74.75K USD**, while average maximum salary is **128.21K USD**.
- Salary levels vary across states, job titles, education categories, and revenue groups.
- The rating-versus-salary scatter chart shows variation but does not establish causation.

### Important Note About the Line Chart
The dataset does **not** contain a job-posting date/year. The `Founded` field represents the **company founding year**. Therefore, the line chart shows job records according to company founding year and should not be interpreted as actual job-posting growth over time.

## Business Suggestions

- Use state-level job concentration for geographic recruitment and market planning.
- Use industry and job-title concentration to guide talent sourcing and workforce planning.
- Use salary measures as broad benchmarks while considering state and title differences.
- Examine education categories separately for roles with degree-related requirements.
- Use revenue and ownership groups for company segmentation.
- Use the available skill indicators for deeper skill-demand analysis by job title.
- Refresh the Power BI dashboard when new job-market data becomes available.


## Tools & Technologies
- Microsoft Power BI
- Power Query
- DAX
- Data Cleaning
- Data Transformation
- Data Visualization
- KPI Analysis
- Business Analysis




## Conclusion
This project demonstrates an end-to-end Power BI workflow for converting raw job-market data into meaningful business insights. Power Query was used for data preparation, DAX for analytical measures, and Power BI for dashboard development.

The project demonstrates practical skills in **data cleaning, KPI development, business analysis, data visualization, Power Query, DAX, and Power BI**.

## Author
**Mir Sadab Ali**  
**Focus:** Data Analytics | Business Intelligence | Power BI | SQL | Python

