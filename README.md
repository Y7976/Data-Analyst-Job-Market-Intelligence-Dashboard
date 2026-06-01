# Data Analyst Job Market Intelligence & Salary Prediction

## Project Overview

This project analyzes job market data to identify hiring trends, skill demand, salary patterns, and recruitment opportunities for Data Analyst roles. The project combines SQL, Python, Power BI, and Machine Learning to generate actionable insights from job postings and predict salaries based on key job attributes.

---

## Objectives

- Analyze hiring trends across companies and locations.
- Identify the most in-demand technical skills.
- Examine salary distribution across cities and experience levels.
- Track monthly hiring trends.
- Build a salary prediction model using Machine Learning.
- Create an interactive Power BI dashboard.

---

## Dataset Information

### Dataset Columns

**jobs.csv**
- job_id:             Unique job identifier.
- job_title:          Name of the job role.
- company_id:         Unique company identifier.
- company_name:       Name of the hiring company.
- location:           Job location.
- experience_level:   Required experience level.
- salary_lpa:         Annual salary offered (LPA).
- posted_date:        Date of job posting.

**job_skills.csv**
- job_id:             Job identifier linked to jobs dataset.
- skill_name:         Required skill for the job.

**companies.csv**
- company_id:        Unique company identifier.
- company_name:      Company name.
- industry:          Industry category of the company.
---

## Tools & Technologies

- SQL (PostgreSQL)
- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-Learn
- Power BI
- Git & GitHub

---

## SQL Analysis

Performed SQL analysis to answer business questions:

- **Total Job Postings**             –      Calculated the total number of job openings available in the dataset.
- **Top Hiring Companies**           –      Identified companies with the highest recruitment activity.
- **Top Hiring Cities**              –      Determined locations with the maximum job opportunities.
- **Experience Level Distribution**  –      Analyzed hiring demand across experience categories.
- **Average Salary by City**         –      Compared salary offerings across different locations.
- **Average Salary by Experience**   –      Evaluated salary growth with increasing experience.
- **Most Demanded Skills**           –      Identified the most frequently requested technical skills.
- **Skill Demand Share (%)**         –      Measured the percentage contribution of each skill to total demand.
- **Industry-wise Hiring Analysis**  –      Examined recruitment patterns across industries.
- **Monthly Hiring Trend**           –      Tracked changes in hiring activity over time.

### SQL Concepts Used

- Joins
- CTEs
- Window Functions
- Ranking Functions
- Aggregate Functions

---

## Python Analysis

Performed Exploratory Data Analysis (EDA) and statistical analysis.

### Key Insights

- **Data Cleaning**                   –     Processed and prepared data for accurate analysis.
- **Exploratory Data Analysis (EDA)** –     Explored patterns, trends, and distributions within the dataset.
- **Descriptive Statistics**          –     Computed statistical measures such as mean, median, and standard deviation.
- **Salary Distribution Analysis**    –     Analyzed salary spread and variation across job postings.
- **Company-wise Hiring Analysis**    –     Evaluated recruitment volume across companies.
- **Location-wise Analysis**          –     Compared job opportunities across cities.
- **Experience Level Analysis**       –     Assessed hiring demand based on required experience.
- **Skill Demand Analysis**           –     Examined the popularity of different technical skills.
- **Hiring Trend Analysis**           –     Visualized hiring patterns over time.
- **Outlier Detection**               –     Identified unusual salary observations within the dataset.


### Statistical Analysis

### Statistical Analysis

- **Mean Salary**               –    Calculated the average salary offered across all job postings.
- **Median Salary**             –    Identified the middle salary value to understand the typical salary level.
- **Standard Deviation**        –    Measured the variability of salaries around the average salary.
- **Variance**                  –    Quantified the overall dispersion of salary values within the dataset.
- **Interquartile Range (IQR)** –    Measured the spread of the middle 50% of salary observations.
- **Outlier Detection**         –    Identified unusually high or low salary values using the IQR method.
---

## Machine Learning

### Salary Prediction Model

Built a Linear Regression model using:

**Features**
- Company Name
- Location
- Experience Level

**Target Variable**
- Salary (LPA)
** Model Working**
- **Feature Engineering**        –   Selected relevant job attributes for salary prediction.
- **Data Encoding**              –   Converted categorical variables into machine-readable format.
- **Train-Test Split**           –   Divided data into training and testing datasets.
- **Linear Regression Modeling** –   Developed a salary prediction model using Linear Regression.
- **Model Evaluation**           –   Assessed model performance using R² Score, MAE, and RMSE.

### Model Performance

| Metric | Value |
|----------|----------|
| R² Score | 0.94 |
| MAE | 0.93 LPA |
| RMSE | 1.17 LPA |

The model explains 94% of salary variation and demonstrates strong predictive performance.

---

## Power BI Dashboard
 
- **KPI Development**           –   Created key performance indicators for job market analysis.
- **Interactive Filtering**     –   Enabled dynamic filtering using slicers.
- **Hiring Insights Dashboard** –   Visualized company-wise and city-wise hiring trends.
- **Skill Demand Dashboard**    –   Displayed the most in-demand technical skills.
- **Salary Insights Dashboard** –   Compared salaries across locations and experience levels.
- **Trend Analysis Dashboard**  –   Monitored monthly hiring trends through interactive visualizations.

### KPI Cards

- **Total Jobs**      –   Displays the total number of job postings available in the dataset.
- **Total Companies** –   Shows the number of unique companies hiring candidates.
- **Average Salary**  –   Represents the average salary offered across all job postings.
- **Highest Salary**  –   Highlights the maximum salary offered in the dataset.
- **Total Skills**    –   Indicates the total number of unique skills required by employers.

### Visualizations

- **Top Hiring Companies**     –   Identifies companies with the highest number of job openings.
- **Top Hiring Cities**        –   Displays cities with the greatest hiring activity.
- **Experience Distribution**  –   Shows the demand for candidates across different experience levels.
- **Top Skills Analysis**      –   Highlights the most frequently requested technical skills.
- **Salary by City**           –   Compares average salary offerings across locations.
- **Salary by Experience**     –   Analyzes salary growth based on experience level.
- **Monthly Hiring Trend**     –   Tracks changes in hiring activity over time.

### Filters

- **Company Name**     –   Filters dashboard insights for a selected company.
- **Location**         –   Filters data based on job location.
- **Experience Level** –   Displays insights for a specific experience category.
- **Skill Name**       –   Filters results according to selected technical skills.
---

## Key Business Insights

- Identified the most in-demand technical skills.
- Determined cities with the highest hiring activity.
- Analyzed salary trends by location and experience level.
- Evaluated employer hiring patterns.
- Predicted salaries using machine learning techniques.

---




## Results
Analyzed 5,000+ job postings using SQL and Python to uncover hiring, salary, and skill demand trends.
Designed an interactive Power BI dashboard for workforce analytics and job market insights.
Identified top hiring companies, high-demand skills, and location-wise job opportunities.
Built a Linear Regression model for salary prediction, achieving an R² score of 0.94.
Delivered actionable insights through data visualization, statistical analysis, and predictive modeling.

---

## Author

**Yasmin**

Aspiring Data Analyst skilled in SQL, Python, Power BI, Machine Learning, and Data Visualization.
