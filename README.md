## Overview

This portfolio project uses the publicly available OKCupid Profiles data in order to build supervised machine learning models to predict users' orientation from structured profiles (information like age, sex, income, education, diet etc.) and free-text essay submissions.

The raw data used is not included within this repository due to file size limits. I acquired it from Kaggle.

## Methodology

### 1. Exploratory Data Analysis

I begin with exploratory data analysis to:

* Investigate dataset, what columns are included, missing data, cardinality etc.
* Assess class imbalance
* Look for any potential predictive signals
* Inform preprocessing and modelling decisions

### 2. Baseline: Multinomial Logistic Regression

I implement a multinomial logistic regression (MLR) model to act as a baseline comparison for the neural network. Initially, this only uses the structured profile features. The model is evaluated using class-wise precision and recall, with macro-averaged F1 score as the primary metric to optimise for due to class imbalance. Performance was unimpressive, so steps were taken to develop the model in order to enhance predictive ability.

Model development includes:

* Train/validation/test splitting with stratification  
* Regularization tuning (L1, L2, Elastic Net)  
* Hyperparameter optimization for regularization strength  
* Class imbalance handling via class weighting  
* Threshold optimization beyond default argmax decision rules  
* Feature engineering, including interaction terms  

Despite systematic optimization, performance gains were modest, suggesting limited predictive signal in structured variables alone.


This project will be concluded with a neural network to (hopefully!) produce more accurate predictions.


