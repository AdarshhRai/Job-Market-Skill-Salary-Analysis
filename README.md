# Job-Market-Skill-Salary-Analysis
Built an interactive job market analysis dashboard using Excel Power Query for data cleaning and transformation, Power Pivot for data modeling, and DAX for calculated measures. Analyzed skill demand, salary trends, and role distribution to deliver actionable insights for data-driven career decisions.

# Job-Market-Skill-Salary-Analysis


## Project 2 Analysis

## Introduction

As a former job seeker, I was surprised by the lack of clear, data-backed guidance on which **data roles and skills** actually lead to higher pay. This project explores the data science job market to identify **in-demand skills**, **regional salary differences**, and whether **more skills translate into better compensation**—all using advanced Excel analytics.

---

## Questions Analyzed

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

---

## Excel Skills Used

* **📊 Pivot Tables**
* **📈 Pivot Charts**
* **🧮 DAX (Data Analysis Expressions)**
* **🔍 Power Query (ETL)**
* **💪 Power Pivot (Data Modeling)**

---

## Dataset Overview

The dataset contains real-world **2023 data job postings**, including:

* **👨‍💼 Job titles**
* **💰 Salary information**
* **📍 Job locations**
* **🛠️ Required skills**

Each job posting may list multiple skills, which are normalized for analysis.

---

## 1️⃣ Do More Skills Get You Better Pay?

### 🔍 Power Query (ETL)

#### 📥 Extract

Using Power Query, the original dataset was split into two queries:

* `data_jobs_all` – complete job posting information
* `data_jobs_skills` – skills listed per job ID

#### 🔄 Transform

Both queries were cleaned and standardized by:

* Changing column data types
* Removing unnecessary columns
* Cleaning and trimming text
* Splitting multi-skill fields

**Job Data Transformations**
![Power Query – Job Data Steps](/0_Resources/Images/2_Project_Analysis_Screenshot1.png)

**Skills Data Transformations**
![Power Query – Skills Steps](/0_Resources/Images/2_Project_Analysis_Screenshot2.png)

#### 🔗 Load

Both transformed tables were loaded into the workbook to support modeling and analysis.

![Loaded Job Table](/0_Resources/Images/2_Project_Analysis_Screenshot3.png)
![Loaded Skills Table](/0_Resources/Images/2_Project_Analysis_Screenshot4.png)

### 📊 Analysis & Insights

* 📈 A positive correlation exists between the **number of skills requested** and **median salary**, especially for senior roles.
* 💼 Roles with fewer required skills (e.g., Business Analyst) tend to have lower salaries.

![Skills vs Salary Scatter](/0_Resources/Images/2_Project_Analysis_Chart1.png)

**So What:** Specialization and broader skill sets generally lead to higher-paying opportunities.

---

## 2️⃣ Salary by Region

### 🧮 PivotTables & DAX

A PivotTable was built on the Power Pivot data model to calculate **median salaries**.

**Median Salary (US Only)**

```DAX
=CALCULATE(
    MEDIAN(data_jobs_all[salary_year_avg]),
    data_jobs_all[job_country] = "United States"
)
```

**Overall Median Salary**

```DAX
Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
```

### 📊 Insights

* 💼 Senior Data Engineers and Data Scientists earn top salaries globally.
* 💰 US-based roles generally offer higher compensation than Non-US roles.

![Regional Salary Comparison](/0_Resources/Images/2_Project_Analysis_Chart2.png)

**So What:** Location plays a major role in salary negotiations and career planning.

---

## 3️⃣ Top Skills of Data Professionals

### 🔧 Power Pivot & Data Modeling

The cleaned tables were integrated into a single data model using `job_id` as a **one-to-many relationship**.

![Data Model Relationship](/0_Resources/Images/2_Project_Analysis_Screenshot5.png)

Power Pivot enabled efficient measure creation and skill-level analysis.

![Power Pivot Menu](/0_Resources/Images/2_Project_Analysis_Screenshot6.png)

### 📊 Insights

* 💻 **SQL and Python** dominate data job requirements.
* ☁️ Cloud technologies like **AWS and Azure** are increasingly in demand.

![Top Skills Bar Chart](/0_Resources/Images/2_Project_Analysis_Chart3.png)

**So What:** Focusing on core programming and cloud skills significantly improves employability.

---

## 4️⃣ Pay of the Top 10 Skills

### 📈 Advanced Pivot Chart

A combo PivotChart was created:

* **Columns:** Median Salary
* **Line (Secondary Axis):** Skill Likelihood (%)

### 📊 Insights

* 💰 High-paying skills include **Python, Oracle, and SQL**.
* 📉 Tools like **Word and PowerPoint** show lower salary association and demand.

![Top Skills Pay Comparison](/0_Resources/Images/2_Project_Analysis_Chart4.png)

**So What:** Investing in high-value technical skills yields stronger salary outcomes.

---

## Conclusion

This Excel-based project demonstrates how **Power Query, Power Pivot, DAX, and advanced visualizations** can be combined to perform real-world labor market analysis. The insights highlight the strong link between **skill specialization**, **location**, and **compensation**, providing actionable guidance for data professionals aiming to maximize career growth and salary potential.

---

## Author

Portfolio project showcasing **advanced Excel analytics**, data modeling, and business insight generation.

