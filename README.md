# 📊 Telco Customer Churn Prediction

This project analyzes customer churn data from a telecom company to predict whether a customer will churn (leave the service). The analysis includes exploratory data analysis (EDA), data cleaning, feature encoding, logistic regression modeling, feature selection, and model evaluation.

---

## 📁 Dataset
- Source: `blastchar/telco-customer-churn` from Kaggle via `kagglehub`.
- Total entries: 7,043
- Features: 21 (Categorical and numerical)
- Target: `Churn` (Yes/No)

---

## 🔍 Exploratory Data Analysis (EDA)

Here are some visual insights discovered from the data:

### Internet Service vs Churn
- 📉 **Fiber Optic users churn the most** (high cost).
- 🟩 Customers with **no internet service churn the least**.

![Internet Service Churn](#)

### Contract Type vs Churn
- ⛔ **Month-to-Month** contracts show the **highest churn** — easier to leave.
- ✅ **Two-Year contracts** show **lowest churn**.

![Contract Churn](![Screenshot 2025-06-18 185042](https://github.com/user-attachments/assets/c03b2d66-0034-4a76-a0d3-c993ad7d84f5))


### Payment Method vs Churn
- 📉 **Electronic check** users churn more often than others.

![Payment Method Churn](#)

---

## 🧹 Data Preprocessing

- Cleaned `TotalCharges` (removed empty strings, converted to float).
- Encoded categorical columns using `get_dummies` and `OrdinalEncoder`.
- Label-encoded the target (`Churn`) to binary.

---

## 🔧 Feature Selection

Used **Sequential Forward Selection (SFS)** to choose top 6 features:
- `PhoneService_Yes`
- `MultipleLines_Yes`
- `StreamingMovies_Yes`
- `InternetService_Fiber optic`
- `PaymentMethod_Electronic check`
- `tenure`

---

## 📈 Model Training & Results

### Logistic Regression (Baseline)
- Accuracy: **78.89%**

### Logistic Regression (SFS + Undersampling)
- Accuracy: **75.67%**
- Precision: **76.95%**
- Recall: **72.36%**
- F1 Score: **74.58%**
- Log Loss: **49.09**

### Other Models
| Model               | Accuracy (%) |
|---------------------|--------------|
| Logistic Regression | 81.23        |
| Naive Bayes         | 75.31        |
| SVM (Linear Kernel) | 80.89        |
| Decision Tree       | 71.12        |

---

## 📷 EDA Visuals (Drop Here)

> You can drag & drop your best EDA visuals below this section:

- ![EDA Screenshot 1](#)
- ![EDA Screenshot 2](#)
- ![EDA Screenshot 3](#)

---

## ✅ Conclusion

- **Contract type**, **tenure**, **internet service**, and **payment method** significantly influence customer churn.
- Feature selection and proper encoding play a key role in improving model performance.
- Logistic Regression with feature selection performs reasonably well for this classification problem.

---

## 📌 Tools Used
- Python, Pandas, Seaborn, Scikit-learn
- KaggleHub, Matplotlib, Imbalanced-learn
