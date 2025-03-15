# SQL-Python-Datasets-Analysis-Project




## **Project Overview**
This project analyzes three datasets from the City of Chicago using SQL and Python. The goal is to extract meaningful insights by storing the data in an SQLite database and executing SQL queries.

## **Datasets Used**
1. **Socioeconomic Indicators in Chicago**  
   - Contains six indicators of public health significance and a hardship index for each Chicago community area.  
   - Source: [Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2)

2. **Chicago Public Schools**  
   - Includes performance data for Chicago Public Schools for the 2011-2012 school year.  
   - Source: [Chicago Data Portal](https://data.cityofchicago.org/Education/Chicago-Public-Schools-Progress-Report-Cards-2011-/9xs2-f89t)

3. **Chicago Crime Data**  
   - Contains reported crime incidents in Chicago from 2001 to the present.  
   - Source: [Chicago Data Portal](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-present/ijzp-q8t2)

## **Technologies Used**
- **Python (Pandas, SQLite3)**
- **SQL (SQLite)**
- **Jupyter Notebook**

## **Project Steps**
1. **Data Extraction & Storage**
   - Loaded datasets into Pandas DataFrames.
   - Stored data in an SQLite database (`FinalDB.db`) with three tables:
     - `CENSUS_DATA`
     - `CHICAGO_PUBLIC_SCHOOLS`
     - `CHICAGO_CRIME_DATA`

2. **SQL Queries & Analysis**
   - Queried crime trends, school safety scores, and community hardship levels.
   - Used aggregation functions, subqueries, and filtering techniques.

3. **Key Findings**
   - Community areas with the highest poverty levels were identified.
   - Schools were analyzed for safety scores.
   - Most crime-prone areas were determined.

## **Example SQL Queries**
- **Total number of recorded crimes**  
  ```sql
  SELECT COUNT(*) FROM CHICAGO_CRIME_DATA;
  ```
- **List of community areas with per capita income < $11,000**  
  ```sql
  SELECT COMMUNITY_AREA_NUMBER, COMMUNITY_AREA_NAME 
  FROM CENSUS_DATA 
  WHERE PER_CAPITA_INCOME < 11000;
  ```
- **Community area with the highest hardship index**  
  ```sql
  SELECT COMMUNITY_AREA_NAME 
  FROM CENSUS_DATA 
  WHERE HARDSHIP_INDEX = (SELECT MAX(HARDSHIP_INDEX) FROM CENSUS_DATA);
  ```

## **How to Run**
1. Clone this repository.  
   ```bash
   git clone <repository-link>
   cd <repository-folder>
   ```
2. Install required dependencies (if using Jupyter Notebook):  
   ```bash
   pip install pandas sqlite3
   ```
3. Open the Jupyter Notebook and run the provided Python script to set up the database.
4. Execute SQL queries to analyze data.


