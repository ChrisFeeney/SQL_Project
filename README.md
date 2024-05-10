# Introduction
Dive into the data job market! Focusings on data scientist roles, this project explores top-paying jobs, in-demand skills, and where high demand meets high salary in data science. [project_sql folder](/project_sql/)

SQL queries? Check them out here: 
# Background
Driven by a quest to navigate the data science job market more effectively, this project was born from a desire to pinpoint top-paid and in-demand skills, streamlining others work to find optimal jobs.

Data hails from Luke Barousse's [SQL Course](https://lukebarousse.com/sql).

### The questions I wanted to answer:

1. What are the top-paying data analyst jobs?
2. What skills are required for these top-paying jobs?
3. What skills are most in demand for data scientists?
4. Which skills are associated with higher salaries?
5. What are the most optimal skills to learn?

# Tools I used
For my deep dive into the data science job market, I harnessed the power of several key tools:

- **SQL**: The backbone of my analysis, allowing me to query the database and unearth critical insights.

- **PostgreSQL**: The chosen database management system, ideal for handling the job posting data.

- **Visual Studio Code**: My go-to for database amangement and executing SQL queries.

- **Git & GitHub**: Essential for version control and sharing my SQL scripts and analysis, ensuring collaboration and project tracking.

# The Analysis
Each query for this project aimed at investigating specific aspects of the data science job market. Here's how I approached each question:

### 1. Top Paying Data Science Jobs
To identify the highest-paying roles. I filtered data scientist positions by average yearly salary and location, focusing on remote jobs. This query highlights the high paying opportunities in the field.


```sql
SELECT
  job_id,
  job_title,
  name AS company_name,
  job_location,
  job_schedule_type,
  salary_year_avg,
  job_posted_date
FROM
  job_postings_fact
LEFT JOIN company_dim
  ON job_postings_fact.company_id=company_dim.company_id
WHERE
  job_title_short = 'Data Scientist' AND
  job_location = 'Anywhere' AND
  salary_year_avg IS NOT NULL
ORDER BY
  salary_year_avg DESC
LIMIT 10
;
```
Breakdonw of the top data science jobs in 2023:
- **Wide Salary Range:** Top 10 paying data analyst roles span from $300,000 to $550,000, indicating significant salary potential in the field.

- **Diverse Employers:**
Companies like Reddit, Walmart, Algo Capital Group are among those offering high salaries, showing a broad interest across different industries.

- **Job Title Variety:**
There's a high diversity in job title, from Staff Data Scientist to Head of Data Science, reflecting varied roles and specializations within data science.

# What I learned
Throughout this adventure, I've turbocharged my SQL toolkit with some serious firepower:

- **Complex Query Crafting:** 
Mastered the art of advanced SQL, merging tables like a pro and wielding WITH clauses for ninja-level temp table maneuvers.

- **Data Aggregation:** Got cozy with GROUP BY and turned aggreagate functions like COUNT( ) and AVG( ) into my data-summarizing sidekicks.

- **Analytical Wizardry:** 
Leveled up my real-world puzzle-solving skills, turning questions into actionable, insightful SQL queries.

# Conclusions

### Insights
From the analysis, several general insights emerged:

1. **Top-Paying Data Analyst Jobs:** 
The highest-paying jobs for data scientists that allow remote work offer a wide range of salaries, the highest at $550,000!
2. **Skills for Top-Paying Jobs:** 
High-paying data science jobs requireadvanced proficiency in Python, suggesting it's a critical skill for earning a top salary.
3. **Most In-Demand Skills:** 
Python is also the most demanded skill in the data science job market, thus making it essential for job seekers.
4. **Skills with Higher Salaries:** Specialized skills such as asana, lua, and slack, are associated with the highest with the highest average salaries, indicating a premium in niche expertise.
5. **Optimal Skills for Job Market Value:** Python and SQL lead in demand and offer high average salaries, positioning them as the most optimal skills for data scientist to learn to maximize their market value.

### Closing Thoughts

This project enhanced my SQL skills and provided valuable insights into the data science job market. The findings from the analysis serve as a guide to prioritizinf skill development and job search efforts. Aspiring data scientists can better position themselves in a competitive job market by focusing on high-demand, high salary skills. This exploration highlights the importance of continous learning and adaptation to emerging trends in the field of data science.