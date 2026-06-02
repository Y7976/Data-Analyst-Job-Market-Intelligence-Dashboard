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
##  Why This Project?

I chose this project because it combines multiple Data Analytics skills into a single real-world business problem. The project focuses on analyzing job market trends, identifying in-demand skills, understanding salary patterns, and predicting salaries using Machine Learning.

This project allowed me to:
- Apply SQL for business-oriented data analysis.
- Perform data cleaning, EDA, and statistical analysis using Python.
- Build interactive dashboards in Power BI.
- Develop a Linear Regression model for salary prediction.
- Generate actionable insights from job market data.

By working on this project, I gained hands-on experience across the complete data analytics workflow, from data processing and visualization to predictive modeling.

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

##  Tools & Technologies Used

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
```python
total_jobs = jobs.shape[0]
total_jobs
```
# Visualization
```python
plt.figure(figsize=(6,4))

sns.countplot(
    x='job_title',
    data=jobs
)

plt.title("Number of Jobs")
plt.xlabel("Job Title")
plt.ylabel("Count")

plt.show()
```
![image alt](https://github.com/Y7976/Data-Analyst-Job-Market-Intelligence-Dashboard/blob/922bd29aeb5472ee660a4ba004847b2a23e2d128/Total_jobs.png)
- Measured overall market demand.

## 2. Top Hiring Companies

- Identified companies posting the highest number of jobs.
```python
total_companies = jobs['company_name'].nunique()
total_companies
```
# Visualization
```python
plt.figure(figsize=(12,6))
sns.countplot(
    data=jobs,
    x='company_name',
    order=jobs['company_name'].value_counts().index
)

plt.title("Number of Job Postings by Company")
plt.xlabel("Company Name")
plt.ylabel("Count")

plt.xticks(rotation=45)

plt.show()
```
![image alt](https://github.com/Y7976/Data-Analyst-Job-Market-Intelligence-Dashboard/blob/922bd29aeb5472ee660a4ba004847b2a23e2d128/Number_of_companies.png)
- Ranked companies based on hiring frequency.

## 3. Top Hiring Locations

- Determined cities with maximum job opportunities.
```python
total_cities = jobs['location'].nunique()
total_cities
```
# Visualization
```python
plt.figure(figsize=(10,5))

sns.countplot(
    data=jobs,
    x='location',
    order=jobs['location'].value_counts().index
)

plt.title("Number of Jobs by City")
plt.xlabel("City")
plt.ylabel("Count")

plt.xticks(rotation=45)

plt.show()
```
![image alt](https://github.com/Y7976/Data-Analyst-Job-Market-Intelligence-Dashboard/blob/922bd29aeb5472ee660a4ba004847b2a23e2d128/Number_of_cities.png)
- Compared job availability across locations.
## 4. Average Salary

- Calculate average salary of the Data Analyst.
```python
avg_salary = round(jobs['salary_lpa'].mean(), 2)

print("Average Salary:", avg_salary)
```
# Visualization
```python
jobs['salary_range'] = pd.cut(
    jobs['salary_lpa'],
    bins=[0,5,10,15,20,25],
    labels=['0-5','5-10','10-15','15-20','20-25']
)

plt.figure(figsize=(8,5))

sns.countplot(
    x='salary_range',
    data=jobs
)

plt.title("Salary Distribution")
plt.xlabel("Salary Range (LPA)")
plt.ylabel("Number of Jobs")

plt.show()
```
![image alt](https://github.com/Y7976/Data-Analyst-Job-Market-Intelligence-Dashboard/blob/922bd29aeb5472ee660a4ba004847b2a23e2d128/Average_Salary.png)
## 5. Most In-Demand Skills

- Extracted skills from job postings.
- Counted frequency of each skill.
```python
top_skills = (
    skills.groupby('skill_name')
    .size()
    .reset_index(name='demand_count')
    .sort_values(by='demand_count', ascending=False)
)

top_skills.head(10)
```
- Ranked skills by demand.
# Visualization
```python
plt.figure(figsize=(10,5))

plt.bar(
    top_skills['skill_name'],
    top_skills['demand_count']
)

plt.title("Top 10 Most Demanded Skills")
plt.xlabel("Skills")
plt.ylabel("Demand Count")

plt.xticks(rotation=45)

plt.tight_layout()
plt.show()
```
![image alt](https://github.com/Y7976/Data-Analyst-Job-Market-Intelligence-Dashboard/blob/c1d1c3336c625c2d3ceb20d87098f1b4dfed5de7/Most_demand_skill.png)
### Most Common Skills Identified

- SQL
- Python
- Power BI
- Excel
- Tableau
- Machine Learning
- Statistics
- Data Visualization

## 6. Salary Analysis


- Salary Comparison by Location
```python
salary_by_city = (
    jobs.groupby('location')['salary_lpa']
    .mean()
    .reset_index()
)

salary_by_city['salary_lpa'] = salary_by_city['salary_lpa'].round(2)
salary_by_city = salary_by_city.sort_values(
    by='salary_lpa',
    ascending=False
)

salary_by_city.head(10)
```
- Salary Comparison by Experience Level
```python
salary_by_experience = (
    jobs.groupby('experience_level')['salary_lpa']
    .mean()
    .reset_index()
)

salary_by_experience['salary_lpa'] = salary_by_experience['salary_lpa'].round(2)
salary_by_experience = salary_by_experience.sort_values(
    by='salary_lpa',
    ascending=False
)

salary_by_experience.head(10)
```
# Visualization
```python
plt.figure(figsize=(8,5))

plt.bar(
    salary_by_experience['experience_level'],
    salary_by_experience['salary_lpa']
)

plt.title("Average Salary by Experience Level")
plt.xlabel("Experience Level")
plt.ylabel("Average Salary (LPA)")

plt.tight_layout()
plt.show()
```
![image alt](https://github.com/Y7976/Data-Analyst-Job-Market-Intelligence-Dashboard/blob/69ffa88a13eed9d9d54f0811557ef918e4c7ed38/salary%20by%20experience%20level.png)


## 7. Experience Level Analysis

- Entry-Level Jobs
- Mid-Level Jobs
- Senior-Level Jobs
```python
experience_analysis = (
    jobs.groupby('experience_level')
    .size()
    .reset_index(name='total_jobs')
    .sort_values(by='total_jobs', ascending=False)
)
experience_analysis.head(10)
```
# Visualization
```python
plt.figure(figsize=(8,5))

plt.bar(
    experience_analysis['experience_level'],
    experience_analysis['total_jobs']
)

plt.title("Experience Level Analysis")
plt.xlabel("Experience Level")
plt.ylabel("Number of Job Postings")

# Values on top of bars
for i, value in enumerate(experience_analysis['total_jobs']):
    plt.text(i, value, str(value), ha='center')

plt.show()
```
![image alt](https://github.com/Y7976/Data-Analyst-Job-Market-Intelligence-Dashboard/blob/69ffa88a13eed9d9d54f0811557ef918e4c7ed38/Experience_Level_analysis.png)
## 8. Monthly Hiring Trend
- Analyzed month-over-month job postings to understand hiring patterns over time.
```python
jobs['month'] = jobs['posted_date'].dt.month

monthly_hiring = (
    jobs.groupby('month')
    .size()
    .reset_index(name='jobs_posted')
)
monthly_hiring.head(10)
```
# Visualization
```python
plt.figure(figsize=(10,5))

plt.plot(
    monthly_hiring['month'],
    monthly_hiring['jobs_posted'],
    marker='o'
)

plt.title("Monthly Hiring Trend")
plt.xlabel("Month")
plt.ylabel("Number of Jobs Posted")

plt.grid(True)

plt.show()
```
![image alt](https://github.com/Y7976/Data-Analyst-Job-Market-Intelligence-Dashboard/blob/69ffa88a13eed9d9d54f0811557ef918e4c7ed38/monthly%20hiring%20trend.png)

- **Outcome:** Identified peak hiring months and fluctuations in recruitment demand throughout the year.
---
##  Statistical Insights

### 1. Skill Demand Share (%)
- Measured the percentage contribution of each skill to identify the most in-demand technologies

```python
skill_share = (
    skills['skill_name']
    .value_counts(normalize=True)
    .mul(100)
    .round(2)
)
skill_share.head(10)
```
- **Outcome:** SQL, Python, Power BI, Tableau, and AWS emerged as the most sought-after skills.
### 2. Skill Combination Analysis
- Identified the most frequently requested skill pairs using market basket analysis.

```python
skill_combination = (
    skills.groupby('job_id')['skill_name']
    .apply(lambda x: ','.join(sorted(x)))
)
skill_combination.head(10)

from collections import Counter
from itertools import combinations

pairs = Counter()

for job_id, group in skills.groupby('job_id'):

    skill_list = sorted(
        group['skill_name'].unique()
    )

    for pair in combinations(skill_list, 2):
        pairs[pair] += 1

print(pairs.most_common(10))
```
- **Outcome:** AWS + Python, SQL + Tableau, and Pandas + Tableau were among the most common skill combinations.
### 3. Salary Premium by Skill
- Analyzed average salaries associated with different technical skills.

```python
merged = jobs.merge(skills ,on = 'job_id')
salary_by_skill =(
    merged.groupby('skill_name')['salary_lpa']
    .mean()
    .reset_index()
)

salary_by_skill['salary_lpa'] = salary_by_skill['salary_lpa'].round(2)
salary_by_skill = salary_by_skill.sort_values(
    by='salary_lpa',
    ascending=False
)

salary_by_skill.head(10)
```
- **Outcome:** Advanced analytical and cloud-related skills were linked to higher average salaries.
### 4. Hiring Growth Rate
- Evaluated month-over-month hiring trends using time-series analysis.

```python
monthly_hiring['growth_rate'] = (
    monthly_hiring['jobs_posted']
    .pct_change() * 100
)

print(monthly_hiring)
```
- **Outcome:** Hiring demand fluctuated throughout the year, highlighting peak recruitment periods.
### 5. Outlier Analysis
- Applied the IQR method to identify salary anomalies and high-paying opportunities.
```python
Q1 = jobs['salary_lpa'].quantile(.25)
Q3 = jobs['salary_lpa'].quantile(.75)

IQR = Q3-Q1

outliers = jobs[
    (jobs['salary_lpa'] < Q1-1.5*IQR) |
    (jobs['salary_lpa'] > Q3+1.5*IQR)
]

print(len(outliers))
```
- **Outcome:** Detected premium job postings offering significantly higher salaries than the market average.

#  Salary Prediction Model

A Machine Learning model was developed to predict salary packages based on job attributes such as company, location, and experience level. The project follows a complete end-to-end machine learning workflow, including data preprocessing, feature engineering, model training, evaluation, and visualization.

---

##  Objective

To build a predictive model capable of estimating salary (LPA) for job postings using historical job market data.

---

##  Machine Learning Workflow

# Import Libraries
import pandas as pd
import numpy as np

from sklearn.model_selection import train_test_split
from sklearn.preprocessing import OneHotEncoder
from sklearn.compose import ColumnTransformer
from sklearn.pipeline import Pipeline
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_absolute_error
from sklearn.metrics import mean_squared_error
from sklearn.metrics import r2_score


### 1. Data Collection
- Imported the job market dataset containing company, location, experience level, and salary information.
```python
jobs = pd.read_csv("/content/jobs_realistic_salary.csv")

jobs.head()
```
### 2. Data Understanding
- Examined dataset structure, data types, and feature distributions.
- Identified target and predictor variables.

### 3. Data Cleaning
- Checked for missing values and duplicate records.
```python
jobs.drop_duplicates(inplace=True)
jobs.isnull().sum()
```
- Ensured data consistency across all features.

### 4. Feature Selection
- Selected relevant predictors:
  - Company Name
  - Location
  - Experience Level
```python
X = jobs[
    [
        'company_name',
        'location',
        'experience_level' ]
]
y = jobs['salary_lpa']
```
### 5. Target Variable Definition
- Defined **Salary (LPA)** as the target variable for prediction.

### 6. Data Preprocessing
- Applied One-Hot Encoding to transform categorical variables into numerical format.
- Handled unseen categories using `handle_unknown='ignore'`.
```python
categorical_features = [
    'company_name',
    'location',
    'experience_level'
]

preprocessor = ColumnTransformer(
    transformers=[
        (
            'cat',
            OneHotEncoder(
                handle_unknown='ignore'
            ),
            categorical_features
        )
    ]
)
```
### 7. Train-Test Split
- Split the dataset into training and testing sets.
- Training Data: 80%
- Testing Data: 20%
```python
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```
### 8. Pipeline Creation
- Built a machine learning pipeline integrating:
  - ColumnTransformer
  - OneHotEncoder
  - Linear Regression
```python
model = Pipeline(
    steps=[
        ('preprocessor', preprocessor),
        ('regressor', LinearRegression())
    ]
)
```

### 9. Model Training
- Trained a Linear Regression model using the processed training dataset.
```python
model.fit(
    X_train,
    y_train
)
```
![image alt](https://github.com/Y7976/Data-Analyst-Job-Market-Intelligence-Dashboard/blob/ad757dbabf8c595b6c41e83bafcc6cdd0cf9e9ff/linear%20regression%20train%20test%20model.png)
### 10. Salary Prediction
- Generated salary predictions on unseen test data.
```python
predictions = model.predict(
    X_test
)
```
### 11. Model Evaluation
- Evaluated model performance using:
  - Mean Absolute Error (MAE)
  - Root Mean Squared Error (RMSE)
  - R² Score
```python
mae = mean_absolute_error(y_test, predictions)

rmse = np.sqrt(
    mean_squared_error(
        y_test,
        predictions
    )
)

r2 = r2_score(
    y_test,
    predictions
)

print("MAE :", round(mae,2))
print("RMSE:", round(rmse,2))
print("R² Score:", round(r2,2))
print("Model Accuracy:", round(r2*100,2), "%")
```
### 12. Visualization & Interpretation
- Created an Actual vs Predicted Salary scatter plot.
- Assessed prediction accuracy and model performance visually.
```python
plt.figure(figsize=(10,6))

# Actual Salary
plt.scatter(
    range(len(y_test)),
    y_test,
    color='blue',
    label='Actual Salary'
)

# Predicted Salary
plt.scatter(
    range(len(predictions)),
    predictions,
    color='orange',
    label='Predicted Salary'
)

plt.title("Actual vs Predicted Salary")
plt.xlabel("Test Data Points")
plt.ylabel("Salary (LPA)")

plt.legend()
```
---

##  Model Performance

| Metric | Value |
|----------|----------|
| MAE | 0.93 |
| RMSE | 1.17 |
| R² Score | 0.94 |

---

##  Insights

- Experience level was the strongest factor influencing salary.
- Location significantly impacted compensation levels.
- The model successfully explained 94% of salary variation.
- Prediction errors remained low, indicating strong model reliability.

---

##  Technologies Used

- Python
- Pandas
- NumPy
- Scikit-Learn
- Matplotlib
- Google Colab

---

##  Outcome

Successfully developed a Linear Regression model capable of predicting salaries with an **R² Score of 0.94**, demonstrating strong predictive performance and practical application of machine learning in job market analytics.

#  SQL Analysis Performed

## SQL Analysis

A total of **19 SQL business problems** were solved using PostgreSQL to analyze hiring trends, salary patterns, skill demand, and workforce insights.

### 1. Total Job Postings
- Calculated the total number of job openings available in the dataset.
```sql
select count(*) as total_job_posting from jobs
```
- **Outcome:** Measured overall hiring activity in the job market.

### 2. Total Companies Hiring
- Identified the number of companies actively recruiting.
```sql
select count( company_name) as total_company_hiring  from company;
```
- **Outcome:** Evaluated employer participation in the market.

### 3. Top Hiring Companies
- Ranked companies based on total job postings.
```sql
select company_name,
       count(job_id) as total_hiring
from jobs
group by company_name
order by count(job_id) desc
limit 10 ;
```
- **Outcome:** Identified organizations with the highest recruitment demand.

### 4. Top Hiring Cities
- Analyzed job opportunities across different locations.
```sql
select location,
       count(job_id) as top_hiring_cities
from jobs
group by  location
order by count(job_id) desc
 ;
```
- **Outcome:** Determined the cities with the highest hiring activity.

### 5. Experience Level Distribution
- Examined hiring demand across experience categories.
```sql
select experience_level,
      count(job_id) as job_distribution
from jobs
group by 1
order by 2 desc ;
```
- **Outcome:** Entry-level and fresher positions accounted for a major share of opportunities.

### 6. Average Salary by City
- Compared average salaries across locations.
```sql
select location,
       round(avg(salary_lpa),2) as Average_salary
from jobs
group by 1
order by 2 desc ;
```
- **Outcome:** Identified cities offering the highest compensation.

### 7. Average Salary by Experience Level
- Evaluated salary growth across experience categories.
```sql
select experience_level,
       round(avg(salary_lpa),2) as Average_salary
from jobs
group by 1
order by 2 desc ;
```

- **Outcome:** Salaries increased consistently with experience level.

### 8. Top 10 Most Demanded Skills
- Measured the frequency of skills mentioned in job requirements.
```sql
select skill_name,
       count(*) as demanded_skills
from job_skills 
group by 1
order by 2 desc 
limit 10 ;
```

- **Outcome:** SQL, Python, Power BI, Tableau, and AWS emerged among the most demanded skills.

### 9. Top Cities for Freshers
- Analyzed fresher opportunities by location.
```sql
select location ,
       count(*) as jobs 
from jobs
where experience_level = 'Fresher'
group by 1
order by 2
limit 10;
```

- **Outcome:** Identified cities with the highest entry-level hiring demand.

### 10. Companies Offering Highest Average Salary
- Compared average salary packages across companies.
```sql
select company_name,
       round(avg(salary_lpa),2) as Average_salary
from jobs
group by 1
order by 2 desc
limit 5 ;
```

- **Outcome:** Highlighted organizations providing premium compensation.

### 11. Rank Companies by Number of Openings
- Applied Window Functions to rank companies by hiring volume.
```sql
select company_name ,
       count(job_id)as Available_jobs,
	   Rank() over(order by count(job_id) desc  )as ranking
from jobs
group by 1
 ;
```
- **Outcome:** Generated company-wise recruitment rankings.

### 12. Highest Paying Company in Each City
- Identified the highest-paying employer within every location.
```sql
select * 
from
(select company_name,location ,
       round(avg(salary_lpa),2) as highest_salary,
	   rank() over(partition by location 
	              order by avg(salary_lpa) desc ) as rk
from jobs
group by 1 ,2 ) as t
where rk = 1 ;
```
- **Outcome:** Revealed location-specific salary leaders.

### 13. Skill Demand Share (%)
- Calculated the percentage contribution of each skill to total demand.
```sql
select  skill_name,
        count(*) as demand_skills,
		round(
        count(*) * 100.0 / (select count(job_id) from jobs)	
		, 2
		) as demand_share
from job_skills
group by 1
order by 2 desc ;
```
- **Outcome:** Quantified the market demand for individual skills.

### 14. Industry-Wise Hiring Analysis
- Evaluated recruitment activity across industries.
```sql
select c.industry,
       count(j.job_id) as total_hiring
from companies as c
join jobs as j
on c.company_id = j.company_id 
group by 1
order by 2 desc ;
```

- **Outcome:** Identified industries with the highest workforce demand.

### 15. Top Skill Required by Each Company
- Determined the most frequently requested skill for every company.
```sql
select *
from
(select skill_name ,
	   company_name,
	   count(*)as skill_demand ,
	   row_number() over( 
	   partition by company_name
	   order by count(*) desc
	   ) as rn
from job_skills as js
join jobs as j
on js.job_id = j.job_id
group by 1,2  ) as t

where rn=1;
```
- **Outcome:** Highlighted company-specific hiring preferences.

### 16. Top 3 Hiring Companies in Each City
- Ranked employers within each city using Window Functions.
```sql
select *
from
(select location ,company_name,
       count(job_id) as Total_hiring,
	   Dense_Rank() over(partition by location 
	                     order by count(job_id)desc)
	                     as dr
from jobs
group by 1,2)
where dr <= 3;
```
- **Outcome:** Identified leading recruiters across locations.

### 17. Salary Compared to City Average
- Compared individual salaries against city-level averages.
```sql
SELECT j.*
FROM jobs j
JOIN (
        SELECT location,
               AVG(salary_lpa) AS avg_salary
        FROM jobs
        GROUP BY location
     ) a
ON j.location = a.location
WHERE j.salary_lpa < a.avg_salary;
```


- **Outcome:** Identified jobs offering above-average compensation.

### 18. Most Demanded Skill in Every Industry
- Combined Joins, CTEs, and Window Functions to analyze skill demand.
```sql
WITH skill AS
(
    SELECT c.industry,
           js.skill_name,
           COUNT(*) AS demand,
           ROW_NUMBER() OVER(
               PARTITION BY c.industry
               ORDER BY COUNT(*) DESC
           ) AS skill_rank
    FROM job_skills js
    JOIN jobs j
      ON js.job_id = j.job_id
    JOIN companies c
      ON c.company_id = j.company_id
    GROUP BY c.industry, js.skill_name
)

SELECT industry,
       skill_name,
       demand
FROM skill
WHERE skill_rank = 1;
```
- **Outcome:** Determined the most valuable skill across each industry.

### 19. Month-over-Month Hiring Growth Trend
- Analyzed hiring growth using time-series and LAG functions.
```sql
with growth
as
(select
       extract(Month from posted_date) as month,
	   count(*) as job_posted
	 from jobs
group by 1 ) 

select month,
       job_posted,
	   lag(job_posted)
	   over(order by month) as previous_month,
       round(job_posted -  lag(job_posted)
	   over(order by month)*100.0
	  /
	   lag(job_posted)
	   over(order by month),2) as growth_percentage
from growth ;
```
- **Outcome:** Tracked recruitment growth and seasonal hiring fluctuations over time.

### SQL Concepts Used
- Joins
- Aggregate Functions
- GROUP BY & HAVING
- Subqueries
- Common Table Expressions (CTEs)
- Window Functions (RANK, DENSE_RANK, ROW_NUMBER, LAG)
- Date Functions
- Business-Oriented Analytical Queries

---


#  Power BI Dashboard

An interactive Power BI dashboard was developed to transform raw job market data into meaningful business insights. The dashboard enables users to analyze hiring trends, salary patterns, skill demand, and recruitment activity through dynamic visualizations and KPI tracking.

---

##  Objective

To create a data-driven dashboard that helps understand job market trends, hiring demand, salary distribution, and skill requirements across different companies and locations.



---
![image alt](https://github.com/Y7976/Data-Analyst-Job-Market-Intelligence-Dashboard/blob/576670cfc9ca48925074160db14332f2dd3c4df8/job_intellegence_dashboard.png)

![image alt](https://github.com/Y7976/Data-Analyst-Job-Market-Intelligence-Dashboard/blob/576670cfc9ca48925074160db14332f2dd3c4df8/Job_intellegence_dashboard%202.png)
##  Dashboard Development Process

### 1. Data Import
- Imported Jobs, Companies, and Skills datasets into Power BI.

### 2. Data Cleaning
- Verified data quality and handled inconsistencies using Power Query.

### 3. Data Modeling
- Established relationships between:
  - Jobs Table
  - Companies Table
  - Skills Table

### 4. KPI Creation
Developed key performance indicators including:
- Total Jobs
- Total Companies
- Average Salary
- Highest Salary
- Total Skills
- Top Hiring City

### 5. Hiring Analysis
Created visualizations to analyze:
- Top Hiring Companies
- Top Hiring Cities
- Experience Level Distribution

### 6. Skill Demand Analysis
Developed visuals to identify:
- Most Demanded Skills
- Skill Demand Share (%)
- Skill Distribution Trends

### 7. Salary Analysis
Analyzed:
- Average Salary by City
- Average Salary by Experience Level
- Salary Distribution

### 8. Hiring Trend Analysis
Created a Monthly Hiring Trend visualization to monitor recruitment patterns over time.

### 9. Interactive Filtering
Added slicers for:
- Company
- Location
- Experience Level
- Skill Name

### 10. Dashboard Design
Implemented a clean and user-friendly layout for easy navigation and insight discovery.

---

##  Dashboard Insights

- Identified the top hiring companies and locations.
- Revealed the most demanded technical skills in the market.
- Highlighted salary differences across cities and experience levels.
- Tracked hiring fluctuations through monthly trend analysis.
- Provided a comprehensive view of job market opportunities.

---

##  Dashboard Components

### KPI Cards
- Total Jobs
- Total Companies
- Average Salary
- Highest Salary
- Top Hiring City
- Total Skills

### Visualizations
- Top Hiring Companies
- Top Hiring Cities
- Experience Level Distribution
- Skill Demand Analysis
- Salary Analysis
- Monthly Hiring Trend

### Filters
- Company Name
- Location
- Experience Level
- Skill Name

---

##  Tools Used

- Power BI
- Power Query
- DAX
- Data Modeling

---

##  Outcome

Developed an interactive Job Market Intelligence Dashboard that enables users to explore hiring trends, salary insights, skill demand patterns, and recruitment activity through dynamic visualizations and KPI-driven analytics.




---
##  Key Insights

- SQL, Python, Power BI, Tableau, and AWS were the most demanded skills.
- Bangalore, Hyderabad, Mumbai, and Delhi NCR emerged as major hiring hubs.
- Entry-level and Fresher roles accounted for the highest number of job opportunities.
- Salary increased consistently with experience level.
- The Linear Regression model achieved an R² Score of 0.94, indicating strong predictive performance.

---

## Learning Outcomes

- Performed data cleaning, EDA, and statistical analysis using Python.
- Applied SQL concepts including Joins, CTEs, Subqueries, and Window Functions.
- Built interactive Power BI dashboards using DAX and data modeling.
- Developed and evaluated a Linear Regression model for salary prediction.
- Generated actionable business insights from job market data.


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
