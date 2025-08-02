# Bank Customer Churn Analysis & Segmentation
# 🔍 Overview
End-to-end machine learning project on customer churn analysis using account-level data from a European bank. Involves data cleaning, feature engineering, churn prediction with logistic regression and random forest (AUC: 0.86), and customer segmentation using K-Means to support targeted retention strategies.

# 📊 Dataset
Source: Simulated data with 10,000 records and 13 fields
Key Features: CustomerId, Geography, Gender, Tenure, Balance, EstimatedSalary, NumOfProducts, Exited (target)

# 🧠 Objectives
# ✅ Objective 1: Data Import & QA
Imported Bank_Churn_Messy.xlsx and joined Account_Info to Customer_Info via CustomerID (left join)
Removed duplicates, standardized column types, and handled missing data (median for numeric, "MISSING" for categorical)

# ✅ Objective 2: Data Cleaning
Fixed currency and formatting issues
Merged inconsistent labels in Geography (e.g., "fr", "France", "FRANCE" → "France")
Profiled for outliers and nonsensical values, imputing where necessary

# ✅ Objective 3: Exploratory Data Analysis (EDA)
Plotted distributions (boxplots, histograms) to assess churn trends
Explored categorical variables vs. Exited (churn), notably:
Higher churn in Germany
Slightly higher churn in female customers
Feature-target relationships visualized with scatterplot matrices and bar charts

# ✅ Objective 4: Feature Engineering & Preparation
Engineered:
balance_to_income = Balance / EstimatedSalary (mean ≈ 3.88)
income_v_products = EstimatedSalary / NumOfProducts
Converted categorical variables into dummy variables
Removed identifiers (CustomerId, Surname)
Train-test split: 80% train, 20% test

# 🤖 Modeling & Evaluation
# 🔹 Logistic Regression:
Accuracy: 81.95%
Precision: 60.5%
Recall: 23.4%
F1 Score: 0.34
AUC: 0.766

# 🔹 Random Forest (Tuned with Cross-Validation):
Test Accuracy: 86.65%
AUC Score: 0.862
Most important features: Balance, NumOfProducts, balance_to_income

# 🔍 Clustering & Segmentation
# ✅ Objective 1: Feature Selection & Standardization
Removed ID fields and standardized numeric fields
Created a new feature: ProductsPerYear = NumOfProducts / Tenure

# ✅ Objective 2 & 3: K-Means Clustering (2 Rounds)
Used elbow method to choose k = 4
Performed clustering with and without geography-related features
Cluster 1 had the highest churn rate (~23%)
Heatmaps revealed customer behavior by cluster (e.g., high balance but low tenure segments)

# ✅ Objective 4: Insights & Recommendations
Combined clusters with churn and country data
Noted patterns:
High churn segments often had low product usage and high income
Germany-dominant clusters showed elevated churn
Proposed retention strategies like targeted product bundling and loyalty incentives

# 📈 Key Outcomes
Discovered high-risk customer segments using both supervised and unsupervised techniques
Created actionable features like balance_to_income to improve model performance
Delivered a high-performing Random Forest model (AUC: 0.86)

# 🛠️ Tools & Libraries
Python (Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn)
Jupyter Notebooks
Excel for initial data QA

