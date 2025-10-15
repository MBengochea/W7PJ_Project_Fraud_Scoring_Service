# Fraud Scoring Service

## Overview  
This project builds a reusable machine learning pipeline that detects fraudulent transactions from any structured CSV file. Whether the data comes from PayPal, Stripe, or internal logs, the system validates the input, engineers meaningful features, runs multiple models, and outputs fraud risk scores.

---

## What It Does  
- Accepts any transaction CSV file  
- Validates column structure, data types, and missing values  
- Cleans and transforms the data (encoding, scaling, feature creation)  
- Trains and compares four ML models:  
  - Logistic Regression  
  - Decision Tree  
  - Random Forest  
  - K-Nearest Neighbors (KNN)  
- Outputs fraud probability per transaction  
- Summarizes model performance using Accuracy, Precision, Recall, and F1

---

## How It Works  
1. **Input Validation**  
   - Checks schema, nulls, types, duplicates  
2. **Feature Engineering**  
   - Encodes categoricals, scales numerics, creates derived features  
3. **Model Training & Evaluation**  
   - Benchmarks four classifiers  
   - Compares metrics across models  
4. **Scoring & Output**  
   - Generates fraud scores  
   - Produces model comparison summary  
5. **Optional Deployment**  
   - Streamlit or Flask interface for CSV upload and scoring

---

## Deliverables  
- Modular Python pipeline  
- Fraud scores per transaction  
- Model comparison dashboard  
- Ready-to-integrate output for analysts or systems

---

## Why Machine Learning  
Fraud patterns evolve. Static rules fail. ML adapts. This project turns raw data into actionable insight—fast, scalable, and production-ready.

## Repo folder Tree
```
fraud_scoring_service/
├── data/
│   └── raw/
│        ├──synthetic_fraud_dataset.csv
├── notebooks/
│   ├── 01_topic_selection.ipynb
│   └── 02_data_preparation.ipynb
│   └── 03_model_training.ipynb
├── src/
│   ├── validate_input.py
│   ├── clean_data.py
│   ├── feature_engineering.py
│   └── model_evaluation.py
├── README.md
└── .gitignore
└── .config.yaml
└── pyproject.toml
└── uv.lock
```
## Kanban (done)

## To do (I)
- Dataset Acquisition & Profiling: load and config dataset from data/raw/
- Load into 01_topic_selection.ipynb and inspect: .shape, .dtypes, .isnull().sum(), .describe()
- Check for duplicates, outliers, skewed distributions
- Document findings: Which columns are usable, Which need cleaning or transformation
- Output: Data profile ready for Day 3 cleaning

- Create in src a function ===> validate_input.py: Check required columns: amount, timestamp, merchant, etc., Validate types: numeric, categorical, datetime, Flag missing values and duplicates.

- Create another function ===> clean_data.py: Drop or fill nulls (mean/mode), Convert types (e.g. timestamp to datetime), Save cleaned DataFrame

- document the logic of these functions here in notebook 02_data_preparation.ipynb Output: Clean, validated dataset ready for feature engineering


## to do day 3

. Load the cleaned dataset

. Split into train/test

. Train 4 models: Logistic Regression, Decision Tree, Random Forest, KNN

. Predict and calculate metrics

. Compare results in a table


