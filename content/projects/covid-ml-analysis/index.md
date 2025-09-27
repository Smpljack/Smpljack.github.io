---
title: "Exploratory Data Analysis of COVID-19 Pandemic Data for Machine Learning"
summary: "A comprehensive machine learning analysis I conducted for an IBM course in 2021, exploring COVID-19 pandemic data to identify key predictors and relationships between variables using statistical methods and scikit-learn."
authors:
  - admin
tags:
  - Machine Learning
  - Data Analysis
  - COVID-19
  - Statistical Analysis
  - Scikit-learn
  - IBM Course
date: "2021-12-15T00:00:00Z"
publishDate: "2021-12-15T00:00:00Z"

# Optional external URL for project
external_link: ""

# Featured image
image:
  caption: "COVID-19 pandemic parameters analysis showing relationships between cases, deaths, ICU patients, testing, and vaccination rates"
  focal_point: "center"
  preview_only: false

# Slides (optional)
slides: ""
---

## Project Overview

This project was conducted in December 2021 as part of an IBM machine learning course, during a period when extensive COVID-19 pandemic data was widely available. The analysis focused on the United States dataset due to its superior data completeness compared to other countries, particularly regarding testing metrics and vaccination coverage.

## Scope and Objectives

The primary goal was to conduct an exploratory data analysis (EDA) on daily COVID-19 statistics to identify a robust subset of variables that could serve as effective features for predicting the number of new cases. The analysis involved comprehensive data exploration, quality assessment, statistical analysis, feature evaluation, data cleaning, and feature engineering.

## Key Findings and Main Conclusions

### 1. **Vaccination Impact on Pandemic Dynamics**
- **Strong Negative Correlation**: As vaccination rates increased, new COVID-19 cases showed a clear decrease, demonstrating the effectiveness of vaccination campaigns.
- **Statistical Significance**: When analyzing populations with high vaccination rates (≥40% fully vaccinated), positive test rates consistently remained below the 0.03 threshold, resulting in a p-value of 1.0.
- **Temporal Evolution**: The positive rate (ratio of new cases to new tests) exhibited distinct temporal patterns, peaking early in the pandemic and declining as vaccination efforts scaled up.

### 2. **Testing and Case Relationships**
- **Positive Correlation**: A clear relationship was observed between increased testing and higher case detection, highlighting the importance of testing infrastructure.
- **Weekly Patterns**: Daily data showed significant weekly fluctuations due to data gathering methodologies, which were addressed through weekly averaging techniques.

### 3. **ICU and Mortality Patterns**
- **Delayed Response**: Deaths and ICU patient rates showed strong correlation with new cases but exhibited a slight temporal delay, reflecting the progression of severe disease.
- **Healthcare Burden**: ICU patient rates closely tracked case numbers, providing insights into healthcare system stress.

## Methods and Technical Approach

### **Data Processing and Feature Engineering**
1. **Variable Selection**: From 59 initial variables, the analysis focused on 8 key metrics:
   - New cases per million
   - New deaths per million  
   - ICU patients per million
   - New tests per thousand
   - Reproduction rate
   - Positive rate
   - People vaccinated per hundred
   - People fully vaccinated per hundred

2. **Data Preprocessing**:
   - **Outlier Removal**: Filtered extreme values in reproduction rate (>1.1)
   - **Log Transformation**: Applied log1p-transformation to variables with |skewness| > 0.75 to normalize distributions
   - **Weekly Averaging**: Applied to smooth daily fluctuations and reveal underlying trends

3. **Hypothesis Testing**
   - **Null Hypothesis**: Full vaccination does not reduce positive test rates
   - **Alternative Hypothesis**: Full vaccination significantly reduces positive test rates
   - **Significance Level**: α = 0.05

### **Tools and Technologies**
- **Python**: Primary programming language
- **Scikit-learn**: Machine learning framework for data processing and model development
- **Statistical Libraries**: For hypothesis testing and distribution analysis
- **Visualization**: Seaborn and Matplotlib for comprehensive data visualization

## Impact and Significance

This analysis provided insights into the complex relationships between COVID-19 variables during the pandemic's peak. The findings demonstrated the critical role of vaccination in reducing disease transmission and highlighted the importance of comprehensive testing strategies.

The project successfully identified key predictors for COVID-19 case trajectories and established a foundation for developing predictive models using linear regression techniques, demonstrating the practical application of machine learning methods to real-world public health challenges.
