
# Project 2 Analysis

## Introduction

Through this project, I wanted to explore salary trends and the skills most valued in the data job market. By analyzing real-world job data provided in Luke Barousse's Excel course, I gained insights into how factors such as job title, location, and key technical skills influence salaries. This project also helped me strengthen my Excel data analysis and dashboard development skills through hands-on practice.

### Questions to Analyze

While completing this project, I explored the following questions to better understand salary trends in the data job market:

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. It was provided as part of Luke Barousse's Excel course, where it is used to teach data analysis and dashboard creation in Excel. The dataset serves as the foundation for analyzing salary trends, job roles, locations, and required skills.
It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## 1️⃣ Do more skills get you better pay?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract

- I first used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
    - 🗃️ First one with all the data jobs information.
    - 🔧 The second listing the skills for each job ID.

#### 🔄 Transform

After importing the data, I performed several transformation and cleaning steps, including:

- Converting columns to the appropriate data types.
- Removing unnecessary columns.
- Cleaning text by removing unwanted words and characters.
- Trimming extra whitespace for consistency.
- Preparing the data for analysis and dashboard creation.

    - 📊 data_jobs_all

      <img width="244" height="312" alt="2_Project_Analysis_Screenshot1" src="https://github.com/user-attachments/assets/34c130cb-ddb8-4bff-98f3-967fcf8ecef0" />

    - 🛠️ data_job_skills

      <img width="243" height="328" alt="2_Project_Analysis_Screenshot2" src="https://github.com/user-attachments/assets/cee296b1-a26d-46a8-bff5-5387ce3dc87c" />

#### 🔗 Load

- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
    - 📊 data_jobs_all

       <img width="1916" height="649" alt="2_Project_Analysis_Screenshot3" src="https://github.com/user-attachments/assets/e8e186ba-08a2-41fa-a558-19eee5e1bc5d" />

    - 🛠️ data_job_skills

        <img width="1914" height="702" alt="2_Project_Analysis_Screenshot4" src="https://github.com/user-attachments/assets/f0358592-323a-4d98-8ace-4ea7b1e70616" />

### 📊 Analysis

#### 💡 Insights

- 📈 There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

   <img width="874" height="537" alt="2_Project_Analysis_Chart1" src="https://github.com/user-attachments/assets/cecf89f4-d2cc-4d61-818a-92ee05df5b62" />

#### 🤔 Key Takeaway

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

#### 📈Pivot Table

- 🔢 I created a PivotTable using the Data Model I created with Power Pivot.
- 📊 I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
- 🧮 Then I added new measure to calculate the median salary for United States jobs.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX

- To calculate the median year salary I used DAX.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### 📊 Analysis

#### 💡 Insights

- 💼 Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- 💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

   <img width="1776" height="738" alt="2_Project_Analysis_Chart2" src="https://github.com/user-attachments/assets/8aec8484-1cfa-4095-b06c-993ace7631f4" />

#### **🤔 Key Takeaway**

- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot

#### 💪 Power Pivot

- 🔗 I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### 🔗 Data Model

- I created a relationship between my two tables using the `job_id` column.

    <img width="1788" height="1264" alt="2_Project_Analysis_Screenshot5" src="https://github.com/user-attachments/assets/b2156c14-54c9-4fd4-8190-291abc0d418a" />

#### 📃 Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

    <img width="1918" height="742" alt="2_Project_Analysis_Screenshot6" src="https://github.com/user-attachments/assets/55f61943-8c98-48e4-b024-6d432bfe271e" />

### 📊Analysis

#### 💡Insights

- 💻 SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- ☁️ Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

   <img width="759" height="513" alt="2_Project_Analysis_Chart3" src="https://github.com/user-attachments/assets/d41e014c-bdeb-4e84-91b3-61efca9cc90a" />

#### 🤔Key Takeaway

- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Skill: Advanced Charts (Pivot Chart)

#### 📈 PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    - 🪙 **Primary Axis:** Median Salary (as a Clustered Column)
    - 👍 **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### 📊 Analysis

#### 💡Insights

- 💰 Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
- 📉 Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

    <img width="862" height="452" alt="2_Project_Analysis_Chart4" src="https://github.com/user-attachments/assets/79afce4a-0b74-422d-8ef9-e9d78a64d088" />

### 🤔Key Takeaway

- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

## Conclusion

This project was completed as part of Luke Barousse's Excel course, where I built an interactive salary dashboard using a real-world dataset of data science job postings. Throughout the project, I applied Excel features such as Power Query, PivotTables, Pivot Charts, formulas, and dashboard design techniques to analyze job titles, salaries, locations, and required skills.

By completing this project, I strengthened my practical Excel and data analysis skills while gaining valuable insights into salary trends across the data job market. It also demonstrated how interactive dashboards can transform raw data into meaningful, data-driven insights that help users better understand career opportunities and salary expectations.
