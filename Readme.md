# 📊 Student Depression Data Analysis (SQL + Tableau)

This project explores mental health factors among students using SQL Server for preprocessing and Tableau for visualization. It provides key insights into how academic, financial, and lifestyle factors contribute to student depression.

---

## 📁 Dataset

- **File:** `Depression+Student+Dataset.csv`
- **Source:** Simulated for educational purposes
- **Columns:** Gender, Age, Academic Pressure, Financial Stress, Study Hours, Sleep Duration, Student Satisfaction, Depression, etc.

---

## 🛠️ Tools Used

| Tool           | Purpose                        |
|----------------|--------------------------------|
| SQL Server     | Data preprocessing and cleaning |
| Tableau Desktop| Interactive data visualization |
| Excel/CSV      | Raw data source                 |

---

## 🔧 SQL Preprocessing Steps

```sql
-- Create database
CREATE DATABASE [Tableau Project];

-- Clean gender column
UPDATE [dbo].[Depression+Student+Dataset]
SET Gender = 'F' WHERE Gender = 'Female';
UPDATE [dbo].[Depression+Student+Dataset]
SET Gender = 'M' WHERE Gender = 'male';

-- Add age group column
ALTER TABLE [dbo].[Depression+Student+Dataset]
ADD Age_group VARCHAR(MAX);

UPDATE [dbo].[Depression+Student+Dataset]
SET Age_group = CASE
    WHEN Age BETWEEN 18 AND 24 THEN 'A1'
    WHEN Age BETWEEN 25 AND 30 THEN 'A2'
    ELSE 'A3'
END;

-- Add index column
ALTER TABLE [dbo].[Depression+Student+Dataset]
ADD index_column INT IDENTITY(1,1);

-- Modify Depression column
ALTER TABLE [dbo].[Depression+Student+Dataset]
ALTER COLUMN Depression VARCHAR(MAX);
UPDATE [dbo].[Depression+Student+Dataset]
SET Depression = 'Yes' WHERE Depression = '1';
UPDATE [dbo].[Depression+Student+Dataset]
SET Depression = 'No' WHERE Depression = '0';

-- Modify binary columns to True/False
UPDATE [dbo].[Depression+Student+Dataset]
SET have_you_ever_had_suicidal_thoughts = 'True' WHERE have_you_ever_had_suicidal_thoughts = '1';
UPDATE [dbo].[Depression+Student+Dataset]
SET have_you_ever_had_suicidal_thoughts = 'False' WHERE have_you_ever_had_suicidal_thoughts = '0';



UPDATE [dbo].[Depression+Student+Dataset]
SET Family_History_of_Mental_Illness = 'True' WHERE Family_History_of_Mental_Illness = '1';
UPDATE [dbo].[Depression+Student+Dataset]
SET Family_History_of_Mental_Illness = 'False' WHERE Family_History_of_Mental_Illness = '0';

#📊 Tableau Dashboard Overview
Academic Pressure vs Student Count – Bar chart

Financial Stress vs Student Count – Bubble chart

Study Hours vs Student Count – Line chart

Sleep Duration vs Student Count – Donut chart

Student Satisfaction vs Student Count – Bar chart

#📈 Insights
Academic Pressure

AP1 and AP3 have high student counts; AP2 is lowest.

Financial Stress

FS1 and FS2 dominate; severe FS levels are less common.

Study Hours

Most students study ~10 hrs/week; moderate workloads are typical.

Sleep Duration

7–8 hrs and >8 hrs are most common; <5 hrs also significant.

Student Satisfaction

Higher satisfaction levels (SS3, SS4) dominate.

Lower satisfaction (SS1) is underrepresented.

#🔍 Key Takeaways
Moderate study schedules and sleep are common among students.

Financial stress and low satisfaction may contribute more to depression.

Preventive mental health strategies should focus on early signs like dissatisfaction or poor sleep patterns.

#🎓 Learning Outcomes
Data cleaning and transformation using SQL

Building interactive dashboards with Tableau

Extracting actionable insights from real-world data

Storytelling through data visualization

#📎 Files Included
Depression+Student+Dataset.csv – Raw dataset

Student_Depression_Data_Analysis_Final_Readme.pdf – Full walkthrough
📊 Tableau Dashboard Overview
Academic Pressure vs Student Count – Bar chart

Financial Stress vs Student Count – Bubble chart

Study Hours vs Student Count – Line chart

Sleep Duration vs Student Count – Donut chart

Student Satisfaction vs Student Count – Bar chart

📈 Insights
Academic Pressure

AP1 and AP3 have high student counts; AP2 is lowest.

Financial Stress

FS1 and FS2 dominate; severe FS levels are less common.

Study Hours

Most students study ~10 hrs/week; moderate workloads are typical.

Sleep Duration

7–8 hrs and >8 hrs are most common; <5 hrs also significant.

Student Satisfaction

Higher satisfaction levels (SS3, SS4) dominate.

Lower satisfaction (SS1) is underrepresented.

🔍 Key Takeaways
Moderate study schedules and sleep are common among students.

Financial stress and low satisfaction may contribute more to depression.

Preventive mental health strategies should focus on early signs like dissatisfaction or poor sleep patterns.

🎓 Learning Outcomes
Data cleaning and transformation using SQL

Building interactive dashboards with Tableau

Extracting actionable insights from real-world data

Storytelling through data visualization

#📎 Files Included
Depression+Student+Dataset.csv – Raw dataset

Readme.pdf – Full walkthrough

Student_depression_project.png – Tableau screenshot 

Student_depression(SQL+TABLEAU).twbx – Tableau workbook file 
SQL_Student_depression.sql -sql query

📌 Author
Ashwini Koppula
🔗 GitHub Profile

.png – Tableau screenshot 
.twbx – Tableau workbook file
.sql-sql files ssms
📌 Author
Ashwini Koppula
🔗 GitHub Profile


