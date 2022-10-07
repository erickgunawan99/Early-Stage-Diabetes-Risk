# Early-Stage-Diabetes-Risk

# Abstract
This project aims to select the best classifier algorithm than can predict whether someone has an early stage diabetes risk or not using an available public dataset.

# Data Understanding
* The data can be downloaded at 
  https://www.kaggle.com/datasets/ishandutta/early-stage-diabetes-risk-prediction-dataset
* The data was collected by questionnaires from the patients of Sylhet Diabetes Hospital in Sylhet, Bangladesh 
  and has been approved by a doctor
* It contains 17 columns, 16 of them are categorical columns with binary response and 1 "Age" column that consists a numerical value

# Exploratory Data Analysis
* There are no missing values nor duplicates found
* The categorical columns has been encoded accordingly


# Features Selection
* Chi-square method was used to analyse the significance of each categorical columns with respect to the diabetes class column
  | Features             | P-Value|
  | -------------        |:------:|
  | Gender               | 0.0    |
  | Polyuria             | 0.0    |
  | Polydipsia           | 0.0    |
  | Sudden Weight Loss   | 0.0    |
  | Weakness             | 0.002  |
  | Polyphagia           | 0.0    |
  | Genital Thrush       | 0.01   |
  | Visual Blurring      | 0.0002 |
  | Itching              | 0.7    |
  | Irritability         | 0.0    |
  | Delayed Healing      | 0.5    |
  | Partial Paresis      | 0.0    |
  | Muscle Stiffness     | 0.1    |
  | Alopecia             | 0.0    |
  | Obesity              | 0.25   | 
 
* Seperate scatter plot to visualize age and diabetes class relationship
 
![age](age-class-scatter.png)

* "Itching", "Delayed Healing, "Muscle Stiffness", and "Obesity" show insignificant relationship as reflected by the high p-value and "Age" doesn't provide a distinction between the positive and negative diabetic classes.

# Model Selection
  Three classifier models; Logistic Regression, K-Nearest Neighbors, and Random Forest; were examined using a ten-fold cross validation. 
  | Models              | Accuracy | Precision | Recall | F1    |
  | ---------------     | -------- | --------  | ------ | ----- |
  | K-Nearest Neighbors | 0.85     | 0.95      | 0.79   | 0.86  |
  | Logistic Regression | 0.91     | 0.95      | 0.91   | 0.93  |
  | Random Forest       | 0.97     | 0.98      | 0.98   | 0.98  |
  
  Random Forest has the best score in all front and especially far ahead in the "Recall" score, which is the most important metric because in the nature of disease prediction model, false negative is the priority to minimize.
 
 # Model Evaluation (Random Forest)
 The random forest classifier model was fit into the dataset without feature elimination and with feature elimination involved to compare the result.
|      With All Features        |
| ---------------------------   |
| True Positive: 70             |
| True Negative: 33             |
| False Positive: 0             |
| False Negative: 1             |
| Precision: 1.0                |
| Recall: 0.9859154929577465    |
| F1-Score: 0.9929078014184397  |
  
  
  
  
  
  
