# finaltest-of-dp-fe

Customer Data Preprocessing & Feature Engineering Project
📌 Project Overview

This project demonstrates a complete Data Preprocessing (DP) and Feature Engineering (FE) pipeline using Python and Scikit-Learn. The notebook covers data collection, integration, cleaning, missing value treatment, outlier handling, encoding, scaling, feature construction, transformation, and dataset export.

📂 Dataset Sources

The project combines customer-related information from multiple sources:

CSV File (customer.csv)
JSON File (customer.json)
SQLite Database
REST API Data

After loading the data, all datasets are merged into a single dataframe for analysis.

🛠 Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
Scikit-Learn
SQLite3
Requests
🚀 Project Workflow
1️⃣ Data Collection

Data is imported from multiple sources:

pd.read_csv()
pd.read_json()
sqlite3
requests
2️⃣ Data Integration

Datasets are merged using:

df = customers.merge(transactions,on="customer_id")
df = df.merge(products,on="product_id")
3️⃣ Exploratory Data Analysis (EDA)
Dataset Information
df.info()
Histogram Visualization
df.hist()
Boxplot Visualization
sns.boxplot()
4️⃣ Missing Value Handling
KNN Imputation
KNNImputer()
MICE Imputation
IterativeImputer()
Complete Case Analysis
df.dropna()
Missing Value Indicator
df["income_missing"]
5️⃣ Outlier Detection & Treatment
Z-Score Method
zscore()
IQR Method
Q1 = df["income"].quantile(0.25)
Q3 = df["income"].quantile(0.75)
Percentile Capping
quantile(0.01)
quantile(0.99)
6️⃣ Feature Construction
Date Conversion
pd.to_datetime()
Days Since Last Purchase
df["days_since_last_purchase"]
Customer ID Numeric Conversion
df["customer_num"]
7️⃣ Categorical Encoding
Label Encoding
LabelEncoder()

Applied on:

Gender
Ordinal Encoding
OrdinalEncoder()

Applied on:

Education
One Hot Encoding
pd.get_dummies()

Applied on:

Product Category
8️⃣ Numerical Feature Encoding
Quantile Binning
pd.qcut()

Created:

income_group
9️⃣ Feature Scaling
Standard Scaling
StandardScaler()
Min-Max Scaling
MinMaxScaler()
MaxAbs Scaling
MaxAbsScaler()
Robust Scaling
RobustScaler()
Normalization
Normalizer()
🔟 Feature Engineering
Purchase Per Day
purchase_amount /
(days_since_last_purchase + 1)

Generated:

purchase_per_day
1️⃣1️⃣ Function Transformations
Log Transformation
np.log1p()

Feature:

purchase_amount_log
Square Root Transformation
np.sqrt()

Feature:

price_sqrt
Reciprocal Transformation
1/(x+1)

Feature:

income_reciprocal
Power Transformation
PowerTransformer(method="yeo-johnson")

Feature:

income_power
1️⃣2️⃣ Binary Feature Creation
np.where()

Created:

frequent_buyer
1️⃣3️⃣ Export Processed Dataset
df.to_csv(
    "processed_customer_data.csv",
    index=False
)

Output:

processed_customer_data.csv
📊 Features Created
Feature Name	Description
income_missing	Missing value indicator
days_since_last_purchase	Days since latest purchase
customer_num	Numeric customer ID
income_group	Quantile-based income bins
purchase_per_day	Purchase efficiency metric
purchase_amount_log	Log transformed purchase amount
price_sqrt	Square root transformed price
income_reciprocal	Reciprocal transformed income
income_power	Yeo-Johnson transformed income
frequent_buyer	Binary purchase indicator
🎯 Learning Outcomes

After completing this project, you will understand:

Data Collection from Multiple Sources
Data Integration
Missing Value Treatment
Outlier Handling
Feature Construction
Feature Encoding
Feature Scaling
Feature Transformation
Binary Feature Creation
Exporting Clean Datasets
📁 Output
processed_customer_data.csv

A fully cleaned and feature-engineered dataset ready for:

Machine Learning
Data Analysis
Visualization
Predictive Modeling
⭐ Author

Manan Patel
Data Preprocessing & Feature Engineering Practice Project using Python and Scikit-Learn.
