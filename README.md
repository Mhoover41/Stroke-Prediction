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

![Age Hist and Box plot](https://github.com/Mhoover41/Stroke-Prediction/assets/127150137/914d2a9b-aafd-4970-9437-731fa7811f58)

- There are no outliers and the median Age is 45.

![Avg Glucose Hist and Box Plot](https://github.com/Mhoover41/Stroke-Prediction/assets/127150137/0072566f-11c8-403f-8bce-174c5ada132a)

- This is right skewed. The maximum average glucose level is 271. The mean is 106 and median is 92. There is 12.3% outliers on the high side. Since this is a signtificant amount I don't want to lose that much data so I will leave the outliers in place.

# Explanatory Analysis
## Key Questions:
1. What is correlated the most with stroke occurances?  Age has the highest correlation with stroke but it is only 25%.  

![Heatmap](https://github.com/Mhoover41/Stroke-Prediction/assets/127150137/c2f7b74a-7241-450a-a790-99539c760d59)

2. Is Stroke more likely to occur with age and hypertension?  More strokes occur with higher ages. Hypertension does not appear to be correlated with stroke.

![Age by Hypertensin with Stroke](https://github.com/Mhoover41/Stroke-Prediction/assets/127150137/28dcfcbf-e4aa-4156-9f19-c750e1db1b59)

3. Which type of work results with higher incidences of stroke?  Private work type has the most strokes. 

![Stroke by WorkType](https://github.com/Mhoover41/Stroke-Prediction/assets/127150137/eed12cfc-f622-4d59-9bcd-971e414d6d72)

4.  Is Average Glucose Level correlated with Stroke?  It has a low correlation but the graph shows that higher Average Glucose Levels results in more strokes.

![Avg Glucose Level with Stroke](https://github.com/Mhoover41/Stroke-Prediction/assets/127150137/eea8174e-5fa0-4665-932e-166349542395)


# Machine Learning Models used:
- KNN
- Random Forest
- Logistic Regression

    - I also tried each model with and without PCA.  PCA did not improve the performance of any of the models.  
    - I did feature engineering with each of the models as well and that did not improve model performance.
    - I did under sampling with each model as well and this is what gave me the best results with each model. 

# Recommendations: 
## Model Recommended: 
For this business problem, we want to look at F1 score and recall mostly. This is an extremely unbalanced class so accuracy will not be a good metric. Recall in terms of stroke diagnosis would be the percentage of patients who actually have a stroke and are correctly identified by the model. Recall is important metric because missing a stroke case can have serious consequence for the patient's health and recovery.

- Overall Logistic Regression with Under Sampling gave the best results with the lowest False Negatives (Type II Errors) at 19%. The F1 score of our positive class (Stroke) was 24%. Accuracy was 74%. It also had the highest recall on the positive class of 81%.

## Best Model Metrics: 

![Revised Final Metric](https://github.com/Mhoover41/Stroke-Prediction/assets/127150137/37b3e77d-e3b6-4e91-b16d-2fb183a010b3)


