# Trustly Bank Human Resources Employee Turnover Analysis

## Problem Statement 

I was tasked by an HR Specialist from the Seattle HQ of Trustly Bank to investigate employee turnover rates in correlation with education and department. I was sent an Excel file to run my analysis. During a meeting, we discussed specific requirements for this project. We discussed in more detail that the company had noticed an uptick in employee turnover and would like to explore some possible directions to look into further. They suspect that employee education and job title may explain the increase, but they need more solid evidence. To discover these insights, I will work heavily in Excel to extract and calculate more relevant information. After this, I will make a Power BI dashboard to present to managers and stakeholders. Stakeholders also require a general HR overview, which will be incorporated into the same dashboard.

## Data Structure

The Excel I was sent has a few errors, making cleanup simple. The main task will be separating tables and writing formulas to calculate turnover related to education and the department. Here is a rundown of the columns I have to start with.

We have employee_id, first_name, last_name, gender, birth_date, age, hire_date, tenure_years, job_title, department, location_state, performance_rating, promotion_last_3yrs, attrition, employment_status, termination_date, salary, education_level.

These columns provide a solid starting point. Later on, there will be some calculated columns that will aid in visualization and analysis.

### Data Dictionary
| Column Name         | Description                                                                                  |
|---------------------|----------------------------------------------------------------------------------------------|
| employee_id         | The ID number associated with an employee, starting with 'TR-' followed by 5 digits.         |
| first_name          | First name of employee                                                                       |
| last_name           | Last Name of employee                                                                        |
| gender              | Gender employee                                                                              |
| birth_date          | Birth date of employee                                                                       |
| age                 | Age of employee                                                                              |
| hire_date           | The date on which the employee was hired                                                     |
| tenure_years        | Number of years the employee has been employed, represented as an integer                    |
| job_title           | The title of the job for which the employee is hired                                         |
| department          | The department for which the employee's job title is under                                   |
| location_state      | State where the employee is employed                                                         |
| performance_rating  | On a scale from 1-5, 5 being the best, how well the employee's performance is rated          |
| promotion_last_3yrs | 1 if the employee was given a promotion in the last 3 years, 0 if not                        |
| attrition           | Yes if the employee has been terminated, no if they are still employed                       |
| employment_status   | Employees are labelled as either active, on leave, or terminated                             |
| termination_date    | The date on which the employee was terminated, left blank if they are still employed         |
| salary              | How much the employee is paid per year                                                       |
| education_level     | The highest level of education attained, high school, associate, bachelor, master, doctorate |

## Excel Work

The bulk of the calculations for the dashboard take place in Excel. We start with the initial sheet that was provided and create more for each education level and department. To calculate turnover rates, we use the formula:

`(# terminations) / (avg # Employees)`

Each sheet for every department and education level will have the same layout:

| Column Name    | Description                                                                                     |
|----------------|-------------------------------------------------------------------------------------------------|
| year           | The year the data in the same row is associated with                                            |
| employee_begin | The number of employees at the beginning of the year                                            |
| terminations   | The number of terminations in the year                                                          |
| employee_end   | The number of employees at the end of the year                                                  |
| avg_employees  | The average number of employees in the year, calculated by: `[(employee_begin+employee_end)/2]` |
| turnover_rate  | The turnover rate for the year                                                                  |

## Power BI Work

Now that all of these sheets are made, the entire workbook can be imported into Power BI. For each department table, I added a new column that labels the department, and similarly, with education levels. Then, I used Power Query to combine all department tables and education tables into dept_turnover and edu_turnover tables respectively. After this, I am left with three main tables to work with: trustly_hr_dataset, dept_turnover, and edu_turnover.

## Visualization

### Overview

![image](https://github.com/user-attachments/assets/e1f0949b-c9da-4c97-9df3-3ab527e8f666)

The first visual is a total of current employees and terminations per year. The number is the total up to date. The charts show that both hiring and termiantions are trending up, with more hiring than terminating.

---

![image](https://github.com/user-attachments/assets/78d64456-30c9-4e5d-8e1e-ab8a66c4db13)

This donut chart shows the distribution of male and female employees out of the total current employees. The compamy has a slight bit more female than male employees.

---

![image](https://github.com/user-attachments/assets/816a0ac5-5042-42c8-9a5d-dd404e078b61)

This shows the distribution of current employees among different age groups. We hire mostly among the ages of 25-64, with steep drop offs in 17-24 and 65+. This makes sense with retirements and employees being too young/ inexperienced. 

---

![image](https://github.com/user-attachments/assets/a65b34f3-8006-42c7-a8e5-1479c04c9fec)

Here is a graphic that shows branch locations. This shows we have branches in Washington (Seattle, Spokane), Montana (Billings), Oregon (Portland, Eugene), and Idaho (Boise). The company headquarters is in Seattle. The size of each bubble is representative of the amount of employees in the state. 

---

![image](https://github.com/user-attachments/assets/7fd7a248-aa78-4639-ba20-d1723260c089)

Here is the distribution of employees by department. The distribution is as expected, with retail banking at the top, and legal at the bottom.

---

![image](https://github.com/user-attachments/assets/058da2fa-3bac-4bba-8e91-087b87038f7c)
![image](https://github.com/user-attachments/assets/556af292-f208-44d1-a70a-5337f2d23acf)

These two matrices show a numerical analysis of turnover rates by education and department. Customer support has seen a rise in turnover in the last three years, and make up most of the turnovers in recent years. Human resources has also seen some increase. Employees with only high school education have seen the most turn over, with associate degree holders being a close second. It appears that the gap in turnover between high school and associate is mcuh smaller than associate and bachelor. Employees with a doctorate have the lowest turnover as expected. 













