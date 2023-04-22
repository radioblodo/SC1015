# SC1015: DSAI Mini Project - Predicting Stroke using various factors

School of Computer Science and Engineering \ 
Nanyang Technological University \
Lab: B134 \
Team 1 

Members 
  1. Chai Zi Liang ([@radioblodo](https://github.com/radioblodo))
  2. Ian Boo Jing Yong ([@sirwoofles](https://github.com/sirwoofles))
  3. Ng Yin Ming ([@badbananaa](https://github.com/badbananaa))
 
---
### Description
This repository contains all the Jupyter Notebooks, datasets, images, video presentations, and the source materials/references we have used and created as part of the Mini Project for SC1015: Introduction to Data Science and AI.

This README briefly highlights what we have accomplished in this project. If you want a more detailed explanation of things, please refer to the the Jupyter Notebooks in this repository. They contain more in-depth descriptions and smaller details which are not mentioned here in the README. For convenience, we have divided the notebooks into 5 parts which broadly relate to the 5 main sections of this project

---
### Table of Contents:
1. [Problem Definition](#1-Problem-Definition)
2. [Data Preparation and Cleaning](#2-Data-Preparation-and-Cleaning)
3. [Exploratory Data Analysis](#3-Exploratory-Data-Analysis)
4. [Linear Regression Model](#4-Linear-Regression-Model)
5. [Logistic Regression](#5-Logistic-Regression)
6. [K Nearest Neighbour (KNN)](#6-K-Nearest-Neighbour-(KNN))
7. [Naïve Bayes](#7-Naïve-Bayes)
8. [Conclusion](#8-Conclusion)
9. [References](#9-References)
---
### 1. Problem Definition 
Can we predict the probability of getting stroke and thus take measures to prevent it? If so, which model would be the most helpful in predicting?

**Our Dataset:** ['Diabetes, Hypertension and Stroke Prediction' from Kaggle](https://www.kaggle.com/datasets/prosperchuks/health-dataset) \
**Our Problem:** How can we predict the probability of getting stroke? And can we take measures to prevent it? If so, which model would be the most helpful in predicting?

**Practical Motivation:** We believe that this dataset as well as the problem we pose is relavant to the Singapore context. This is because Stroke is currently Singapore's 4th leading cause of death, comprising of 6.8% of all deaths in Singapore(World Stroke Organization, n.d.). By learning the various reasons contributing to Stroke, we might be able to predict an individual's risk for Stroke. And we can also recommend actions to reduce the individual's risk to Stroke by targeting the corresponding factors contributing to his risk for Stroke.

### 2. Data Preparation and Cleaning 
Within this section, we have prepped and cleaned the dataset to facilitate improved analysis of the data and enable the utilization of the data for machine learning models in subsequent sections.

Steps we took for this section:
1. **Preliminary Feature Selection:** Out of '10' Variables, we drop variables 'work_type' and 'Residence_type' that we think are not relevant or feasible for exploration. 
2. **Change Variable Types:** In the original dataset, the data types of categorical variables were labelled as 'int64' or 'float64'. So we changed their data types to 'category'
3. **Dropping 'NaN's:** All the 'NaN' values in our dataset were dropped.
4. **Removing of age<0:** All the rows with values <0 for 'age' were removed.

### 3. Exploratory Data Analysis
Afterwards, we conducted Exploratory Data Analysis on our DataFrame, which involved generating different graphs to visualize potential patterns within the variables. Subsequently, we established the correlation between the variables and Stroke, and deduced some inferences to address our problem at this stage.

We did the following:
1. **Explored `Sex` and relationship with `Stroke`**: This is a categorical variable of 2 categories 'Male' and 'Female'. We found that Females were more likely to suffer from Stroke.
2. **Explored `age` and relationship with `Stroke`**: This is a numerical variable for age of the people in the dataset. We learnt that the median age of those suffering from Stroke is greater.
3. **Explored `hypertension` and relationship with `Stroke`**: This is a categorical variable of those with and without hypertension. There is a strong correlation of hypertension and Stroke.
4. **Explored `heart_disease` and relationship with `Stroke`**: Similar to 'hypertension', There is a strong correlation of 'heart_disease' and Stroke.
5. **Explored `ever_married` and relationship with `Stroke`**: We found that there was a strong correlation between 'ever_married' and Stroke.
6. **Explored `average_glucose_level` and relationship with `Stroke`**: This is a numerical variable of the average blood glucose level. We found that there were a lot of outliers with high glucose level but did not suffer from Stroke. We found that there was correlation between blood glucose level and Stroke.
7. **Explored `bmi` and relationship with `Stroke`**: 'bmi' is a numerical variable that increases with a persons weight. There were a lot of outliers with high bmi present. We found that there is little correlation between 'bmi' and Stroke.
8. **Explored `smoking_status` and relationship with `Stroke`**: We found that there was correlation between smoking and Stroke.

For visualisation and further analysis, please refer to the Jupyter Notebook on EDA.

### 4. Decision Tree Classifier 
We decided to use what we have learned from SC1015 and used Decision Tree Classifier to help us classify whether a particular group of people is more prone to getting stroke and from there, determine which factor is the most significant contributor. 


### 5. Logistic Regression


### 6. K Nearest Neighbour (KNN)


### 7. Naïve Bayes

### 8. Conclusion

### 9. References
