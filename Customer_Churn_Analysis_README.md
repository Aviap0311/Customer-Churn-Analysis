# 📉 Customer Churn Analysis using Machine Learning

Predicting **customer churn** (whether a customer will leave or stay) using machine learning and data analysis techniques.  
This project helps businesses identify patterns and take preventive actions to reduce customer loss.

---

## 📘 Project Overview

Customer churn occurs when a customer stops using a company’s product or service.  
By analyzing historical customer data, we can build predictive models to identify at-risk customers before they leave.

### Objectives:
- Analyze customer behavior data 🧠  
- Identify key factors leading to churn 📊  
- Build and evaluate churn prediction models 🤖  
- Deploy a prediction API using Flask 🚀  

---

## 📂 Folder Structure

```
customer-churn-analysis/
├─ data/
│  ├─ raw/                # Original dataset (churn_data.csv)
│  └─ processed/          # Cleaned and transformed data
├─ notebooks/
│  ├─ 01-EDA.ipynb        # Exploratory Data Analysis
│  └─ 02-Modeling.ipynb   # Model training and evaluation
├─ src/
│  ├─ data_processing.py  # Data cleaning and preprocessing
│  ├─ feature_engineering.py # Feature creation
│  ├─ model_training.py   # Model training logic
│  └─ evaluate.py         # Model performance evaluation
├─ models/
│  └─ churn_model.joblib  # Trained model
├─ app/
│  └─ app.py              # Flask API for prediction
├─ reports/
│  └─ figures/            # EDA plots and model visuals
├─ requirements.txt       # Dependencies list
└─ README.md              # Documentation file
```

---

## 🧩 Dataset

- **Source:** [Kaggle - Telco Customer Churn Dataset](https://www.kaggle.com/blastchar/telco-customer-churn)
- **Target Variable:** `Churn` (Yes/No)
- **Size:** ~7,000 rows × 20+ features

### Key Features:
- `gender` – Customer’s gender (Male/Female)  
- `SeniorCitizen` – Whether the customer is a senior citizen  
- `Partner` / `Dependents` – Family-related info  
- `tenure` – Number of months the customer has stayed  
- `Contract` – Type of contract (Month-to-month, One year, Two year)  
- `MonthlyCharges` – The amount charged to the customer monthly  
- `TotalCharges` – Total amount charged  

---

## ⚙️ Installation and Setup

### 1. Clone the Repository
```bash
git clone https://github.com/Aviap0311/customer-churn-analysis.git
cd customer-churn-analysis
```

### 2. Create Virtual Environment
```bash
python -m venv venv
venv\Scripts\activate        # For Windows
# or
source venv/bin/activate       # For Mac/Linux
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

---

## 🧠 Model Building Steps

### Step 1: Data Preprocessing
- Handle missing values
- Encode categorical columns (LabelEncoder / OneHotEncoder)
- Normalize numerical features
- Convert target variable into binary (Yes=1, No=0)

### Step 2: Feature Engineering
- Create new features like `AverageChargesPerMonth`
- Drop redundant or highly correlated columns
- Balance dataset using SMOTE (if needed)

### Step 3: Model Training
Trained multiple models and compared results:

| Model | Accuracy | Precision | Recall | F1-Score |
|--------|-----------|-----------|----------|-----------|
| Logistic Regression | 0.81 | 0.77 | 0.70 | 0.73 |
| Random Forest | 0.85 | 0.80 | 0.78 | 0.79 |
| XGBoost | **0.87** | **0.83** | **0.81** | **0.82** |

### Step 4: Model Saving
Best model (`XGBoost`) saved as `churn_model.joblib`.

---

## 🚀 API Deployment (Flask App)

Run the churn prediction API locally:

### Run Flask App
```bash
cd app
python app.py
```

### API Endpoint
- **URL:** `http://127.0.0.1:5000/predict`
- **Method:** POST  
- **Input (JSON example):**
```json
{
  "gender": "Female",
  "SeniorCitizen": 0,
  "Partner": "Yes",
  "Dependents": "No",
  "tenure": 12,
  "Contract": "Month-to-month",
  "MonthlyCharges": 70.35,
  "TotalCharges": 845.5
}
```

- **Output:**
```json
{
  "Churn_Prediction": "Yes",
  "Probability": 0.83
}
```

---

## 📊 Evaluation Metrics

| Metric | Description |
|---------|-------------|
| **Accuracy** | % of correct predictions |
| **Precision** | % of correct churn predictions |
| **Recall** | % of actual churns correctly predicted |
| **F1-Score** | Harmonic mean of precision and recall |

---

## 📈 Visualizations

- Customer tenure vs churn rate  
- Monthly charges distribution  
- Correlation heatmap  
- Feature importance (XGBoost / RandomForest)  

All visuals stored in `reports/figures/`.

---

## 💾 Technologies Used

| Category | Libraries |
|-----------|------------|
| Data Handling | pandas, numpy |
| Visualization | matplotlib, seaborn |
| Machine Learning | scikit-learn, xgboost, catboost |
| Model Saving | joblib |
| Deployment | flask |

---

## 📦 Future Improvements

- 🧭 Add customer feedback sentiment analysis  
- 🕒 Include time-based churn trends  
- 🌐 Deploy model on cloud (AWS/Render/Hugging Face)  
- 📊 Add interactive dashboard (Streamlit or Power BI)  

---

## 👨‍💻 Author

**Avinash Pawar**  
📧 Email: [avinashpawar1010@gmail.com](mailto:avinashpawar1010@gmail.com)  
💻 GitHub: [Aviap0311](https://github.com/Aviap0311)

---

## 🏁 Conclusion

This project demonstrates how businesses can leverage machine learning to predict and reduce customer churn.  
It covers the full data science workflow — from EDA to deployment 🚀

---

> ⭐ Don’t forget to star the repository if you found it useful!
