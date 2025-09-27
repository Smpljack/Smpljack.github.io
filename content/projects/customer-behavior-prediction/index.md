---
title: "Predicting StoreToWebFraction: Customer Purchase Behavior Analysis"
summary: "A comprehensive machine learning project from an IBM course focusing on predicting customer purchase channel preferences (online vs. in-store) using Ridge regression with polynomial features and hyperparameter tuning."
authors:
  - admin
tags:
  - Machine Learning
  - Ridge Regression
  - Customer Analytics
  - Hyperparameter Tuning
  - Feature Engineering
  - IBM Course
  - Predictive Modeling
date: "2021-09-01T00:00:00Z"
publishDate: "2021-09-01T00:00:00Z"

# Optional external URL for project
external_link: ""

# Featured image
image:
  caption: "Customer dataset analysis showing relationships between demographics, spending habits, and purchase channel preferences"
  focal_point: "center"
  preview_only: false

# Slides (optional)
slides: ""
---

## Project Overview

This project was conducted as part of an IBM machine learning course, focusing on predicting customer purchase channel preferences through the development of a `StoreToWebFraction` metric. The analysis aimed to determine whether customers primarily purchase items online or in-store, with an emphasis on model interpretability over pure predictive power.

## Dataset and Methodology

### **Customer Dataset**
The analysis utilized a publicly available customer dataset from Kaggle containing 2,240 observations with comprehensive customer information:

- **Demographics**: Birth year, household income, family composition (kids/teens)
- **Spending Patterns**: Amounts spent on various product categories (wines, fruits, meat, fish, sweets, gold products)
- **Purchase Behavior**: Channel preferences (deals, web, catalog, in-store), web visits, recency
- **Marketing Response**: Campaign acceptance rates across multiple campaigns

### **Target Variable Engineering**
A new target variable `StoreToWebFraction` was created to represent the ratio of in-store to total purchases:
```
StoreToWebFraction = NumStorePurchases / (NumStorePurchases + NumWebPurchases)
```

## Key Findings

### **1. Feature Importance Analysis**
The Ridge regression model revealed significant insights about customer behavior predictors:

- **`NumWebVisitsMonth`**: The most impactful feature with a coefficient magnitude ~3x greater than other variables, showing strong negative correlation with in-store purchases
- **Product Categories**: `MntGoldProds`, `MntWines`, and `MntMeatProducts` showed strong negative correlations, indicating web-centric customers prefer these categories
- **Demographics**: Surprisingly, `Year_Birth` and `Income` had lower impact than expected on channel preference

### **2. Model Performance Optimization**
Through systematic hyperparameter tuning:

- **Polynomial Features Degree 2**: Achieved maximum R² = 0.4238 with α = 280.72, but resulted in 104 features with poor interpretability
- **Polynomial Features Degree 1**: Achieved R² = 0.30 with α = 80.22, providing better balance between performance and interpretability

### **3. Data Quality and Preprocessing**
- **Outlier Removal**: Identified and removed obvious outliers in `Income` and `MntMeatProducts`
- **Feature Engineering**: Applied log1p-transformation to variables with |skewness| > 0.75
- **Data Reduction**: Final dataset contained 2,211 observations after cleaning (29 dropped)

## Methods and Technical Approach

### **Data Preprocessing**
1. **Feature Engineering**: 
   - Log transformations for skewed variables
   - One-hot encoding for categorical features
   - Polynomial feature generation (degrees 1 and 2)

2. **Data Cleaning**:
   - Outlier identification and removal
   - NaN handling and data validation
   - Feature selection based on skewness thresholds

### **Model Development**
1. **Linear Regression Variants**:
   - Standard linear regression
   - Ridge regression with regularization
   - Polynomial feature integration

2. **Hyperparameter Optimization**:
   - Systematic α tuning across logarithmic scale (10⁰ to 10³)
   - Performance evaluation using R² score
   - Cross-validation for model selection

3. **Performance Assessment**:
   - Root Mean Squared Error (RMSE) analysis
   - Training vs. test set evaluation
   - Feature importance coefficient analysis

## Business Insights and Recommendations

### **Key Customer Segments Identified**
- **Web-Centric Customers**: High `NumWebVisitsMonth`, prefer wine/gold/meat products
- **Store-Centric Customers**: Lower web engagement, different product preferences
- **Channel-Agnostic Customers**: Balanced purchasing across channels

### **Strategic Recommendations**
1. **Data Collection Enhancement**: Focus on gathering `NumStoreVisitsMonth` data to mirror web visit insights
2. **Technology Adoption**: Consider `PC_Ownership` as a predictive feature for online purchasing behavior
3. **Product Strategy**: Leverage product category preferences for targeted channel recommendations
