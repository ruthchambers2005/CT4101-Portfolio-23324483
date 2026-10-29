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
-The data will be split via a time-based split using submission date.

# Running the Notebooks
1. Data Inspection and Audit(1).ipynb: This notebook examines the dataset, looking for missing values, duplicates, target distribution and any possible outliers.
2. Data Preparation and Baseline(4).ipynb: This notebook conducts data cleaning, selects predictors, creates the train/test split, states the preprrocessing pipeline and evaluates the baseline regression model.

To run the notebooks:
1. Download/copy the GitHub repository.
2. Download the dataset using the instructions stated above.
3. Install required Python packages using pip -r requirements.txt.
4. Open Jupyter Notebook.
5. Run the data instpection and audit first.
6. Run the data preparation and baseline.

For each notebook, select restart kernel and run all cells to execute the code in order. 

# Project Progress
The following work has been completed: 
- Initial dataset inspection and data-quality assesment.
- Investigation of exact duplicates and repeated apllication references.
- Creation and Validation of the processing-time target variable.
- Missing-data analysis using the supporting BCMS document.
- Initial feature selection and data leakage assesment.
- Investigation of invalid and extreme numerical values.


# Requiremnts
- Python
- Jupyter Notebook
- Required packages listed in requiremnts.txt

# Evaluation Plan
The initial baseline will predict the median application processing time calculated from the training data. 

Model performance will be evaluated using Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).

# Responsible Machine Learning
The project considers data leakage, incomplete records, potentially erroneous measurements and the handling of personal information. direct application identifiers will not be used as model predictors. 

# Assistance and References
External documentation, code sources and any use of generative AI or coding assistants will be acknowledged in the project submission. 
