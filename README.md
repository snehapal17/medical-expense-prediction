# Medical Expense Prediction

## 📌 Project Overview
This project aims to predict future medical expenses of patients based on various factors such as:

- **Age**
- **Gender**
- **Body Mass Index (BMI)**
- **Region**
- **Smoking Behavior**

The goal is to develop an accurate regression model that can help estimate medical costs for insurance purposes.

---

## 📊 Dataset
The dataset used for this project is `med-insurance.csv`, which contains information about patients and their corresponding medical expenses.

### **Columns in the dataset:**
- `age` - Age of the individual
- `sex` - Gender (Male/Female)
- `bmi` - Body Mass Index
- `children` - Number of dependent children
- `smoker` - Smoking status (Yes/No)
- `region` - Region of residence
- `expenses` - Medical expenses (target variable)

---

## 🔎 Exploratory Data Analysis (EDA)
### **Steps Performed:**
✅ Checked for **null values** and **outliers** using Z-score and IQR method.  
✅ Visualized distributions using **Seaborn histograms** and **box plots**.  
✅ Analyzed **correlations** using a **heatmap**.  
✅ Performed **univariate, bivariate, and multivariate analysis** to understand relationships between features and medical expenses.

#### **Key Observations:**
- **Smoking** has a **strong impact** on expenses (smokers have significantly higher costs).
- **Age and BMI** also influence medical expenses.
- **Sex, Region, and Children** do not have a major independent impact.

---

## ⚙️ Data Preprocessing

1. **Handled Outliers**: Used IQR method to cap extreme values.
2. **Encoded Categorical Variables**: Applied **Label Encoding** for `sex`, `smoker`, and `region`.
3. **Log Transformation**: Applied `log1p` to expenses to handle skewness.
4. **Feature Scaling**: Standardized numerical features using **StandardScaler**.

---

## 🚀 Model Training & Evaluation
### **Algorithms Used:**
| Model                        | Training Accuracy (%) | Testing Accuracy (%) | RMSE  |
|------------------------------|----------------------|----------------------|--------|
| **Linear Regression**        | 74.48               | 76.43               | 0.425  |
| **Lasso Regression**         | 70.00               | 72.62               | 0.458  |
| **Ridge Regression**         | 74.48               | 76.43               | 0.425  |
| **Decision Tree Regression** | 78.81               | 79.37               | 0.398  |
| **Random Forest Regression** | 82.80               | 84.55               | 0.344  |
| **XGBoost Regression**       | 83.73               | 84.45               | 0.345  |
| **Gradient Boost Regression**| 86.60               | 86.27               | 0.324  |

📌 **Gradient Boosting Regressor** gave the best results with **minimum RMSE**.

---

## 📈 Feature Importance
Using **XGBoost**, we identified key features impacting medical expenses:

- **Smoker Status** (Most Important)
- **Age**
- **BMI**
- **BMI × Smoker Interaction**

---

## 📌 Installation & Usage
### **🔧 Requirements**
Ensure you have Python installed, then install dependencies:
```bash
pip install -r requirements.txt
