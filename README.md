# Capstone-Project-2
HR Analytics: Attrition Analysis Using SQL
This project is designed to explore and analyze attrition in a company’s HR dataset using SQL. The primary focus is to calculate and analyze attrition rates by different factors such as gender, department, age, monthly income, years at the company, and more. The dataset is processed and stored in an SQLite database to run SQL queries efficiently.

Project Overview
The project consists of various stages:

Data Retrieval and Preprocessing: Initially, we load a CSV file containing the HR dataset and store it in an SQLite database.
Exploratory Data Analysis: We perform various SQL queries to extract insights into the attrition patterns in the company.
Key Steps and SQL Queries
1. Database Creation
We use SQLite3 to create a local database and load the dataset into it using the pandas.to_sql() function. This step converts the raw data into a structured format, enabling us to perform SQL queries.

Objective: Create a SQLite3 database and load the data.

2. Attrition by Gender
In this query, we calculate the attrition rate by gender (Male, Female). The query groups employees by gender and attrition status, calculating the attrition percentage for each gender.

SQL Query:

Uses CASE statements to classify attrition as "Yes" or "No".
The query computes the number of employees who left within each gender group and the attrition rate as a percentage.
3. Attrition by Department
Here, we calculate the attrition rate per department. We determine the total number of employees in each department and the number of employees who left.

SQL Query:

Uses SUM(CASE WHEN Attrition = 'Yes' THEN 1 ELSE 0 END) to count employees who left.
The attrition rate is calculated by dividing the number of employees who left by the total number of employees in that department.
4. Attrition by Age Groups
We categorize employees by age into specific ranges such as <30, 30-39, 40-49, and >50. The query then calculates the attrition rate for each age group.

SQL Query:

Utilizes CASE statements to group ages into categories.
Groups the data by age and attrition status and computes the attrition percentage for each age group.
5. Attrition by Monthly Income and Job Level
This query analyzes the relationship between monthly income and attrition, comparing the average income of employees who left versus those who stayed. It groups the data by job level and department.

SQL Query:

The average monthly income is calculated for both employees who left (attrition = 'Yes') and those who stayed (attrition = 'No').
The difference in income between the two groups is computed to analyze whether income influences attrition.
6. Attrition by Years at the Company
Employees are grouped by their tenure at the company (e.g., 0 years, 2-5 years, 6-10 years, >20 years). The query calculates attrition rates within each tenure group.

SQL Query:

Uses CASE statements to categorize tenure.
Groups employees by tenure and attrition status, then computes the attrition rate within each group.
7. Exploring Key Reasons for Attrition
We perform a deeper analysis into why certain age groups (e.g., employees over 50) have higher attrition rates than others, or why employees with higher pay may still leave.

SQL Queries:

Age-based Attrition: Compares the attrition rates of employees aged 40-50 and those over 50, to uncover potential causes such as retirement or health issues.
Income-based Attrition: Investigates why employees with higher incomes might still leave by examining the attrition rates across different job levels.
Key Learnings
SQL Techniques Used:
Aggregation: Using functions like COUNT(), SUM(), and AVG() to summarize data.
Group By: Grouping the data based on different attributes such as gender, department, age, and tenure to calculate attrition rates.
Window Functions: Using ROW_NUMBER() and PARTITION BY to order and calculate attrition rates across different subgroups.
Case Statements: Categorizing data into age groups or attrition statuses using SQL CASE statements.
Insights Gained:
The attrition rate varies significantly by department and age group.
Employees in certain age ranges (e.g., over 50 years old) have higher attrition rates, possibly due to retirement or other personal reasons.
Income does not seem to be a strong driver for attrition across all job levels; instead, tenure and department factors play a larger role in influencing turnover.
