# Prediction of Stroke Using Machine Learning
  - Melissa Hoover
  - Email:  Hoovermissy@yahoo.com
  - LinkedIn: https://www.linkedin.com/in/melissajhoover/
  - June 2023

![OIP](https://github.com/Mhoover41/Stroke-Prediction/assets/127150137/966e5a72-a867-4534-b655-9dc592dc12ab)

## Project Description
This dataset is used to predict whether a patient is likely to get stroke based on the input parameters like gender, age, various diseases, and smoking status. Each row in the data provides relavant information about the patient.

Data Source: https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset

Data Link: [healthcare-dataset-stroke-data.csv](https://github.com/Mhoover41/Stroke-Prediction/files/11501796/healthcare-dataset-stroke-data.csv)

## Data Dictionary
1) id: unique identifier
2) gender: "Male", "Female" or "Other"
3) age: age of the patient
4) hypertension: 0 if the patient doesn't have hypertension, 1 if the patient has hypertension
5) heart_disease: 0 if the patient doesn't have any heart diseases, 1 if the patient has a heart disease
6) ever_married: "No" or "Yes"
7) work_type: "children", "Govt_jov", "Never_worked", "Private" or "Self-employed"
8) Residence_type: "Rural" or "Urban"
9) avg_glucose_level: average glucose level in blood
10) bmi: body mass index
11) smoking_status: "formerly smoked", "never smoked", "smokes" or "Unknown"*
12) stroke: 1 if the patient had a stroke or 0 if not

Note: "Unknown" in smoking_status means that the information is unavailable for this patient

# Exploratory Analysis
- During the exploratory data analysis, a boxplot and histogram was visualized for each numeric datatype column.
- This gave a good baseline for all of the numeric and categorical columns for univariate EDA.



- There are no outliers and the median Age is 45.



- This is right skewed. The maximum average glucose level is 271. The mean is 106 and median is 92. There is 12.3% outliers on the high side. Since this is a signtificant amount I don't want to lose that much data so I will leave the outliers in place.

# Explanatory Analysis
## Key Questions:
1. What is correlated the most with Stroke occurances?  Age has the highest correlation with Stroke but it is still low.  


2. Is Stroke more likely to occur with age and hypertension?  More strokes occur with higher ages but hypertension did not change much between no stroke and stroke.


3. Is the type of work correlated with higher incidences of Stroke?  Private work type has the most strokes. 


# Machine Learning Models used:
- KNN
- Random Forest
- Logistic Regression

- I also tried each model with and without PCA.  PCA did not improve the performance of any of the models.  
- I did Feature Engineering with each of the models as well and that did not improve model performance.
- I did Under Sampling with each model as well and this is what gave me the best results with each Model. 

# Recommendations: 
## Model Recommended: 
For this business problem, we want to look at F1 score and recall mostly. This is an extremely unbalanced class so accuracy will not be a good metric. Recall in terms of stroke diagnosis would be the percentage of patients who actually have a stroke and are correctly identified by the model. Recall is important metric because missing a stroke case can have serious consequence for the patient's health and recovery.

Overall Random Forest with Under Sampling gave the best results with the lowest False Negatives (Type II Errors) at 18%. The F1 score of our positive class (Stroke) was 22%. Accuracy was 71%. It also had the highest recall on the positive class of 82%.

## Best Model Metrics: 



