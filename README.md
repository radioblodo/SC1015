# SC1015: DSAI Mini Project - Predicting Stroke using various factors

School of Computer Science and Engineering | Nanyang Technological University \
Lab: B134 \
Team 1 

Members 
  1. Chai Zi Liang ([@radioblodo](https://github.com/radioblodo))
  2. Ian Boo Jing Yong ([@sirwoofles](https://github.com/sirwoofles))
  3. Ng Yin Ming ([@badbananaa](https://github.com/badbananaa))
 
---
### Description
This repository contains all the Jupyter Notebooks, datasets, video presentations, and the source materials/references we have created and used as part of the Mini Project for SC1015: Introduction to Data Science and AI.

This README briefly highlights what we have accomplished in this project. If you want a more detailed explanation of things, please refer to the the Jupyter Notebooks. For clarity, we have divided our project into 9 sections.

---
### Table of Contents:
1. [Problem Definition](#1-Problem-Definition)
2. [Data Preparation and Cleaning](#2-Data-Preparation-and-Cleaning)
3. [Exploratory Data Analysis](#3-Exploratory-Data-Analysis)
4. [Decision Tree Classifier](#4-Decision-Tree-Classifier)
5. [Logistic Regression](#5-Logistic-Regression)
6. [K Nearest Neighbour (KNN)](#6-K-Nearest-Neighbour-(KNN))
7. [Gaussian Naïve Bayes](#7-Gaussian-Naïve-Bayes)
8. [Conclusion](#8-Conclusion)
9. [References](#9-References)
---
### 1. Problem Definition
Can we predict the probability of getting stroke and thus take measures to prevent it? If so, which model would be the most helpful in making this prediction?

**Our Dataset:** ['Diabetes, Hypertension and Stroke Prediction' from Kaggle](https://www.kaggle.com/datasets/prosperchuks/health-dataset) \
**Our Problem:** We decided to focus on Stroke Prediction. How can we predict the probability of getting stroke? And can we take measures to prevent it? If so, which model would be the most helpful in predicting?

**Practical Motivation:** We believe that this dataset as well as the problem we pose is relavant to the Singapore context. This is because Stroke is currently Singapore's 4th leading cause of death, comprising of 6.8% of all deaths in Singapore. By learning the various reasons contributing to Stroke, we might be able to predict an individual's risk for Stroke. And we can also recommend actions based on data driven insights to reduce the individual's risk to Stroke.

### 2. [Data Preparation and Cleaning](https://github.com/radioblodo/SC1015/blob/main/Data_Cleaning.ipynb) 
Within this section, we have prepped and cleaned the dataset to facilitate the analysis of the data and for the machine learning models in subsequent sections.

Steps we took for this section:
1. **Preliminary Feature Selection:** Out of '10' Variables, we drop variables 'work_type' and 'Residence_type' that we think are not relevant or feasible for exploration. 
2. **Change Variable Types:** In the original dataset, the data types of categorical variables were labelled as 'int64' or 'float64'. So we changed their data types to 'category'
3. **Dropping 'NaN's:** All the 'NaN' values in our dataset were dropped.
4. **Removing of age<0:** All the rows with values <0 for `age` were removed.
5. **Exported a csv file of the cleaned dataset to be used in subsequent sections**

### 3. [Exploratory Data Analysis](https://github.com/radioblodo/SC1015/blob/main/Exploratory_Data_Analysis.ipynb) 
Afterwards, we conducted Exploratory Data Analysis on our DataFrame, which involved generating different graphs to visualize potential patterns within the variables. Subsequently, we established the correlation between the variables and Stroke, and deduced some inferences to address our problem at this stage.

We did the following:
1. **Explored `Sex` and relationship with `Stroke`**: This is a categorical variable of 2 categories 'Male' and 'Female'. We found that Females were more likely to suffer from Stroke.
2. **Explored `age` and relationship with `Stroke`**: This is a numerical variable for age of the people in the dataset. We learnt that the median age of those suffering from Stroke is greater.
3. **Explored `hypertension` and relationship with `Stroke`**: This is a categorical variable of those with and without hypertension. There is a strong correlation of hypertension and Stroke.
4. **Explored `heart_disease` and relationship with `Stroke`**: Similar to 'hypertension', there is a strong correlation of 'heart_disease' and Stroke.
5. **Explored `ever_married` and relationship with `Stroke`**: We found that there was a strong correlation between 'ever_married' and Stroke.
6. **Explored `average_glucose_level` and relationship with `Stroke`**: This is a numerical variable of the average blood glucose level. We found that there were a lot of outliers with high glucose level but did not suffer from Stroke. We found that there was correlation between blood glucose level and Stroke.
7. **Explored `bmi` and relationship with `Stroke`**: 'bmi' is a numerical variable that increases with a persons weight. There were a lot of outliers with high bmi present. We found that there is little correlation between 'bmi' and Stroke.
8. **Explored `smoking_status` and relationship with `Stroke`**: We found that there was correlation between smoking and Stroke.
9. **Explored correlation using Pearson Correlation Coefficient and Chi-square test**: we found the extent to which our features are correlated and associated to `Stroke`. We had to do two separate tests because the variables were of different data types.

For visualisation and further analysis, please refer to the Jupyter Notebook on EDA.

### 4. [Decision Tree Classifier](https://github.com/radioblodo/SC1015/blob/main/Decision_Tree_Classifier.ipynb) 
We decided to use what we have learned from SC1015 and used Decision Tree Classifier to help us classify whether a particular group of people is more prone to getting stroke and from there, determine which factor is the most significant contributor. Then we also used this to predict `Stroke`.

We split our dataset of 40,849 points into `80:20` train-test datasets with `random_state = 42` to ensure replicability of results. 
We tested the trained model on the test dataset and the accuracy of predicting `Stroke` is `66%`.

Then we optimised the model by performing `GridSearchCV` to determine the optimum depth for the model. After re-running the optimised model, the accuracy was improved to `84.6%`

### 5. [Logistic Regression](https://github.com/radioblodo/SC1015/blob/main/Logistic_Regression_Model.ipynb)
We used `Logistic Regression` because:
1. It can model the relationship between the categorical dependent variable `Stroke` and one or more independent variables, which can be categorical or numerical. This is useful for us due to the characteristics of our dataset and let us predict the probability of `Stroke` based on the independent variables, which is our goal.
2. Works with small sample sizes: This model is useful for datasets <100k. 
3. We can manipulate the threshold on the predicted probability of the dependent variable. Which will affect the accuracy of the model as it changes the limit when we classify people to have Stroke.

We used the same training and test data sets and the resultant accuracy in predicting `Stroke` is 68.36%.

Then we optimised the model by adding hyperparameters using `GridSearchCV`. We also added smoothing parameters to reduce the risk of overfitting. The optimised Model's accuracy improved only by a small margin to 68.397%.

### 6. [K Nearest Neighbour (KNN)](https://github.com/radioblodo/SC1015/blob/main/K-Nearest_Neighbour.ipynb)
We used `KNN` because:
1. It is useful for classification problems like predicting categorical variables such as stroke, based on a mix of numerical and categorical predictor variables.
2. It is a non-parametric method - means that it does not make any assumptions for data distribution and the model structure is determined by our dataset. which is helpful in our case to model real-world datasets that do not follow mathematical assumptions.

Using the same training and test datasets, we got an accuracy of 81%.

Then we optimised the model by changing the parameter k, which affects how many nearest points to check and use the classification of those to form a prediciton. we plotted the error-rate and k-value chart to see which k value will result in the lowest error rate. We chose k=2 and the improved accuracy was 89%, the highest among the models.

### 7. [Gaussian Naïve Bayes](https://github.com/radioblodo/SC1015/blob/main/Gaussian_Naive_Bayes.ipynb)
We used `Gaussian Naïve Bayes` because:
1.  It is probabilistic machine learning algorithm that can be used in classification tasks.
2.  Naive - assumes that the features of the model are independent of each other. This makes the model more flexible and less complex, making it less prone to overfitting.
3.  Does not require huge training data

We used the same training and test data sets and the resultant accuracy in predicting `Stroke` is 66%.
Then we used `GridSearcCV` to make adjustments to the hyperparameters and improved the model's accuracy to 67%.

### 8. Conclusion
From our project, we cleaned our dataset and performed exploratory analysis. Then, we implemented 4 different machine learning models and evaluated their accuracy in predicting `Stroke`. Out of the 4 models, we found out that `K Nearest Neighbour` was the most accurate at 86%.

Beyond this project, we could possibly further improve our model into predicting the level of an individual's risk of Stroke. Then, we can implement this prediction model in a preliminary Stroke Risk Assessment, a convenient way for the public to input their information in return for a reliable gauge of risk for Stroke. Then, we can advise them steps to mitigate their risk or to seek professional medical diagnosis. This would raise awareness of Stroke and aid in early prevention of Strokein Singapore.

### 9. References
1. https://www.kaggle.com/datasets/prosperchuks/health-dataset
2. https://www.world-stroke.org/news-and-blog/news/sso-spotlight-singapore
3. https://www.kdnuggets.com/2020/01/decision-tree-algorithm-explained.html
4. https://www.projectpro.io/recipes/optimize-hyper-parameters-of-decisiontree-model-using-grid-search-in-python
5. https://statisticsbyjim.com/regression/choosing-regression-analysis/
6. https://towardsdatascience.com/tuning-the-hyperparameters-of-your-machine-learning-model-using-gridsearchcv-7fc2bb76ff27
7. https://medium.com/analytics-vidhya/k-nearest-neighbors-algorithm-7952234c69a4 
8. https://towardsdatascience.com/how-to-find-the-optimal-value-of-k-in-knn-35d936e554eb
9. https://www.ibm.com/topics/knn 
10. https://www.upgrad.com/blog/gaussian-naive-bayes/?msclkid=658123f7d04811ec8608a267e841a654 
11. https://www.analyticsvidhya.com/blog/2021/01/gaussian-naive-bayes-with-hyperpameter-tuning/
12. https://www.kaggle.com/getting-started/225022
13. https://www.sciencedirect.com/topics/mathematics/naive-bayes
14. https://link.springer.com/article/10.1007/s10100-021-00782-1
