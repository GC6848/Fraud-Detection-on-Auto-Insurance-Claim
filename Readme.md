# Project Capstone: Fraud Detection on Auto Insurance Claims 

## Executive Summary
This study seeks to develop a model capable of predicting auto insurance fraud. Through the study, I have created a classification model with a Test AUC of 86%.


## Background

Insurance is a contract, represented by a policy, in which a policyholder receives financial protection or reimbursement against losses from an insurance company. The losses, both big and small, may result from damage to the insured or their property, or from liability for damage or injury caused to a third party. Most insurance policies are made up of core components including premium, deductible and policy limit ([source](https://www.investopedia.com/terms/i/insurance.asp)). 

There are many types of insurance policies and auto insurance is one of the most common types of insurance. Insurance industry is massive in the United States and car insurance is required by law ([source](https://www.investopedia.com/terms/i/insurance.asp)). Each year, more than 7,000 companies collect over \\$1 trillion in premiums. Unfortunately, the industry also provides more opportunities and bigger incentives for committing insurance fraud with total cost of insurance fraud (non-health insurance) estimated to be more than \\$40 billion per year. This insurance fraud cost translates to increase in premium ranging from \\$400 and \$700 per year for the average U.S family ([source](https://www.fbi.gov/stats-services/publications/insurance-fraud)).

By auto insurance alone, fraud already costs auto insurers to lose at least $29 billion a year to staged-crash scams ([source](https://www.fbi.gov/stats-services/publications/insurance-fraud)). Common insurance frauds include inflating claims; misrepresenting facts on an insurance application; submitting claims for injuries or damage that never occurred; and staging accidents ([source](https://www.iii.org/article/background-on-insurance-fraud)).

Because of severity of insurance fraud, 78% of the consumers have expressed their concern about insurance fraud. In addition, 48 states has made insurance fraud a specific crime ([source](https://insurancefraud.org/fraud-stats)).


## Problem Statement

Insurance fraud incurs losses to insurance company. Hence, in this project, I am tasked to develop a model to help auto insurance company to save cost by predicting whether insurance claims is fraudulent or not.

The model is expected to predict if insurance claim is fraudulent based on unseen data, accurately. Metrics used to assess model's prediction are both F1 score and area under curve of the ROC (ROC AUC). These metrics will be compared against a baseline model fraud prediction of F1 score and ROC AUC at 40% and above 50% respectively. 


## Datasets

The datasets used for this analysis are obtained from [Kaggle](https://www.kaggle.com/datasets/buntyshah/auto-insurance-claims-data):

| Dataset | Description |
|---|---|
| insurance_claims.csv | Contains data relating to `months_as_customer`, `age`, `policy_number`, `policy_bind_date`, `policy_state`, `policy_csl`, `policy_deductable`, `policy_annual_premium`, `umbrella_limit`, `insured_zip`, `insured_sex`, `insured_education_level`, `insured_occupation`, `insured_hobbies`, `insured_relationship`, `capital-gains`, `capital-loss`, `incident_date`, `incident_type`, `collision_type`, `incident_severity`, `authorities_contacted`, `incident_state`, `incident_city`, `incident_location`, `incident_hour_of_the_day`, `number_of_vehicles_involved`, `property_damage`, `bodily_injuries`, `witnesses`, `police_report_available`, `total_claim_amount`, `injury_claim`, `property_claim`,`vehicle_claim`, `auto_make`, `auto_model`, `auto_year`, `fraud_reported` and `_c39` |


## This project has been organised into multiple notebooks for ease of navigation and better readability.

#### Overview of technical analysis: 

(1) 1_Problem_Statement,_SQL_ETL_and_Understanding_Data <br>
(2) 2_Preproccessing <br>
(3) 3_Feature_Engineering_Modelling <br>
(4) 4_Fraud_Claim_Analysis_Conclusion_Recommendations

### Fraud Claim Analysis
Fraud analysis has confirmed and verified that model's recommended features indeed have significant positive impacts in detecting fraud as the features have higher fraud ratio compared to other features.

Summary of fraud reported by claim count, overall claim fraud ratio and fraud ratio by insured's hobbies is this [Tableau Dashboard](https://public.tableau.com/app/profile/gerald.chin/viz/fraud_detection_on_auto_insurance_claim/fraud_detection_on_auto_insurance_claim_overview_of_fraud).

### Conclusion
Gaussian Naive Bayes is chosen as the final model as Gaussian Naive Bayes <br>
(1) is not overfitting;   
(2) has highest testing ROC AUC at 86%;  
(3) has high f1 score at 74%; and <br>
(4) can do better classification based on small dataset. ([source](https://www.educba.com/naive-bayes-vs-logistic-regression)).

This model helps to predict fraud and reduce loss from fraud claims, which translates to saving.

### Recommendations
These are the limitations observed: <br>
(1) dataset is small, with data from 1 Jan 2015 to 1 March 2015; <br>
(2) results generalizability limited to Ohio, Illinois and Indiana; <br>
(3) no description for certain columns such as `_c39`, `policy_csl` and `insured_relationship`; <br>
(4) no information on the source of data, whether it is from one insurance company, a few companies or more; and <br>
(5) Naïve Bayes model do not work well if features are correlated.

Hence, it is recommended to <br>
(1) seek clarification on data source and data description; and <br>
(2) continuous training and improving model with more data. 
