# Flipkart Customer Service Satisfaction Analysis

## Overview

This project analyzes Flipkart's customer support data to understand what drives customer satisfaction and builds machine learning models to predict satisfaction levels (CSAT Score). The workflow covers data exploration, cleaning, feature engineering, visualization, hypothesis testing, model building, and evaluation.

---

## Project Steps

### 1. Problem Statement

- **Goal:** Predict customer satisfaction (CSAT Score: 1-5) based on support interaction details.
- **Business Value:** Early identification of dissatisfied customers, improved agent training, and better resource allocation.

---

### 2. Data Understanding

- **Source:** [data/Customer_support_data.csv](data/Customer_support_data.csv)
- **Key Features:**
  - Product category, response time, item price, resolution status, agent shift, CSAT score, etc.
- **Initial Exploration:** Checked data shape, column types, duplicates, and missing values.

---

### 3. Data Wrangling & Preprocessing

- **Datetime Conversion:** Converted date/time columns to datetime objects for calculations.
- **Missing Values:**
  - Filled categorical columns with mode or 'Unknown'.
  - Filled numerical columns with median.
- **Dropped Columns:** Removed high-cardinality or identifier columns (e.g., Unique id, Agent_name).
- **Feature Engineering:**
  - Calculated response time in seconds.
  - Calculated survey delay in days.
- **Categorical Encoding:** Converted object columns to category dtype for memory efficiency.

---

### 4. Data Visualization & Insights

- **Univariate Analysis:** Distribution plots for CSAT Score, channel, category, price, handling time, and agent shift.
- **Bivariate/Multivariate Analysis:**
  - Bar plots and scatter plots to explore relationships (e.g., CSAT by channel/category, handling time vs. CSAT).
  - Correlation heatmap and pair plots for numerical features.
- **Business Insights:** Identified key drivers of satisfaction and potential operational improvements.

---

### 5. Hypothesis Testing

- **ANOVA:** Tested if CSAT differs by support channel.
- **Pearson Correlation:** Checked relationship between handling time and CSAT.
- **Chi-Square:** Tested dependency between issue category and product category.

---

### 6. Feature Engineering & Selection

- **Outlier Detection:** Used Z-score and IQR methods for numerical features.
- **Label Encoding:** Converted categorical variables to numeric codes.
- **Feature Binning:** Created buckets for response time and price.
- **Feature Selection:** Used L1-regularized Logistic Regression to select important features.

---

### 7. Model Building & Evaluation

- **Models Used:**
  - Logistic Regression
  - Decision Tree Classifier
  - Random Forest Classifier
- **Data Split:** 80% training, 20% testing.
- **Scaling:** StandardScaler for numeric features.
- **Imbalanced Data Handling:** Used `class_weight='balanced'` in models.
- **Evaluation Metrics:** Accuracy, Precision, Recall, F1-Score (with focus on low CSAT scores for business impact).
- **Best Model:** Random Forest (highest accuracy and balanced performance across all CSAT levels).

---

### 8. Model Explainability

- **Feature Importance:** Random Forest's built-in feature importance used to identify key drivers of satisfaction.

---

### 9. Future Work

- Explore advanced NLP on customer remarks.
- Deploy model using MLOps best practices.

---

## How to Run

1. Clone the repository.
2. Place the dataset in the `data/` folder.
3. Open and run the notebook: [Flipkart_Customer_Service_Satisfaction_Analysis.ipynb](Flipkart_Customer_Service_Satisfaction_Analysis.ipynb)
4. Follow the notebook cells for step-by-step analysis and results.

---

## File Structure

- `Flipkart_Customer_Service_Satisfaction_Analysis.ipynb` — Main analysis notebook.
- `data/Customer_support_data.csv` — Dataset file.

---

## Key Takeaways

- **Fast response times, issue type, and product category** are the most important factors for customer satisfaction.
- **Random Forest** provides the most reliable predictions for CSAT.
- The workflow is modular and can be adapted for similar customer service datasets.
