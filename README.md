# Trustly Bank Human Resources Employee Turnover Analysis

## Problem Statement 

I was tasked by an HR Specialist from the Seattle HQ of Trustly Bank to investigate employee turnover rates in correlation with education and department. I was sent an Excel file to run my analysis. During a meeting, we discussed specific requirements for this project. We discussed in more detail that the company had noticed an uptick in employee turnover and would like to explore some possible directions to look into further. They suspect that employee education and job title may explain the increase, but they need more solid evidence. To discover these insights, I will work heavily in Excel to extract and calculate more relevant information. After this, I will make a Power BI dashboard to present to managers and stakeholders. Stakeholders also require a general HR overview, which will be incorporated into the same dashboard.

## Data Structure

The Excel I was sent has a few errors, making cleanup simple. The main work will be separating tables and writing formulas to calculate turnover concerning education and the department. Here is a rundown of the columns I have to start with.

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

