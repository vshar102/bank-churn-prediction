# Bank Customer Churn Analysis & Segmentation
End-to-End Business Analytics & Machine Learning Project

# Situation
Customer acquisition in retail banking is expensive, making retention critical to profitability.
However, real-world bank data is often messy, imbalanced, and mixed-type, containing both numerical (Balance, Age) and categorical (Geography, Gender) features.
The bank needed to know:
Which customers are likely to churn
Why they churn
How to segment customers for targeted retention strategies

# Task
Build a dual analytics system that:
Predicts customer churn with high recall (catch churners early)
Segments customers into meaningful personas to guide marketing and retention decisions
The solution had to be interpretable, business-ready, and suitable for real decision-making, not just model accuracy.

# Action (Technical & Analytical Approach)
🔹 Data Preparation & Quality:
Cleaned and standardized raw bank data (10,000 customers, 13+ features)
Resolved inconsistent categorical values (e.g., Geography labels)
Removed identifiers and handled missing values
Applied One-Hot Encoding for categorical variables
Standardized numerical features (Age, Balance, Salary) to prevent scale bias

🔹 Handling Class Imbalance:
Churn represented only ~20% of customers
Applied SMOTE (Synthetic Minority Over-sampling Technique) to ensure the model learned churn behavior instead of defaulting to “non-churn”
Focused on recall over raw accuracy, aligning with real retention goals

🔹 Churn Prediction (Supervised Learning):
Trained an XGBoost classifier, chosen for:
Strong performance on tabular data
Built-in handling of feature interactions
Clear feature importance for interpretability
Identified key churn drivers such as:
Age
Number of Products
Balance-related features

🔹 Customer Segmentation (Unsupervised Learning):
Performed K-Means clustering on standardized behavioral and financial features
Determined optimal number of clusters using the Elbow Method
Identified distinct customer personas, including:
Young / low-balance / low engagement customers
Older / high-balance / churn-prone customers
Enabled cluster-level churn analysis to connect behavior with risk

# Result
Delivered a high-recall churn prediction model capable of identifying at-risk customers early
Transformed raw predictions into actionable business insights using clustering
Enabled targeted strategies such as:
Product bundling for low-engagement clusters
Loyalty incentives for high-value, churn-prone segments
Shifted the project from a “black-box ML model” to a business strategy enabler

# 📊 Dataset
Source: Simulated European bank customer data
Size: ~10,000 records
Key Features:
CustomerId, Geography, Gender, Age, Tenure, Balance, EstimatedSalary, NumOfProducts, Exited (Target)

# 🧠 Key Analytics Concepts Demonstrated
Business-driven churn modeling
Class imbalance handling with SMOTE
Model interpretability using XGBoost feature importance
Unsupervised customer segmentation with K-Means
Translating ML output into marketing & retention strategy

# 🛠️ Tools & Technologies
Python: Pandas, NumPy, Scikit-learn
Modeling: XGBoost, K-Means
Techniques: One-Hot Encoding, Feature Scaling, SMOTE
Visualization: Matplotlib, Seaborn
Environment: Jupyter Notebook

# 📈 Business Impact
✔ Identified high-risk churn customers before exit
✔ Discovered behavior-based customer personas
✔ Enabled data-driven retention and personalization strategies
✔ Demonstrated real-world ML readiness for banking analytics roles

