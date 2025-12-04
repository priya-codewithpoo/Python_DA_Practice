#  Python Data Analytics Practice Project

##  Overview
This project demonstrates Python programming and Data Analysis skills using a real-world jobs dataset.
It covers data cleaning, exploration, visualization, and insights generation from basic to advanced levels.

---

##  Database Used
**Database:** data_job – a dataset of job listings
**Type:** CSV / Pandas DataFrame (can be imported as Python DataFrame)
**Columns:** job_title_short, job_title, job_location, job_via, job_schedule_type,job_work_from_home, search_location, job_posted_date, job_no_degree_mention,job_health_insurance, job_country, salary_rate, salary_year_avg, salary_hour_avg,company_name, job_skills, job_type_skills. 

---

##  Objectives
- Explore and analyze the data_job dataset to extract actionable insights.
- Practice data manipulation, filtering, aggregation, and visualization using Python (Pandas, NumPy, Matplotlib, Seaborn).
- Identify trends in job listings, salaries, and skill demand.
- Compare remote vs onsite jobs and degree vs non-degree requirements.
- Highlight the most in-demand skills and top-paying job roles.
- Strengthen analytical and Python programming skills for real-world data scenarios.

---

##  Skills Demonstrated
- Pandas: Reading files, filtering, grouping, aggregation, pivot tables, merging, and exploding list-type columns.
- NumPy: Array creation, reshaping, mathematical operations, and filtering.
- Data Visualization: Matplotlib and Seaborn charts – bar, line, scatter, histogram, pie, and trend visualizations.
- Analytical Thinking: Identifying top skills, top-paying jobs, and analyzing trends over time. 

---

##  Project Files
The project is organized by skill level, with each folder containing Python scripts for that level:
-  [1_basic](./1_basic%20level_1.ipynb) - Python data types, loops, conditionals, simple Pandas operations
-  [2_basic](./2_basic%20level_2.ipynb) - Data filtering, aggregation

-  [1_intermediate](./5_intermediate%20level_1.ipynb) – Grouping, aggregation, sorting, ranking, and pivot tables
-  [2_intermediate](./6_intermediate%20level_2.ipynb)– Advanced filtering, working with missing values, summary statistics

-  [1_advanced](./7_advanced%20level_1.ipynb) – Exploding list columns, trend analysis, skill-demand analysis
-  [2_advanced](./8_advanced%20level_2.ipynb) – Advanced visualizations with Matplotlib & Seaborn, complex queries
-  [images](./images/job_sql_requires_most.png) -Job Titles That Require SQL the Most
-  [images](./images/salary_growth_trend_by_job.png) -Salary Growth Trend by Job Title
-  [images](./images/skill_vs_salary.png) - Skill vs Salary (Dot Plot)
-  [images](./images/top_10_skills.png) - Top 10 Skills for Data Analysts

Each file contains code, sample outputs, and chart screenshots where relevant to demonstrate your analysis.

---

## Project Highlights

### **Basic Level**
Python functions (def)
NumPy arrays: mean, median, filtering, reshaping
Pandas basics: filtering, grouping, missing values
Matplotlib: bar, line, histogram, scatter

Example: Clean strings in a list
```python
def clean_strings(lst):
    return [x.strip().lower() for x in lst]

clean_strings([" Python ", "excel ", " SQL"])
# Output: ['python', 'excel', 'sql']

```
---

### **Intermediate Level**
Aggregation & grouping by job title, country, or company
Salary analysis & filtering for remote, degree, or high-paying jobs
Sorting & ranking
Visualizations with Matplotlib & Seaborn

Example: Average salary by country
```python
avg_salary_by_country = (df[df['salary_year_avg'].notna()]
                         .groupby('job_country')['salary_year_avg']
                         .mean()
                         .round()
                         .astype(int)
                         .reset_index(name='avg_salary')
                         .sort_values(by='avg_salary', ascending=False))

```
---

### **Advanced Level**

Pivot tables for multi-dimensional analysis
Exploding skill lists for skill demand analysis
Advanced visualizations: Seaborn barplots, heatmaps, line plots

Example: Top SQL jobs
```python
df_sql = df.explode('job_skills')
df_sql = df_sql[df_sql['job_skills'] == 'sql']
df_sql_count = df_sql.groupby('job_title_short').size().reset_index(name='sql_count')

sns.barplot(data=df_sql_count, x='sql_count', y='job_title_short')
plt.title("Job Titles That Require SQL the Most")
plt.show()
```
---

 ## Key Insights

- Top-paying roles and high-demand skills identified
- Trends in remote work and salary visualized
- Hands-on practice with Python functions, NumPy, Pandas, Matplotlib, Seaborn

---

## Tools & Technologies

- Python 3.x | Jupyter Notebook
- Pandas, NumPy, Matplotlib, Seaborn
- Git & GitHub for version control

---

 ## Conclusion
These projects helped strengthen SQL and Python skills, including data cleaning, analysis, and visualization.  
The repository demonstrates the ability to handle real-world datasets and extract meaningful insights.

---