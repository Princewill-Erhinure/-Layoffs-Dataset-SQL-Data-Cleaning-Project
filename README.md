🧹 Layoffs Dataset – SQL Data Cleaning Project
This project focuses on cleaning and preparing a real-world dataset (Layoffs data) using structured SQL techniques. The dataset was messy — containing duplicates, inconsistent entries, null values, and formatting issues. I approached the cleaning process in a step-by-step, analyst-driven way, ensuring the data became clean, usable, and ready for analysis.

📌 Project Objectives
Clean and standardize the dataset for accurate analysis

Fix data integrity issues such as duplicates, nulls, and inconsistent formats

Demonstrate real-world SQL skills in data preparation

🛠️ Tools Used
SQL (MySQL syntax)

DBMS: Any platform that supports SQL-based querying

🧪 Cleaning Process Overview
1. Created a Staging Table
- Duplicated the original layoffs table to layoffs_staging to safely apply changes without affecting the source data.

2. Removed Duplicates Without a Unique ID
- Used ROW_NUMBER() OVER (PARTITION BY all columns) to identify duplicates

- Created a second staging table with row numbers (layoffs_staging2)

- Deleted records where row_num > 1 to keep only the first instance

3. Standardized Inconsistent Values
- Trimmed extra spaces in company and industry columns using TRIM()

- Standardized values such as:

- crypto, cryptocurrency, and crypto currency → unified as Crypto

- United States. → corrected to United States by removing trailing periods

4. Fixed Date Formatting Issues
- Original date column was in text format

- Used STR_TO_DATE(date_column, '%m/%d/%y') to convert to valid date values

- Applied ALTER TABLE to change the column to the proper DATE type

5. Handled Nulls and Blank Fields
- Identified and filled missing values by joining with similar rows (e.g., Airbnb)

- Deleted rows with nulls in key columns (total_laid_off, percentage_laid_off) when recovery wasn’t possible

6. Final Cleanup
- Dropped temporary columns like row_num after cleaning

- Ran final verification to ensure data was fully clean and analysis-ready

📈 Outcome
The final dataset is structured, consistent, and free from major data quality issues.
This makes it suitable for downstream analysis, visualization, or dashboarding in tools like Excel, Power BI, or Tableau.

💡 Key Learnings
How to clean real-world data without relying on unique IDs

Handling messy text, formatting, and missing values with precision

Importance of staging tables and step-by-step transformation tracking
