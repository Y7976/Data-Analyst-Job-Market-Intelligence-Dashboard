# Data Analyst Job Market Intelligence
![image alt](https://github.com/Y7976/Data-Analyst-Job-Market-Intelligence-Dashboard/blob/9e7a3d489a8dcfa01b234200652f9488385688ad/data_analyst_job_intellegence.png)
##  Project Overview

The **Data Analyst Job Market Intelligence** project analyzes job postings to identify hiring trends, salary patterns, in-demand skills, and top recruiting companies. The goal is to transform raw job market data into actionable insights for job seekers, students, and recruiters using **SQL, Python, and Power BI**.

---

##  Project Objectives

- Analyze current trends in the Data Analyst job market.
- Identify the most demanded technical and soft skills.
- Discover top hiring companies and locations.
- Analyze salary distributions across different roles.
- Build interactive dashboards for business insights.
- Develop a machine learning model to predict salaries.

---

##  Dataset Information

The dataset contains job postings collected from various job portals and includes information about companies, locations, salaries, job descriptions, and required skills.

### Dataset Columns

| Column Name | Description |
|------------|-------------|
| Job_Title | Title of the job position |
| Company_Name | Name of the hiring company |
| Location | Job location |
| Employment_Type | Full-time, Part-time, Contract, Internship |
| Experience_Level | Entry, Mid, Senior |
| Salary_Min | Minimum offered salary |
| Salary_Max | Maximum offered salary |
| Average_Salary | Average salary calculated from salary range |
| Skills | Required technical skills |
| Industry | Industry category |
| Remote_Work | Remote or On-site job |
| Job_Posted_Date | Date when job was posted |
| Job_Description | Detailed job description |
| Education_Required | Required educational qualification |

---

## 🛠️ Tools & Technologies Used

| Tool | Purpose |
|--------|---------|
| Python | Data Cleaning & Analysis |
| Pandas | Data Manipulation |
| NumPy | Numerical Operations |
| Matplotlib | Data Visualization |
| Seaborn | Statistical Visualization |
| SQL | Data Querying & Analysis |
| Power BI | Interactive Dashboard |
| Scikit-Learn | Machine Learning |

---

#  Data Cleaning & Preprocessing

The following preprocessing steps were performed:

###  Missing Value Treatment
- Removed rows with excessive missing values.
- Filled missing salary values where applicable.

###  Duplicate Removal
- Identified and removed duplicate job postings.

###  Data Type Conversion
- Converted salary columns into numeric format.
- Converted posting dates into datetime format.

###  Feature Engineering
- Created Average Salary column.
- Extracted skill frequencies.
- Standardized location names.

###  Text Processing
- Cleaned job descriptions.
- Removed unnecessary special characters.
- Standardized skill names.

---

#  Exploratory Data Analysis (EDA)

The dataset was analyzed to answer key business questions.

## 1. Total Number of Job Postings

- Calculated total available jobs in the dataset.
- Measured overall market demand.

## 2. Top Hiring Companies

- Identified companies posting the highest number of jobs.
- Ranked companies based on hiring frequency.

## 3. Top Hiring Locations

- Determined cities with maximum job opportunities.
- Compared job availability across locations.

## 4. Most In-Demand Skills

- Extracted skills from job postings.
- Counted frequency of each skill.
- Ranked skills by demand.

### Most Common Skills Identified

- SQL
- Python
- Power BI
- Excel
- Tableau
- Machine Learning
- Statistics
- Data Visualization

## 5. Salary Analysis

- Minimum Salary Distribution
- Maximum Salary Distribution
- Average Salary Analysis
- Salary Comparison by Location
- Salary Comparison by Experience Level

## 6. Employment Type Analysis

- Full-Time Jobs
- Contract Jobs
- Internship Positions
- Remote Opportunities

## 7. Experience Level Analysis

- Entry-Level Jobs
- Mid-Level Jobs
- Senior-Level Jobs

---

#  SQL Analysis Performed

The following SQL operations were used:

### Aggregate Functions

- COUNT()
- SUM()
- AVG()
- MIN()
- MAX()

### Grouping Operations

- GROUP BY
- HAVING

### Sorting Operations

- ORDER BY

### Filtering Operations

- WHERE Clause

### Ranking Operations

- ROW_NUMBER()
- RANK()
- DENSE_RANK()

### Window Functions

- OVER()
- PARTITION BY()

### Common Table Expressions (CTEs)

- Used for advanced business analysis.

---

#  Power BI Dashboard

An interactive dashboard was developed to visualize key insights.

### Dashboard KPIs

- Total Job Postings
- Average Salary
- Top Hiring Company
- Top Hiring Location
- Most Demanded Skill
- Remote Job Percentage

### Dashboard Visuals

- KPI Cards
- Bar Charts
- Line Charts
- Pie Charts
- Treemaps
- Skill Distribution Charts
- Salary Trend Analysis
- Hiring Company Analysis

---

#  Machine Learning Model

A Linear Regression model was built to predict salary trends.

### Steps Performed

1. Feature Selection
2. Data Encoding
3. Train-Test Split
4. Model Training
5. Prediction
6. Performance Evaluation

### Model Performance

| Metric | Value |
|----------|----------|
| R² Score | 0.94 |

### Interpretation

- The model explains approximately **94% of salary variance**.
- Indicates strong predictive performance.

---

#   Insights

### Hiring Trends

- Data Analyst roles continue to show strong demand.
- Technology companies contribute the highest number of job postings.

### Skills Demand

- SQL and Python are the most frequently requested skills.
- Power BI and Tableau remain highly valued visualization tools.

### Salary Insights

- Senior-level positions offer significantly higher salaries.
- Remote positions often provide competitive compensation.

### Geographic Trends

- Major metropolitan areas have the highest concentration of opportunities.

---

#  Business Impact

This project helps:

### Job Seekers
- Identify high-demand skills.
- Understand salary expectations.
- Target high-opportunity locations.

### Recruiters
- Analyze talent demand trends.
- Benchmark compensation strategies.

### Educational Institutions
- Align training programs with industry requirements.

---




---

#  Author

**Yasmin**  
Aspiring Data Analyst | SQL | Python | Power BI | Machine Learning

---
 If you found this project useful, consider giving it a star.
