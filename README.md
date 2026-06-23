Employee Attrition Analysis

Project Overview:

This project analyzis employee attrition data to identify the key factors that influence employees leaving an organization. Using Python and data analysis libraries, the project performs data cleaning, exploratory data analysis (EDA), correlation analysis, and data visualization to uncover trends related to employee turnover.
The primary objective is to help organizations understand why employees leave and provide insights that can support employee retention strategies.

Dataset:

File: employee_performance_workload_attrition.csv
The dataset contains employee information such as:
•	Department 
•	Role Level 
•	Monthly Salary 
•	Average Weekly Hours 
•	Projects Handled 
•	Performance Rating 
•	Absence Days 
•	Job Satisfaction 
•	Attrition Status (Yes/No) 

Technologies Used:

•	Python 
•	NumPy 
•	Pandas 
•	Matplotlib 
•	Seaborn 
•	Jupyter Notebook 

Project Workflow:

1. Data Loading

The dataset is imported into a Pandas DataFrame for analysis.
import pandas as pd

df = pd.read_csv("employee_performance_workload_attrition.csv")

2. Data Understanding

Basic dataset inspection:
•	Dataset shape 
•	Column names 
•	Data types 
•	Missing values 
df.info()
df.isnull().sum()

3. Data Cleaning:

The following preprocessing steps were performed:
•	Replaced blank values with NaN 
•	Filled missing numerical values using mean 
•	Removed duplicate records 
•	Renamed columns for better readability 
Example:
df[col] = df[col].fillna(df[col].mean())

4. Attrition Analysis:

Overall Attrition Rate:

The percentage of employees who left the organization was calculated using:
attrition_rate = df['attrition'].value_counts(normalize=True) * 100

Department-wise Attrition:

Attrition percentage was analyzed across different departments.
pd.crosstab(
    df['department'],
    df['attrition'],
    normalize='index'
) * 100
Role Level-wise Attrition:

Attrition trends were examined across different employee role levels.
pd.crosstab(
    df['role_level'],
    df['attrition'],
    normalize='index'
) * 100

5. Correlation Analysis:

To determine factors influencing employee attrition, a binary attrition flag was created:
df['attrition_flag'] = df['attrition'].map({
    'Yes': 1,
    'No': 0
})
Correlation analysis was then performed between attrition and:
•	Monthly Salary 
•	Weekly Working Hours 
•	Projects Handled 
•	Performance Rating 
•	Absence Days 
•	Job Satisfaction 

6. Data Visualization:

Several visualizations were created to better understand employee turnover:
Employee Attrition Distribution
•	Pie Chart 
Employees Leaving by Department
•	Bar Chart 
Salary vs Attrition
•	Box Plot 
Job Satisfaction vs Attrition
•	Box Plot 
Correlation Heatmap
•	Heatmap showing relationships between employee attributes and attrition. 

Key Insights:

The analysis helps identify:
•	Departments with higher employee turnover. 
•	Role levels experiencing greater attrition. 
•	Whether salary influences employee retention. 
•	The relationship between job satisfaction and attrition. 
•	How workload and attendance affect employee decisions to leave. 
These insights can assist HR teams in improving employee engagement and retention strategies.

Project Structure:

Employee-Attrition-Analysis/
│
├── Employee Data Analysis.ipynb
├── employee_performance_workload_attrition.csv
├── README.md
└── requirements.txt

Installation:

Clone the repository:
git clone https://github.com/vaishnavi126G/HR-Employee-Attrition-Analysis.git
Install dependencies:
pip install pandas numpy matplotlib seaborn

Run the Project:

Launch Jupyter Notebook:
jupyter notebook
Open:
Employee Data Analysis.ipynb
Run all cells to reproduce the analysis and visualizations.

Future Improvements:

Machine Learning model for attrition prediction. 
•	Interactive dashboards using Power BI or Tableau. 
•	Advanced HR analytics and employee segmentation. 
•	Predictive insights for workforce planning. 

Author:

Vaishnavi G

Employee Attrition Analysis Project using Python, Pandas, Matplotlib, and Seaborn.

