# Company Bankruptcy Prediction  
Machine Learning Project – Final Version

**Team**  
- Léa NAPASEUTH  
- Eric MOTHE  
- Pierre NIETO  
- Lou-Anne PEILLON  

---

## Project Overview

This project aims to predict whether a company is likely to go bankrupt based on a wide range of financial ratios.  
It follows a complete end-to-end machine learning workflow, from data exploration to model optimization and evaluation.

The objective is to classify companies as:

- **1 → Bankrupt**
- **0 → Not Bankrupt**

This task is particularly relevant for **banks, investors, auditors, and regulators**, as early bankruptcy detection helps reduce financial losses and improve risk management.

---

## Dataset Description

The dataset used comes from the *Company Bankruptcy Prediction* dataset (Kaggle).

**Key characteristics:**
- **6,819 companies**
- **96 numerical financial variables**
- **Target variable:** Bankruptcy (0/1)
- **Strong class imbalance:** ~3.2% bankrupt companies

**Types of indicators included:**
- Liquidity ratios  
- Profitability ratios  
- Leverage ratios  
- Operating and efficiency ratios  

**Data properties:**
- No missing values  
- All variables are numerical  
- High correlation between several financial ratios  
- Presence of outliers in some features  

---

## Data Exploration & Preprocessing

### Data exploration
- Histograms and boxplots
- Correlation heatmaps
- Quantile analysis
- PCA variance ratio analysis

### Preprocessing steps
- Median imputation
- Feature scaling using `StandardScaler`
- Outlier analysis (z-score based)
- Dimensionality reduction with PCA
- Stratified train/test split
- Careful handling of class imbalance using adapted metrics and class weights

---

## Machine Learning Models Implemented

### Baseline models
- Dummy Classifier  
- Logistic Regression (class_weight = balanced)

### Classical ML models
- Decision Tree  
- Random Forest  
- K-Nearest Neighbors  
- Support Vector Machine (Linear SVM)  
- Gradient Boosting Classifier  

### Advanced models
- XGBoost  
- LightGBM  
- Multilayer Perceptron (MLP)

### Ensemble methods
- Voting Classifier (soft voting)
- Stacking Classifier

---

## Model Selection & Hyperparameter Tuning

To improve model performance and generalization, hyperparameter optimization was performed using:

- **GridSearchCV** for exhaustive parameter tuning
- **RandomizedSearchCV** for efficient exploration of large parameter spaces

This step helped:
- Reduce overfitting
- Improve robustness
- Optimize recall and PR-AUC for the minority class (bankrupt companies)

---

## Evaluation Metrics

Due to the severe class imbalance, accuracy was not used as a primary metric.  
Models were evaluated using:

- ROC-AUC  
- PR-AUC (priority metric)
- Precision  
- Recall  
- F1-score  
- Confusion matrices  

---

## Results Summary

- Baseline models fail to detect bankrupt companies
- Logistic Regression (balanced) significantly improves recall
- Tree-based models outperform linear models
- Boosting models (LightGBM, XGBoost, Gradient Boosting) achieve the best overall performance
- **LightGBM** obtains the highest ROC-AUC (≈ 0.95)
- Ensemble methods stabilize performance across evaluation metrics

---

## Main Challenges

- Extreme class imbalance (97% vs 3%)
- Feature redundancy and strong correlations
- Risk of overfitting with complex models
- Trade-off between interpretability and performance

---

## Conclusion

This project shows that reliable bankruptcy prediction is achievable through rigorous preprocessing, appropriate evaluation metrics, and advanced ensemble learning methods. Boosting-based models combined with hyperparameter tuning provide the best results, making the final pipeline suitable for real-world financial risk screening and decision-support systems.
