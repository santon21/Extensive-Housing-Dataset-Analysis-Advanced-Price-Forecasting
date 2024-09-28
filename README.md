# Housing Market Forecasting Project

## Overview
This project aims to develop predictive models to forecast housing prices using the Ames Housing dataset. It covers various stages, including data preprocessing, exploratory data analysis, feature engineering, and model development. The primary objective is to accurately predict housing prices, assisting stakeholders in making informed decisions regarding property investments and sales.

## Table of Contents
- [Project Structure](#project-structure)
- [Problem Statement](#problem-statement)
- [Objectives](#objectives)
- [Dataset](#dataset)
- [Data Preprocessing](#data-preprocessing)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Feature Engineering](#feature-engineering)
- [Model Development](#model-development)
- [Results](#results)
- [Future Improvements](#future-improvements)
- [Business Value](#business-value)

## Project Structure
The project consists of the following files:
- `CS441_Final_project-2.ipynb`: Main notebook for data loading, preprocessing, feature engineering, model development, and evaluation.
- `train.csv`: Training dataset containing house features and target sale prices.
- `test.csv`: Test dataset for model evaluation and predictions.
- `Submission.csv`: Submission file containing predicted sale prices for the test set.
- `Submission-0.14-RandomForest.csv`: Alternative submission file with predictions from a Random Forest model.
- `README.md`: Project documentation.

## Problem Statement
The goal of this project is to predict the sale prices of houses using various features related to property characteristics, location, and market conditions. The project addresses the following questions:
- **What are the key factors affecting house prices?**
- **How accurately can we predict house prices based on the available data?**

### Objectives
- Develop models to predict house prices using a variety of regression techniques.
- Identify and analyze the features that significantly impact housing prices.
- Improve prediction accuracy through feature selection and engineering.

## Dataset
The dataset includes:
- **House Characteristics**: Information about the physical attributes of the houses (e.g., size, type, year built).
- **Location Details**: Data related to the location and neighborhood of the houses.
- **Market Data**: Historical sales prices and other relevant market indicators.

### Key Features
- `MSSubClass`: Type of dwelling involved in the sale.
- `MSZoning`: General zoning classification.
- `LotArea`: Lot size in square feet.
- `OverallQual`: Overall material and finish quality of the house.
- `YearBuilt`: Original construction date.
- `SalePrice`: The target variable representing the sale price of the property.

## Data Preprocessing
- **Handling Missing Values**: Missing values were handled using median or mode imputation and removing columns with high missing ratios (e.g., `Alley`, `PoolQC`).
- **Feature Scaling**: Standard scaling was applied to numerical features to normalize data ranges.
- **Encoding Categorical Features**: Label encoding was used for categorical variables.
- **Transformation for Skewness**: Applied log transformation on skewed numerical features and on `SalePrice` to address skewness.

## Exploratory Data Analysis
- Explored relationships between features and the target variable.
- Visualized distributions of various features and identified potential outliers.
- Analyzed correlations to identify features highly predictive of house prices, such as:
  - `OverallQual` and `SalePrice`: 0.79
  - `GrLivArea` and `SalePrice`: 0.71
  - `GarageCars` and `SalePrice`: 0.64

## Feature Engineering
- Created new features by combining existing attributes (e.g., `TotalSF` combining `TotalBsmtSF`, `1stFlrSF`, and `2ndFlrSF`).
- Performed feature selection using Recursive Feature Elimination (RFE) and importance scores from tree-based models.
- Developed composite features like `Total_Bathrooms` and `YrBltAndRemod`.

## Model Development
### Baseline Models
- **Model**: Linear Regression
- **Performance**: Used as a baseline to compare against more complex models.

### Advanced Models
- **Implemented and Compared Performance of Multiple Models Including:**
  - **Random Forest Regressor**
  - **Gradient Boosting Regressor**
  - **Support Vector Regressor**
  - **ElasticNet**
- **PCA Analysis**: Principal Component Analysis (PCA) was applied on both scaled and unscaled data to reduce dimensionality and improve model performance.

### Hyperparameter Tuning
- Conducted hyperparameter tuning using Grid Search and Cross-Validation, particularly for the Gradient Boosting Regressor.

### Best Model
- **Gradient Boosting Regressor** with optimized hyperparameters:
  - `learning_rate`: 0.01
  - `n_estimators`: 1000
  - `max_depth`: 3
  - `min_samples_split`: 10
- **Performance**: Achieved the lowest mean squared error on validation data.

## Results
- The best-performing model was the Gradient Boosting Regressor with tuned hyperparameters, achieving the lowest mean squared error.
- Important features identified included overall quality, total square footage, and year built.
- Model selection and dimensionality reduction were utilized to enhance prediction accuracy.

## Future Improvements
- Explore deep learning models like neural networks to capture complex patterns.
- Incorporate additional data sources, such as economic indicators or more detailed location data, for better predictions.
- Experiment with advanced feature engineering techniques, including feature interactions.

## Business Value
- **Improved Investment Decisions**: Accurate price predictions assist investors in making informed decisions on property purchases and sales.
- **Market Insights**: Insights into house price drivers help guide developers and policymakers in strategic planning.
- **Enhanced Customer Satisfaction**: Real estate agencies can provide more reliable advice to clients, enhancing trust and service quality.
