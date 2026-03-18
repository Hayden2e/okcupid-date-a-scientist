## Overview

This portfolio project uses publicly available OKCupid Profiles data in order to build supervised machine learning models. The selected goal is to predict users' orientation from their structured profile data (information like age, sex, income, education, diet etc.) and free-text essay submissions.

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

Despite systematic optimization, performance gains were modest, suggesting limited predictive signal in the users' structured data. Users' profile data (unstructured essays) were incorporated in the form of features derived using TF-IDF, to attempt further improvement in the MLR model. This resulted in an increase of macro F1 score from 0.50 to 0.57.

This project will be concluded with a neural network to produce more accurate predictions.


