# Estimating-the-Remaining-Useful-Life-RUL-of-a-turbofan-engine-of-CMAPSS-dataset-FD004
## Project Objectives:

This project aims to accurately estimate the Remaining Useful Life (RUL) of a turbofan engine using data analysis of CMAPSS dataset FD004. Predicting RUL enables proactive maintenance, reduces costs, and enhances engine safety. By analyzing sensor data and operational conditions, the project seeks to:

1.Identify key features indicative of engine wear.

2.Develop a predictive model for RUL estimation.

3.Validate the model for accurate.

This work supports predictive maintenance in aerospace, helping optimize engine management and safety.

## Data Normalization/Standardization:

After feature selection, we standardized the data to ensure that all features contributed equally to the model training process, improving the stability and performance of subsequent predictive models.
## Adding RUL Columns to the Train set:

We calculated the Remaining Useful Life (RUL) for each row by subtracting the current time cycle from the engine's maximum time cycle (life span). Then, we added this RUL value as a new column in the training set

## Visualizations:

Initially, we standardize the data and then we performed feature extraction by analyzing the train data set by plotting distribution plots. However, this preliminary step did not clearly indicate which features could be removed due to overlapping information across features.    

![Screenshot 2024-11-17 103730](https://github.com/user-attachments/assets/6b9db591-7463-46e1-92ee-12ecba4fe137)

![Screenshot 2024-11-05 181623](https://github.com/user-attachments/assets/14d53c8d-4509-46e1-a7f7-875729d811d8)

## Clustering by Operational Conditions:

To address this, we applied the DBSCAN clustering algorithm, based on altitude, to segment the data into six distinct operational conditions for both the training and testing datasets. This clustering enabled us to plot sensors against RUL, which helped in identifying features that were contributing to noise and complicating the analysis. These features were removed to improve model clarity and focus.

![Screenshot 2024-11-18 115657](https://github.com/user-attachments/assets/b11b384f-461a-4ea6-aed2-358532dbe460)

These are sensor readings for 1 operation condition

![image](https://github.com/user-attachments/assets/6ede0fc4-6848-4f34-b3eb-230c2bbdd7ff)

## Feature Selection using Fisher Score:

Sensors with high fisher scores are selected as critical features in the regression models.

![Screenshot 2024-11-18 221626](https://github.com/user-attachments/assets/d43510f5-ccb6-4c5d-9989-176c02feeec1)

## Model Selection and Evaluation:

### Model 1: Linear Regression

Linear Regression is a simple regression method that models the relationship between features and the target variable by fitting a straight line. It assumes a linear relationship between the predictors (sensor readings) and the Remaining Useful Life (RUL) of the engine. This model served as a baseline for comparison and achieved an RMSE of 40 approximately, providing an initial estimate of prediction accuracy for RUL.

![image](https://github.com/user-attachments/assets/041e6d42-c6a3-423c-bb24-252e0c3f51b1)

### Model 2: Random Forest Regression
Random Forest is an ensemble learning method that constructs multiple decision trees and averages their predictions to improve accuracy and reduce overfitting. Each tree is trained on a random subset of the data, which helps the model generalize well to unseen data. When applied to predict Remaining Useful Life (RUL), the Random Forest model showed improved performance over the baseline Linear Regression, achieving an RMSE of 38 .

![image](https://github.com/user-attachments/assets/4da4a9fe-c58a-487f-8257-2224e93aa1af)
