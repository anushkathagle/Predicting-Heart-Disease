# Predicting-Heart-Disease
Using classification algorithms on labeled dataset to predict heart disease.

The steps we will follow
1. Problem Definition
2. Data: Getting our data
3. Evaluation: Setting our goals/ benchmark to persue our model. 
4. Features: Understanding what information each feature gives. 
5. Modelling
6. Experimentation
7. Evaluation

## 1. Problem Definition
> We are given a labeled dataset with the details of patients and their repective heart disease status. Using **supervised Machine Learning algorithms**, we need to develop a model,which will **predict if a patient is having heart disease or not**, given the patients details.


## 2. Getting the Data 
> We have colleced this data from kaggle https://www.kaggle.com/datasets/rishidamarla/heart-disease-prediction
The original dataset at https://archive.ics.uci.edu/ml/datasets/Heart+Disease
consist of 76 attributes, but all published experiments refer to using a subset of 14 of them. In particular, the Cleveland database is the only one that has been used by ML researchers.

## 3. Setting Our goals.
After looking at the size of data we can set a rough goal for our model performance. If we reach this goal we will further persue the project to improve it's performance. 
> **Expected performace**
 Accuracy = 90%
 
## 4.Features Of our Data

1. age: age in years
2. sex: sex (1 = male; 0 = female)
3. cp: chest pain type
   - Value 1: typical angina 
   - Value 2: atypical angina
   - Value 3: non-anginal pain
   - Value 4: asymptomatic
4. trestbps: resting blood pressure (in mm Hg on admission to the hospital)
5. chol: serum cholestoral in mg/dl
6. fbs: (fasting blood sugar > 120 mg/dl) (1 = true; 0 = false)
7. restecg: resting electrocardiographic results
    - Value 0: normal
    - Value 1: having ST-T wave abnormality (T wave inversions and/or ST elevation or depression of > 0.05 mV)
    - Value 2: showing probable or definite left ventricular hypertrophy by Estes' criteria
8. thalach: maximum heart rate achieved
9. exang: exercise induced angina (1 = yes; 0 = no)
10. oldpeak = ST depression induced by exercise relative to rest
11. slope: the slope of the peak exercise ST segment
    - Value 1: upsloping
    - Value 2: flat
    - Value 3: downsloping
12. ca: number of major vessels (0-3) colored by flourosopy
13. thal: 
    - 3 = normal; 
    - 6 = fixed defect; 
    - 7 = reversable defect
14. num: diagnosis of heart disease (angiographic disease status)
    - Value 0: < 50% diameter narrowing(absence of disease)
    - Value 1: > 50% diameter narrowing(presence of disease)

## 5. Modeling 
We are going to refer to the scikit learn's estimator selection map.
> https://scikit-learn.org/stable/tutorial/machine_learning_map/index.html

Step 1: We have more than 50 samples, so we can move ahead on the next step.
Step 2: We have to decide if we are predicting a category or not. We are predicting if heart disease exist or not.
Step 3: Since, we are using value of 0 to indicate absence and 1 to indicate presence of disease in the data set. Thus, our data is labled.
Step 4: The total sample available in the dataset is less than 100k. So, according to the map first estimator suggestion is Support vector classification. However, our data has a lot of overlapping points according. So, instead we will used logistic regression which uses probabilistic classification model using the sigmoid function.
Step 5: Since, our data is numeric we can choose algorithms like K-Neighbors Classifier and Ensemble classifier.

## 6. Experimenting
Post modeling we will try to tune the hyper parameters to improve the accuracy of our model. 
First, we will try to tune the hyperparameter by hand for KNN using elbow method.
Second, get a general idea of hyperparameter values using randomied CV search.
Finally, do an exhaustive search using grid search.

## 7. Evaluating our final model
As the last step, we will evaluate the performance of our model using the following parameters
1. Confusion Matrics
2. Precision Value
3. Recall Value
4. F1 Score
5. Accuracy
5. Classification Report
6. Roc Curve
7. Auc Value
