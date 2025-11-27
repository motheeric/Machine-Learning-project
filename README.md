# Company Bankruptcy Prediction  
Machine Learning Project
Team : Léa NAPASEUTH, Eric MOTHE, Pierre NIETO, Lou-Anne PEILLON

This project aims to predict whether a company is likely to go bankrupt based on a wide range of financial ratios.  
It is part of a Machine Learning assignment focused on data analysis, modeling, and evaluation.

---

## Project Overview

The goal of the project is to use financial and accounting indicators to classify companies into:

- **1 → Bankrupt**
- **0 → Not Bankrupt**

The dataset used comes from the *Company Bankruptcy Prediction* dataset (Kaggle) and contains:

- **6,819 companies**
- **96 numerical financial variables**
- A highly **imbalanced target variable** (≈ 3% bankrupt companies)

---

## Dataset Description

The dataset includes several categories of financial indicators:

- **Liquidity ratios** (e.g., Current Ratio)
- **Profitability ratios** (e.g., ROA, Net Income to Total Assets)
- **Leverage ratios** (e.g., Debt Ratio, Liability to Equity)
- **Operating ratios** (e.g., Inventory Turnover)

Data characteristics:

-  No missing values  
-  All variables numerical  
- Severe imbalance → requires appropriate handling (class weights, metrics)

---

## Methods and Preprocessing

The project includes a full processing pipeline:

### Data preprocessing
- Standardization using `StandardScaler`
- Handling imbalance with metrics & class weights
- Outlier detection using z-scores
- Correlation analysis
- PCA for dimensionality reduction
- Train/test split with stratification

### Data exploration
- Histograms
- Boxplots
- Correlation heatmaps
- Quantile analysis
- PCA variance ratio plot

---

## Machine Learning Models Implemented

### **Baseline**
- Dummy Classifier  
- Logistic Regression (class_weight = balanced)

### **Classical ML models**
- Decision Tree  
- Random Forest  
- K-Nearest Neighbors  
- Linear SVM  
- Gradient Boosting Classifier  

### **Advanced models**
- **XGBoost**  
- **LightGBM**  
- **Multilayer Perceptron (MLP)**  

### **Ensemble methods**
- Voting Classifier (soft voting)  
- Stacking Classifier  

Each model is evaluated using:

- ROC-AUC  
- PR-AUC  
- Precision  
- Recall  
- F1-score  
- Confusion matrix  

---

## Results Summary

- Baseline model fails to detect bankrupt companies  
- Logistic Regression (balanced) significantly improves recall  
- Random Forest + Gradient Boosting provide strong performance  
- **XGBoost and LightGBM are the best-performing models overall**  
- Ensemble methods further stabilize performance across metrics  

---

## Main Challenges

- Extreme class imbalance (97% vs 3%)  
- Need for careful evaluation (PR-AUC over accuracy)  
- Avoiding overfitting with complex models  
- Choosing relevant features out of 95+ indicators  

---



