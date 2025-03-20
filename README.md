# 🚀 Machine Learning Capstone Project - Ad Revenue Prediction

## 📌 Project Overview
This project focuses on **predicting future ad revenue** for **DeltaX**, a digital advertising platform.  
Using historical performance data from **August 1st to February 28th**, our goal is to estimate ad revenue for **March 1st–15th**, while minimizing **Root Mean Squared Error (RMSE)**.  

The project includes:
- **Exploratory Data Analysis (EDA)**
- **Feature Engineering**
- **Decision Tree Model with Hyperparameter Tuning**

---

## ❓ Problem Statement
DeltaX advertisers need to forecast campaign performance. Given historical data (**impressions, clicks, cost, conversions, etc.**), the task is to build a model to predict revenue for a future **15-day window**.  

Since actual test dataset values are not provided, the training dataset was **split into train and test sets** to evaluate model performance.

---

## 📊 Dataset Description
### **Training Data**  
- **4,571 rows, 9 columns**  
- Features: `date`, `campaign`, `adgroup`, `ad`, `impressions`, `clicks`, `cost`, `conversions`, `revenue`  

### **Test Data**  
- **318 rows, 8 columns** (same as training data, **excluding revenue**)  

### **Target Variable:** `revenue`

### **Key Features**  
🔹 **Categorical**: `campaign`, `adgroup`, `ad`, `date`  
🔹 **Numerical**: `impressions`, `clicks`, `cost`, `conversions`  

---

## 🔍 Key Steps
### **1️⃣ Exploratory Data Analysis (EDA)**
- **Visualized distributions** of categorical variables (`adgroup`, `campaign`).
- **Analyzed relationships** between numerical features and revenue using **scatterplots & pairplots**.
- **Observed non-linear relationships** between features and revenue.

### **2️⃣ Data Preprocessing**
- **Dropped redundant features**:
  - `campaign`: Only **1 unique value**, making it **meaningless**.
  - `date`: Not useful for **non-time series analysis**.
- **Encoded** `adgroup` using `pd.get_dummies()` (**4 unique values**).
- **Dropped `ad`** due to **high cardinality** (**70 unique values**).

### **3️⃣ Model Building**
- **Split** the training dataset into **train and test sets**.
- **Implemented Decision Tree Model** with **GridSearchCV** for **hyperparameter tuning**.
- **Compared with Linear Regression**, which performed **poorly** due to **non-linear relationships**.
- **Achieved an RMSE of 0.375** on the test set.

---

## 📈 Results
**Model Performance:**  
✅ **RMSE = 0.375** (on the test set split from training data)  

**Key Insights:**
- **`adgroup` and `ad`** showed **significant variability** in revenue.
- **Non-linear relationships** suggested that **tree-based models** are more suitable.
- **Linear Regression was not effective** due to the **non-linear nature** of the data.

---

## 📦 Dependencies
- **Python 3.7+**
- **Libraries**: `pandas`, `numpy`, `scikit-learn`, `seaborn`, `matplotlib`

### **Install Dependencies:**
pip install pandas numpy scikit-learn seaborn matplotlib

## 🔧 **Usage** 
Clone the repository:
git clone https://github.com/Gowthamipriya1307/Exploratory-Data-Analysis.git
cd Exploratory-Data-Analysis
Run the Jupyter Notebook:
jupyter notebook Machine_Learning_Capstone_Project.ipynb

## 🚀 Future Improvements
- ✅ **Explore other tree-based models** like **Random Forest** or **Gradient Boosting** for better performance.  
- ✅ **Investigate feature engineering techniques** to handle **high-cardinality categorical variables** like `ad`.  
- ✅ **Perform cross-validation** to ensure model robustness.  





