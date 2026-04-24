# 🛒 BigMart Sales Prediction

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-orange)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-blue)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-green)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Plotting-yellow)

---

## 📌 Overview

This project focuses on predicting `Item_Outlet_Sales` in the BigMart dataset using machine learning techniques. The objective is to uncover patterns and key factors affecting sales, and to develop a model that can forecast future sales based on historical data.

The workflow includes:
- Data preprocessing and cleaning
- Exploratory data analysis (EDA)
- Model development and evaluation
- Business-oriented insights and recommendations

---

## 📂 Dataset Summary

- **Total Records:** 8523  
- **Features:** 12  
- **Target Variable:** `Item_Outlet_Sales`

### Feature Types

- **Numerical:**  
  `Item_Weight`, `Item_Visibility`, `Item_MRP`, `Outlet_Establishment_Year`, `Item_Outlet_Sales`

- **Categorical:**  
  `Item_Fat_Content`, `Item_Type`, `Outlet_Size`, `Outlet_Location_Type`, `Outlet_Type`

---

## 🧹 Data Preparation

- Missing values handled using appropriate imputation strategies
- Categorical inconsistencies standardized (e.g., `Item_Fat_Content`)
- Data cleaned and prepared for modeling

---

## 📊 Exploratory Data Analysis

### 🔹 Key Insight 1: Price vs Sales

#### 📈 Regplot: `Item_MRP` vs `Item_Outlet_Sales`

- **Observation:** A positive correlation (~0.57) between item price and sales.
- **Business Interpretation:** Pricing strategy plays a critical role in revenue generation.

### 🔹 Key Insight 2: Outlet Type Impact

#### 📊 Barplot + Stripplot: `Outlet_Type` vs `Item_Outlet_Sales`

- **Observation:** Supermarket Type 3 has the highest average sales, followed by Type 1 and Type 2.
- **Business Interpretation:** Larger, well-established supermarket formats outperform smaller stores.

---

## 🤖 Model Summary

A machine learning model was developed to predict `Item_Outlet_Sales`.

- **Model Used:** Random Forest Regressor
- **Why:** Handles non-linear relationships and mixed feature types effectively

### 📊 Model Performance

| Metric | Training | Test |
|--------|----------|------|
| R²     | 0.94     | 0.55 |
| RMSE   | 428      | 1112 |
| MAE    | 297      | 771  |

### 🔍 Interpretation
- The model performs well on training data but shows moderate generalization.
- The gap in performance suggests some overfitting, but the model captures key sales patterns.

---

## 🧩 Additional Insights

### 🏪 Outlet-Level Insights
- **`Outlet_Type`:** Major driver of sales performance, with supermarkets outperforming smaller outlets.
- **`Outlet_Size`:** Medium-sized outlets tend to have the highest sales.

### 🧩 Product-Level Insights
- **`Item_MRP`:** Strong positive correlation with sales (0.57).
- **`Item_Visibility`:** Weak negative correlation (~ -0.13).

---

## 📉 Sales Behavior
- Sales distribution is right-skewed, with a few high-revenue items and many lower-selling products.

---

## ⚠️ Observations & Limitations
- Some categorical features are imbalanced.
- Imputation introduces repeated values (expected).
- Non-linear relationships were observed, and further model tuning may be required.

---

## 🚀 Conclusion

- **Strongest drivers:** `Item_MRP`, `Outlet_Type`
- **Moderate impact:** `Outlet_Size`, `Outlet_Location_Type`
- **Low impact:** `Item_Weight`, `Item_Visibility`

### 📌 Recommendations:
- Focus on **pricing optimization** for better sales performance.
- Invest in **high-performing outlet types** to boost revenue.
- Prioritize **top-selling product categories** for marketing and stock management.

---

## 🛠️ Tech Stack

- Python 🐍  
- Pandas  
- NumPy  
- Matplotlib / Seaborn  

---

## 📎 Author

**Maryam Skaik**  
