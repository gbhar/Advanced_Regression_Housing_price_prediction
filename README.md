# Housing Price Prediction
> Assignment contains the code and resources for the "Housing Price Prediction" project submitted to UpGrad on ML 2 module on Advanced Regression. 

## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
The "Housing Price Prediction" project is a machine learning project developed as part of UpGrade's educational program.the Assignment should into two Parts.Part-I is a programming assignment (to be submitted in a Jupyter Notebook), and Part-II includes subjective questions (to be submitted in a PDF file).
- Background
  A US-based housing company named Surprise Housing has decided to enter the Australian market. The company uses data analytics to purchase houses at a price below their actual values and flip them on at a higher price. For the same purpose, the company has collected a data set from the sale of houses in Australia.
- Business Problem
  You are required to model the price of houses with the available independent variables. This model will then be used by the management to understand how exactly the prices vary with the variables. They can accordingly manipulate the strategy of the firm and concentrate on areas that will yield high returns. Further, the model will be a good way for management to understand the pricing dynamics of a new market.
- Dataset
The project uses a dataset that includes various attributes and features of houses, such as the number of bedrooms, square footage, location, and more. This dataset is crucial for training and evaluating the machine learning model, as it provides the necessary information to make accurate price predictions.
The specifics of the dataset, including its source, size, and attributes, are detailed in the data directory of this repository. You can explore the dataset and its details by referring to the project's Jupyter notebooks in the notebooks directory.
Accurate and data-driven housing price predictions can empower individuals and professionals in the real estate market to make well-informed decisions. The "Housing Price Prediction" project aims to contribute to solving this business problem by leveraging machine learning techniques and a comprehensive dataset.


## Conclusions
- Conclusion 1 from the Analyzing Numerical Data
  * Majority of numerical data have outliers
  * Dropping the all Outliers will causes loss information
  *  hence ressigining fixed minimum values to these rows where feature value is outside the range of [25th Percentilie - 1.5 IOR, 75th percentilie + 1.5 IQR]
  *  IQR or Iner Quartie Range = Difference between 75th percentilie and 25th percentilie values of features.
  *  Target column 'SalePrice' is excluded in this.
- Conclusion 2 from the Analyzing Categorical Features
  * For 'Alley' Nan Means 'No access to alley.
  * For 'BsmtQual','BsmtCond','BsmtExposure','BsmtFinType1','BsmtFinType2' Nan_means "No Bassement"
  * For GarageType, GarageFinish, GarageQual, GarageCond Nan means "No Garage"
  * Fpr FriplaceQu and Fence Nan means 'No Fire' Place and 'No Fence'
  * MiscFeature - Nan means no additional features mentioned.
- Conclusion 3 from the Analyzing Orderred Features
  * LotShape : Slightly irregular LotShape have the highest SalePrice
  * Utilities : Most of the house in the dataset have all the public utilities
  * LandSlope : House at severse land slope have lowest SalePrice
  * HouseStyle : 2 storied houses have the highest SalePrice
  * ExterQual : House with Excellent qualtity of material on the exterior have the highest SalePrice
  * ExterCond : House with Excellent condition of material on the exterior have the highest SalePrice
  * House having excellent heating quality and Kitchen quality have highest SalePrice
  * House With Typical funcationally have highest SalePrice. There are very few house that are severely damaged
  * SalePirce range in Largest for house with average firplace quality
  * SalePrice is highest of Garage is Finished
  * The Range of SalePrice is widest for Typical/Average Garage qualtiy and Condition.
  * there are very few house with excellent condition of garage
  * House with Excellwnt Quality bassement have highest SalePrice
  * House with good living quarters (BsmtFinshType1=GLQ) have highest SalePrice
  * A lost of house have unfinished basement or no bassement (label = Not_applicable)
- Conclusion 4 from the analysis Model Evaluation
  * Ridge and Lasso Regression Model are built with optimum alpha calculated in GridSearchCV method. Optimum alpha = 9.0 for ridge and 0.0001 for lasso model.
  * Model evaluation is done with R2 score and Root Mean Square Error.
  * Lasso Regression is chosen as final model for having slightly better R-square value on test data.
  * Out of 50 features in the final model, top 10 features in order of descending importance are ['1stFlrSF', '2ndFlrSF', 'OverallQual', 'OverallCond', 'SaleCondition_Partial', 'LotArea', 'BsmtFinSF1','SaleCondition_Normal', 'MSZoning_RL', 'Neighborhood_Somerst']
  * Model coefficients are listed in a table along with the corresponding features , for example natural log of SalePrice will change by 0.124911 with unit change in the feature '1stFlrSF' when all
  * the features remain constant. Negative sign in the coefficient signifies negative correlation between the predictor and target variable.
  * Predicted value of SalePrice is tranformed into its original scale by performing antilog.
    
## Technologies Used
- library - version 1.0
  * import numpy as np
  * import pandas as pd
  * import matplotlib.pyplot as plt
  * import seaborn as sns
- library - version 2.0
  * from sklearn.model_selection import train_test_split
  * from sklearn.impute import SimpleImputer
  * from sklearn.preprocessing import StandardScaler
  * from sklearn.linear_model import LinearRegression, Ridge, Lasso
  * from sklearn.model_selection import GridSearchCV
  * from sklearn.feature_selection import RFE
  * import statsmodels.api as sm
- library - version 3.0
  * from sklearn.metrics import mean_squared_error, r2_score


## Acknowledgements
Give credit here.
- This project was inspired by the need for accurate housing price predictions in the dynamic real estate market, where homebuyers and sellers often lack data-driven tools to make informed decisions.
- While developing this project, we consulted various books, online articles, and research papers related to real estate data analysis, machine learning, and regression techniques. These references provided valuable insights and guidance.


## Contact
Created by [[@githubusername](https://github.com/gbhar)] - feel free to contact me!

