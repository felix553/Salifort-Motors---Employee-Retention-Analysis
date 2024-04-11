# Salifort-Motors---Employee-Turnover-Analysis


## Introduction 
This project aims to improve understanding of the deciding factors behind employee turnover at Salifort Motors. We achieve this by training a classifier model on a past HR dataset to predict whether an employee will leave the company based on a variety of factors. The final XGB classifier boasts a F1 score of 0.99 and accuracy of 0.99. Based on the model, the most influential factors behind employee turnover are years spent at the company, reported satisfaction level, number of projects and their last project evaluation.  

## Business Understanding 
High turnover rates can negatively affect the morale and engagement of remaining employees, they can also be expensive for organisations. The model aims to predict whether an employee will leave the company and identify which factors are most influential. These insights can help HR make proactive decisions to improve employee retention. By identifying risk factors and early warning signs, organisations can take preventive measures to mitigate turnover. 


## Data Understanding 
The dataset can be found on kaggle and contains 14,999 rows of self-reported information from employees of a multinational vehicle manufacturing corporation. 

## Data Dictionary 
| Column name            | Type   | Description                                                  |
|------------------------|--------|--------------------------------------------------------------|
| satisfaction_level     | int64  | The employee’s self-reported satisfaction level [0-1]        |
| last_evaluation        | int64  | Score of employee's last performance review [0–1]            |
| number_project         | int64  | Number of projects employee contributes to                   |
| average_monthly_hours  | int64  | Average number of hours employee worked per month            |
| time_spend_company     | int64  | How long the employee has been with the company (years)      |
| work_accident          | int64  | Whether or not the employee experienced an accident at work  |
| left                   | int64  | Whether or not the employee left the company                 |
| promotion_last_5years  | int64  | Whether or not the employee was promoted in the last 5 years |
| department             | str    | The employee's department                                    |
| salary                 | str    | The employee's salary (low, medium, or high)                 |

## Modeling and Evaluation  
A total of 4 classifiers were developed: DecisionTree, RandomForest, Logistic Regression and XGB. XGB which was the best performing model was then tuned using gridsearch to develop the final model. 

Pre-Processing included checking for blank rows, duplicates, and validating data. Feature transformations included encoding dummy variables for department and finally label encoding salary. 

### Performance
![3b1a5698-764b-4bf2-8f32-2684eda99d3e](https://github.com/felix553/Salifort-Motors---Employee-Turnover-Analysis/assets/81670336/a344b5ac-6b10-40f0-8c16-f972d9d4e46b)

|                           | precision | recall | f1-score | support |
|---------------------------|-----------|--------|----------|---------|
| Predicted would not leave |    0.99   |  1.00  |   0.99   |   1857  |
| Predicted would leave     |    0.98   |  0.95  |   0.96   |    377  |
|---------------------------|-----------|--------|----------|---------|
|        accuracy           |           |        |   0.99   |   2234  |
|       macro avg           |    0.98   |  0.97  |   0.98   |   2234  |
|    weighted avg           |    0.99   |  0.99  |   0.99   |   2234  |


![e393d1b7-fcb1-41ce-8592-444f7237d16a](https://github.com/felix553/Salifort-Motors---Employee-Turnover-Analysis/assets/81670336/8d47c2a0-9510-483d-aaaa-a9b87e9614e1)

From this diagram we can see the top 10 more influential factors behind employee turnover at Salifort Motors. The diagram draws attention to the accounting and sales departments as they have been labelled as indicators of employees leaving the company. Overall, a noticeable driving factor of employee turnover is evidently dissatisfaction due to overwork. The comapny should consider reducing individual workloads of certain individuals with a relatively high monthly work hours. 


## Conclusion 
The model performs extremely well at classifying employee turnover. The company should either thoroughly review their work quotas, or consider rewarding employees for working longer hours, as well as consider promoting employees who have been with the company for a long time to promote overall employee satisfaction and retention. 

