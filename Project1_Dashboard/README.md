# Excel Salary Dashboard

<img width="800" height="333" alt="1_Salary_Dashboard_Final_Dashboard" src="https://github.com/user-attachments/assets/41baf685-fe47-4983-aa30-e4d8b0a1912a" />

## Introduction

This Salary Dashboard is a project I completed while following Luke Barousse's Excel course. I built the dashboard alongside the lessons, applying each concept step by step to gain hands-on experience with Excel for data analysis and visualization.

The dashboard analyzes salary data for various data-related job roles, allowing users to explore salary trends based on job title, location, and key skills. Throughout this project, I used Excel features such as Power Query, Pivot Tables, Pivot Charts, Slicers, and interactive dashboard elements to transform raw data into meaningful insights.

This project helped strengthen my practical Excel skills and provided valuable experience in building professional, interactive dashboards from real-world datasets.

### Dashboard File
My final dashboard is in [Salary Dashboard_project1.xlsx](Salary%20Dashboard_project1.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. It was provided as part of Luke Barousse's Excel course, where it is used to teach data analysis and dashboard creation in Excel. The dataset includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

<img width="1336" height="867" alt="1_Salary_Dashboard_Chart1" src="https://github.com/user-attachments/assets/0bbff8f2-457b-4670-aff4-ba1005035397" />

- 🛠️ **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- 🎨 **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- 📉 **Data Organization:** Sorted job titles by descending salary for improved readability.
- 💡 **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### 🗺️ Country Median Salaries - Map Chart

<img width="800" height="430" alt="1_Salary_Dashboard_Country_Map" src="https://github.com/user-attachments/assets/8346e2e3-59e4-4c21-8088-d601cdee3ea8" />

- 🛠️ **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- 🎨 **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
- 📊 **Data Representation:** Plotted median salary for each country with available data.
- 👁️ **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- 💡 **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

- 🔍 **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- 📊 **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- 🎯 **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- **🔢 Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

🍽️ Background Table  

<img width="265" height="220" alt="1_Salary_Dashboard_Screenshot1" src="https://github.com/user-attachments/assets/478464f3-fa3d-42f1-9996-07bab7725903" />

📉 Dashboard Implementation  

<img width="1148" height="1214" alt="1_Salary_Dashboard_Job_Title" src="https://github.com/user-attachments/assets/4fc494c6-3631-4857-bbed-7453f7e08cbb" />

#### ⏰ Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- 🔍 **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- **🔢 Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

🍽️ Background Table

<img width="195" height="119" alt="1_Salary_Dashboard_Screenshot2" src="https://github.com/user-attachments/assets/76275e84-8785-4cff-8671-b029be40c785" />

📉 Dashboard Implementation:

<img width="942" height="1212" alt="1_Salary_Dashboard_Type" src="https://github.com/user-attachments/assets/b4c7a6b3-dc34-443d-a6f5-fddc14e7f548" />

### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - 🎯 User input is restricted to predefined, validated schedule types
    - 🚫 Incorrect or inconsistent entries are prevented
    - 👥 Overall usability of the dashboard is enhanced

 <img width="624" height="602" alt="1_Salary_Dashboard_Data_Validation" src="https://github.com/user-attachments/assets/7ce6faba-dba9-4ca6-86c8-5c65db009800" />

## Conclusion

I created this dashboard as part of Luke Barousse's Excel course to analyze salary trends across various data-related job roles. Using the dataset provided in the course, the dashboard enables users to explore how factors such as job title, location, and employment type influence salaries. This project demonstrates my ability to clean, analyze, and visualize data using Excel while building an interactive dashboard that supports data-driven career insights.
