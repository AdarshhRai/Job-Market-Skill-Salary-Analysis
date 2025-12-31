# Job-Market-Skill-Salary-Analysis
Built an interactive job market analysis dashboard using Excel Power Query for data cleaning and transformation, Power Pivot for data modeling, and DAX for calculated measures. Analyzed skill demand, salary trends, and role distribution to deliver actionable insights for data-driven career decisions.

# Job-Market-Skill-Salary-Analysis


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

📊 data_jobs_all

<img width="244" height="312" alt="image" src="https://github.com/user-attachments/assets/b82f68c9-26dd-492d-b9cf-7d1002751fed" />

🛠️ data_job_skills

<img width="243" height="328" alt="image" src="https://github.com/user-attachments/assets/1f661a59-892b-406c-a5b8-ab32dbe0c96c" />


#### 🔗 Load

Both transformed tables were loaded into the workbook to support modeling and analysis.

📊 data_jobs_all

<img width="1916" height="649" alt="image" src="https://github.com/user-attachments/assets/5075d5e9-a7da-43dd-8eb6-8683902d4779" />

🛠️ data_job_skills

<img width="1914" height="702" alt="image" src="https://github.com/user-attachments/assets/7e370957-2e61-412f-870b-045617a24628" />


### 📊 Analysis & Insights

* 📈 A positive correlation exists between the **number of skills requested** and **median salary**, especially for senior roles.
* 💼 Roles with fewer required skills (e.g., Business Analyst) tend to have lower salaries.

<img width="874" height="537" alt="image" src="https://github.com/user-attachments/assets/4047dd47-3cb3-4670-953e-5d353eaceb68" />


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

<img width="1776" height="738" alt="image" src="https://github.com/user-attachments/assets/8badfa59-f256-46d2-90dc-999c0aa4883d" />

**So What:** Location plays a major role in salary negotiations and career planning.

---

## 3️⃣ Top Skills of Data Professionals

### 🔧 Power Pivot & Data Modeling

🔗 Data Model
I created a relationship between my two tables using the job_id column.

<img width="1788" height="1264" alt="image" src="https://github.com/user-attachments/assets/063356c5-2b86-4d84-80ef-53e56ba432f1" />

📃 Power Pivot Menu
The Power Pivot menu was used to refine my data model and makes it easy to create measures.
<img width="1918" height="742" alt="image" src="https://github.com/user-attachments/assets/1e505efc-90ae-44c0-b0fe-e18d804bc226" />



The cleaned tables were integrated into a single data model using `job_id` as a **one-to-many relationship**.

Power Pivot enabled efficient measure creation and skill-level analysis.

### 📊 Insights

* 💻 **SQL and Python** dominate data job requirements.
* ☁️ Cloud technologies like **AWS and Azure** are increasingly in demand.

<img width="759" height="513" alt="image" src="https://github.com/user-attachments/assets/664bb8fb-3cb6-4c6d-9e00-c45769d894de" />

**So What:** Focusing on core programming and cloud skills significantly improves employability.

---

## 4️⃣ Pay of the Top 10 Skills

### 📈 Advanced Pivot Chart

A combo PivotChart was created:

* **Columns:** Median Salary
* **Line (Secondary Axis):** Skill Likelihood (%)

### 📊 Insights

* 💰 High-paying skills include **Python, Oracle, and SQL**.
* 📉 Tools like **Word and PowerPoint** show lower salary association and demand in Top 10.

<img width="862" height="452" alt="image" src="https://github.com/user-attachments/assets/2c5153ef-8bf1-4899-8985-50b90f32f820" />

**So What:** Investing in high-value technical skills yields stronger salary outcomes.

---

## Conclusion

This Excel-based project demonstrates how **Power Query, Power Pivot, DAX, and advanced visualizations** can be combined to perform real-world labor market analysis. The insights highlight the strong link between **skill specialization**, **location**, and **compensation**, providing actionable guidance for data professionals aiming to maximize career growth and salary potential.

---

## Author

Portfolio project showcasing **advanced Excel analytics**, data modeling, and business insight generation.

