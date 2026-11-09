# CT4101-Portfolio-23324483: Predicting Processing Times for Building Control Applications in Ireland
Portfolio assignment for CT4101 machine learning module. This project investigates a supervised regression problem.

Prediction question: Can characteristics known about a building control application at submission be used to predict the time taken for a decision to be reached? 
This is a regression question. The outcome of the machine learning model is to predict how many days it takes for a building control application to be approved/rejected based on the characteristics of the application.  


# How to download the data and data Information
- Go to https://data.gov.ie/dataset/applications
- Download the csv file entitled 'applications'
- Create a folder named CT4101 Portfolio and then a folder inside that called Data inside the project directory and save the downloaded csv file there. 

- Name: FSC, DAC, Dispensation & Relaxation Applications
- Source: National Building Control Office, from data.gov.ie
- License: Creative Commons Attribution 4.0
- Citation: National Building Control Office (NBCO), FSC, DAC, Dispensation & Relaxation Applications Data 2020–Present, data.gov.ie

# Other Information about this project
- Target variable:  Application processing time in days, obtained from date of submission and date of decision
- Main Input Features: Application type, local authority, classification and use of the proposed building/works, construction type, floor area, number of storeys and site area. 
- Approximate Number of Records: Initial: 43,619, after removing duplicated: 42,862, after cleaning and preparation: 42,711
- Data-Quality Issues:
  The dataset was investigated for missing values, duplicate applications, inconsistent dates and potentially unrealistic numerical values. Date variables were converted into datetime formats, and invalid processing times were excluded.
Variables containing information unavailable at the time of submission were excluded from the model predictors to reduce the risk of data leakage.
- Proposed Baseline: A baseline regression model that predicts the median processing time of the training data for all applications.
- Candidate Models: Linear Regression, k-Nearest Neighbours (KNN) Regression, and Decision Tree Regression.
- Evaluation Metrics: Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE)
- Privacy, Fairness, Misuse, and Responsible ML Risks:
The dataset contains sensitive information, including applicant names and addresses. These variables will be excluded from modelling as they are unnecessary for predicting processing time. Differences in predicted processing times between local authorities or application types will be interpreted carefully and will not automatically be treated as evidence of differences in authority performance. Predictions will be treated as estimates rather than guarantees of how long an individual application will take.
  An 80/20 time-based split was used based on submission date, earlier applications used for training and later applications retained for modelling. 

# Running the Notebooks
1. Data Inspection and Audit(1).ipynb: This notebook examines the dataset, looking for missing values, duplicates, target distribution and any possible outliers.
2. Data Preparation and Baseline(4).ipynb: This notebook conducts data cleaning, selects predictors, creates the train/test split, states the preprocessing pipeline and evaluates the baseline regression model.
3. Model Comparison and Evaluation.ipynb: This notebook trains evaluates 3 regression models(Linear Regression, Decision Tree Regression and KNN Regression) to see how they perform in comparison to the median baseline model. It also includes model visualisation and error analysis. 

To run the notebooks:
1. Download/copy the GitHub repository.
2. Download the dataset using the instructions stated above.
3. Install required Python packages using pip install -r requirements.txt.
4. Open Jupyter Notebook.
5. Run the data instpection and audit first.
6. Run the data preparation and baseline.
7. Run the model comparison and evaluation.

For each notebook, select restart kernel and run all cells to execute the code in order. 

# Project Progress
The following work has been completed: 
- Initial dataset inspection and data-quality assessment.
- Investigation of exact duplicates and repeated apllication references.
- Creation and Validation of the processing-time target variable.
- Missing-data analysis using the supporting BCMS document.
- Initial feature selection and data leakage assesment.
- Investigation of invalid and extreme numerical values.
- Final Preparation of the modelling dataset containing 42,711 observations.
- Selection of 12 predictor variables.
- Constructed  a preprocessing pipeline, using numerical and categorical imputation and one-hot encoding.
- Implementation of a median DummyRegressor baseline.
- Evaluation of the baseline using MAE and RMSE.
- Implementation and evaluation of Linear Regression, Decision Tree Regression and KNN Regression models.
- Investigation of the 3 KNN hyperparameters using a time-based train/test split.
- Comparison of the 3 regression models against the median baseline using MAE and RMSE.
- Visualisation of the Decision Tree and its residuals.
- Error analysis investigating the largest absolute prediction errors.
- Identification of the median baseline as the best-performing model on the current test dataset.


# Requirements
- Python
- Jupyter Notebook
- Required packages listed in requiremnts.txt

# Model Evaluation and Results
A median baseline model and three learned regression models (Linear Regression, Decision Tree Regression and KNN Regression) were evaluated using a time-based 80/20 training and testing split.

Model performance was assessed using Mean Absolute Error (MAE), Root Mean Squared Error (RMSE) and R².

| Model | MAE (days) | RMSE (days) |
|---------------------------|------|------|------|
| Median Baseline | 32.861 | 52.781 |
| Linear Regression | 50.124 | 59.243 | 
| Decision Tree Regression | 45.941 | 63.530 | 
| KNN Regression | 51.441 | 76.800 |

The median baseline achieved the lowest MAE and RMSE. Among the learned regression models, Decision Tree Regression achieved the lowest MAE, while Linear Regression achieved the lowest RMSE.

Further details, visualisations and error analysis are provided in the Model Comparison and Evaluation notebook.

# Responsible Machine Learning
The project considers data leakage, incomplete records, potentially erroneous measurements and the handling of personal information. direct application identifiers will not be used as model predictors. 

# Assistance and References
ChatGPT by OpenAI was used as a learning resource throughout this project to help understand machine learning concepts and help manage the assignment requirements. AI was used to help find data-cleaning approaches, understand preprocessing pipelines, explain evaluation metrics and model settings based on the modules lecture notes and to help find useful documentation for Python online. The CT4101 lecture notes, the pandas website as well as scikit-learn website were the main resources of learning and finding examples of code. https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html , https://scikit-learn.org/stable/index.html, https://matplotlib.org/stable/
