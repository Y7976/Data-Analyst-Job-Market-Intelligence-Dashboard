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

### Jobs Dataset
- Job ID
- Job Title
- Company Name
- Location
- Experience Level
- Salary (LPA)
- Posted Date

### Job Skills Dataset
- Job ID
- Skill Name

### Companies Dataset
- Company ID
- Company Name
- Industry

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

- Total Job Postings
- Top Hiring Companies
- Top Hiring Cities
- Experience Level Distribution
- Average Salary by City
- Average Salary by Experience
- Most Demanded Skills
- Skill Demand Share (%)
- Industry-wise Hiring Analysis
- Monthly Hiring Trends

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

- Top Hiring Companies Analysis
- Hiring Trend Analysis
- Experience Level Distribution
- Salary Distribution
- Salary by City
- Salary by Experience Level
- Skill Demand Analysis

### Statistical Analysis

- Mean Salary
- Median Salary
- Standard Deviation
- Variance
- Interquartile Range (IQR)
- Outlier Detection

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

### Model Performance

| Metric | Value |
|----------|----------|
| R² Score | 0.94 |
| MAE | 0.93 LPA |
| RMSE | 1.17 LPA |

The model explains 94% of salary variation and demonstrates strong predictive performance.

---

## Power BI Dashboard

### KPI Cards

- Total Jobs
- Total Companies
- Average Salary
- Highest Salary
- Total Skills

### Visualizations

- Top Hiring Companies
- Top Hiring Cities
- Experience Distribution
- Top Skills Analysis
- Salary by City
- Salary by Experience
- Monthly Hiring Trend

### Filters

- Company Name
- Location
- Experience Level
- Skill Name

---

## Key Business Insights

- Identified the most in-demand technical skills.
- Determined cities with the highest hiring activity.
- Analyzed salary trends by location and experience level.
- Evaluated employer hiring patterns.
- Predicted salaries using machine learning techniques.

---

## Project Structure

```text
Data-Analyst-Job-Market-Intelligence/
│
├── datasets/
│   ├── jobs.csv
│   ├── job_skills.csv
│   └── companies.csv
│
├── sql/
│   └── analysis_queries.sql
│
├── notebooks/
│   └── job_market_analysis.ipynb
│
├── dashboard/
│   └── PowerBI_Dashboard.pbix
│
├── images/
│   └── dashboard_screenshot.png
│
└── README.md
```

---

## Results

- Analyzed 5,000+ job postings using SQL and Python.
- Built an interactive Power BI dashboard for hiring and salary insights.
- Identified top hiring companies, cities, and in-demand skills.
- Developed a Linear Regression model with **R² = 0.94**.
- Generated actionable job market and workforce analytics insights.

---

## Author

**Yasmin**

Aspiring Data Analyst skilled in SQL, Python, Power BI, Machine Learning, and Data Visualization.
