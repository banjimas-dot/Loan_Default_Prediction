# Loan Default Prediction

This project builds a complete machine learning pipeline to predict loan default using borrower demographic, financial, and loan‑related characteristics. It includes data cleaning, exploratory data analysis (EDA), modeling, evaluation, and interpretation.

The goal is to understand the key drivers of loan default and build a model that can support credit‑risk decision‑making.

---

## 📁 Project Structure

- `data/` – dataset
- `notebooks/` – Jupyter notebooks for EDA, modeling, and evaluation
- `src/` – Python scripts for preprocessing and model training
- `requirements.txt` – project dependencies
- `README.md` – project documentation


---

## 📊 Dataset

The full dataset is too large to upload to GitHub.

To use this project:

1. Download the dataset from your source.
2. Place it in:


A **5,000‑row sample** is included in `data/sample/` for quick testing.

---

## 🧹 1. Data Cleaning

The cleaning notebook performs:

- Handling missing values  
- Converting categorical variables  
- Encoding binary Yes/No fields  
- Fixing data types  
- Removing duplicates  
- Saving a cleaned dataset for EDA  

The cleaned dataset is stored at:


---

## 📈 2. Exploratory Data Analysis (EDA)

The EDA notebook explores:

### **Numeric Distributions**
- Income, LoanAmount, CreditScore, DTIRatio, etc.
- Well‑spread, realistic financial distributions.

### **Categorical Distributions**
- Education, EmploymentType, MaritalStatus, LoanPurpose, etc.

### **Default Imbalance**
- 88% non‑default  
- 12% default  
- Explains why recall is low for the minority class.

### **Key Insights**
- Defaulters tend to have:
  - Lower income  
  - Higher loan amounts  
  - Lower credit scores  
  - Higher DTI ratios  
- EmploymentType and MaritalStatus show strong separation in default rates.
- Borrowers with a **co‑signer** default less.

---

## 🤖 3. Modeling

Three models were trained and evaluated:

- **Logistic Regression**
- **Decision Tree**
- **Random Forest**

### **Performance Summary**

| Model               | Accuracy | Recall (Default=1) | ROC‑AUC |
|--------------------|----------|---------------------|---------|
| Logistic Regression | **0.88** | **0.03**            | **0.73** |
| Decision Tree       | 0.81     | 0.26                | 0.57    |
| Random Forest       | 0.88     | 0.00–0.10           | 0.71    |

### **Why Logistic Regression Wins**
- Highest ROC‑AUC (0.73)
- Most stable generalization
- Matches the linear relationships in the dataset
- Clean, interpretable coefficients

### **Confusion Matrix (Logistic Regression)**

- Correctly predicts most non‑defaults  
- Struggles with defaults due to class imbalance  
- Typical behavior in credit‑risk datasets  

### **Feature Importance (Logistic Regression)**

**Top predictors increasing default risk:**
- Higher InterestRate  
- Higher LoanAmount  
- Being Unemployed  
- LoanPurpose = Other / Business  
- Higher DTIRatio  

**Top predictors reducing default risk:**
- Higher Income  
- Higher CreditScore  
- More MonthsEmployed  
- Having a Co‑Signer  
- Being Married  

---

## ⚠️ Class Imbalance Note

The dataset is imbalanced (12% defaults).  
This causes:

- Low recall for the default class  
- Undefined metric warnings (normal)  
- Models predicting mostly “No Default”  

Possible improvements (not implemented yet):

- Class weighting  
- SMOTE oversampling  
- Threshold tuning  
- Balanced Random Forest  

---

## 🛠️ Technologies Used

- Python  
- Pandas, NumPy  
- Scikit‑learn  
- Matplotlib, Seaborn  
- Jupyter Notebooks  

---

## 📌 Future Work

- Apply class balancing techniques  
- Add hyperparameter tuning  
- Deploy the model as an API  
- Build a Streamlit dashboard  

---

## 👤 Author

**Alfred Goma & Banji Masinja**  
Loan Default Prediction Project  
2026  

---

