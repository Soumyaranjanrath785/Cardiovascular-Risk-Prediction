# Cardiovascular-Risk-Prediction


# 1.INTRODUCTION:
The term “heart disease” refers to several types of heart conditions. The most common type of heart disease in the United States is coronary artery disease (CAD), which affects the blood flow to the heart. Decreased blood flow can cause a heart attack.
Sometimes heart disease may be “silent” and not diagnosed until a person experiences signs or symptoms of a heart attack, heart failure, or an arrhythmia. 

When these events happen, symptoms may include

Heart attack: Chest pain or discomfort, upper back or neck pain, indigestion, heartburn, nausea or vomiting, extreme fatigue, upper body discomfort, dizziness, and shortness of breath.

Arrhythmia: Fluttering feelings in the chest (palpitations).
Heart failure: Shortness of breath, fatigue, or swelling of the feet, ankles, legs, abdomen, or neck veins.

# 2. Problem Statement
The objective of the project is to come up with the machine learning model to predict whether a patient has 10-year risk of developing coronary heart disease (CHD) using the residents of the town of Framingham, Massachusetts dataset.

# 3.DATA SUMMARY
The data set is publicly available on the Kaggle website, and it is from an ongoing cardiovascular study on residents of the town of Framingham, Massachusetts. The classification goal is to predict whether the patient has 10-year risk of future coronary heart disease (CHD). The data set provides the patients’ information. It includes over 4,000 records and 15 attributes. Each attribute is a potential risk factor. There are both demographic, behavioral and medical risk factors.

**Attributes:**

Demographic:

* Sex: male or female("M" or "F")

* Age: Age of the patient;(Continuous - Although the recorded ages have been truncated to whole numbers, the concept of age is continuous) Behavioral

* is_smoking: whether or not the patient is a current smoker ("YES" or "NO")

* Cigs Per Day: the number of cigarettes that the person smoked on average in one day.(can be considered continuous as one can have any number of cigarettes, even half a cigarette.)

Medical( history)

* BP Meds: whether or not the patient was on blood pressure medication (Nominal)
* Prevalent Stroke: whether or not the patient had previously had a stroke (Nominal)
* Prevalent Hyp: whether or not the patient was hypertensive (Nominal)
* Diabetes: whether or not the patient had diabetes (Nominal)
Medical(current)

* Tot Chol: total cholesterol level (Continuous)
* Sys BP: systolic blood pressure (Continuous)
* Dia BP: diastolic blood pressure (Continuous)
* BMI: Body Mass Index (Continuous)
* Heart Rate: heart rate (Continuous - In medical research, variables such as heart rate though in fact discrete, yet are considered continuous because of large number of possible values.)
* Glucose: glucose level (Continuous)
Predict variable (desired target)

* 10 year risk of developing coronary heart disease (CHD) — (binary: “1”, means “There is a risk”, “0” means “There is no risk”).
# 4.The General Approachs that I employed:

**Data cleaning and preprocessing:** Here I checked and dealt with missing and duplicate variables from the data set as these can grossly affect the performance of different machine learning algorithms (many algorithms do not tolerate missing data).

**Exploratory Data Analysis:** Here I wanted to gain important statistical insights from the data and the things that I checked for were the distributions of the different attributes, correlations of the attributes with each other and the target variable and I calculated important odds and proportions for the categorical attributes.

**Feature Selection:** Since having irrelevant features in a data set can decrease the accuracy of the models applied, I used Tree-based: SelectFromModel which is an embedded method that uses algorithms that have built-in feature selection methods which were later used to build different models.

**Model development and comparison:** I used four classification models, i.e., 
Logistic Regression, Random Forrest, XGBoost and Support Vector Machine, 
After which I compared the performance of the models using their accuracy and AUC scores. I then settled with the best performing model.

After training each model and tuning their hyper-parameters using grid search, I evaluated and compared their performance using the following metrics:

**The accuracy score:** which is the ratio of the number of correct predictions to the total number of input samples. It measures the tendency of an algorithm to classify data correctly.

**The F1 Score:** Which is defined as the weighted harmonic mean of the test’s precision and recall. By using both precision and recall it gives a more realistic measure of a test’s performance. (Precision, also called the positive predictive value, is the proportion of positive results that truly are positive. Recall, also called sensitivity, is the ability of a test to correctly identify positive results to get the true positive rate).

**The Area under the ROC Curve (AUC):** Which provides an aggregate measure of performance across all possible classification thresholds. It gives the probability that the model ranks a random positive example more highly than a random negative example.


# Observation 

* XGBoost, Randomforest gives highest Accuracy, Recall, Precision and AUC score.
* Highest recall is given by rf model
Overall we can say that the XGboost with hyperparameter tunning was the best performing model across all metrics. 

# 5.CHALLENGES
* Handling the missing values.
* Making data more accurate.
* Selection of important features.
# 6.CONCLUSION
* The number of people who have Cardiovascular heart disease is almost equal between smokers and non-smokers.
* The top features in predicting the ten year risk of developing Cardiovascular Heart Disease are 'age', 'totChol', 'sysBP', 'diaBP', 'BMI', 'heartRate', 'glucose'.
* The XG boost with hyperparameter tunning is the best performing model in terms of accuracy and the F1 score and Its high AUC-score shows that it has a high true positive rate.
* Balancing the dataset by using the SMOTE technique helped in improving the models' sensitivity.
* With more data(especially that of the minority class) better models can be built.
