# CT4101-Portfolio-23324483: Predicting Processing Times for Building Control Applications in Ireland
Portfolio assignment for CT4101 machine learning module. Regression or Classification Problem.

Prediction question: Can characteristics known about a building control application at submission be used to predict the time taken for a decision to be reached? 
This is a regression question. The outcome of the machine learning model is to predict how many days it takes for a building control application to be approved/rejected based on the characteristics of the application.  


# How to download the data and data Information
- Go to https://data.gov.ie/dataset/applications
- Download the csv file entitled 'applications'

- Name: FSC, DAC, Dispensation & Relaxation Applications
- Source: National Building Control Office, from data.gov.ie
- License: Creative Commons Attribution 4.0
- Citation: National Building Control Office (NBCO), FSC, DAC, Dispensation & Relaxation Applications Data 2020–Present, data.gov.ie

# Other Information about this project
- Target variable:  Application processing time in days, obtained from date of submission and date of decision
- Main Input Features: Application type, local authority, classification and use of the proposed building/works, construction type, floor area, number of storeys and site area. 
- Approximate Number of Records: 42,862
- Data-Quality Issues:
Potential missing values in application characteristics and decision dates will need to be investigated. Date variables will need to be converted to appropriate datetime formats, and invalid or inconsistent dates will need to be checked before calculating processing time. Duplicate applications and unrealistic numerical values, such as building areas or heights, will also be investigated. Post-decision variables will be excluded from the predictors to prevent data leakage.
- Proposed Baseline: A baseline regression model that predicts the median processing time of the training data for all applications.
- Candidate Models: Linear Regression, k-Nearest Neighbours (KNN) Regression, and Decision Tree Regression.
- Evaluation Metrics: Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE)
- Privacy, Fairness, Misuse, and Responsible ML Risks:
The dataset contains sensitive information, including applicant names and addresses. These variables will be excluded from modelling as they are unnecessary for predicting processing time. Differences in predicted processing times between local authorities or application types will be interpreted carefully and will not automatically be treated as evidence of differences in authority performance. Predictions will be treated as estimates rather than guarantees of how long an individual application will take.
