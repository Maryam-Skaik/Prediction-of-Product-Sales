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
- Model interpretability (coefficients & feature importance)
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
- One-Hot Encoding applied for categorical features
- Scaling applied where needed for linear models
- Data cleaned and prepared for modeling pipelines

---

## 📊 Exploratory Data Analysis

### 🔹 Key Insight 1: Price vs Sales

#### 📈 Regplot: `Item_MRP` vs `Item_Outlet_Sales`

- **Observation:** A positive correlation (~0.57) between item price and sales.
- **Business Interpretation:** Pricing strategy plays a critical role in revenue generation.

---

### 🔹 Key Insight 2: Outlet Type Impact

#### 📊 Barplot + Stripplot: `Outlet_Type` vs `Item_Outlet_Sales`

- **Observation:** Supermarket Type 3 has the highest average sales, followed by Type 1 and Type 2.
- **Business Interpretation:** Larger, well-established supermarket formats outperform smaller stores.

---

## 🤖 Model Summary

Two types of models were used:
- **Linear Regression** → for interpretability (coefficients)
- **Random Forest Regressor** → for performance & feature importance

### 📊 Model Performance (Random Forest)

| Metric | Training | Test |
|--------|----------|------|
| R²     | 0.94     | 0.55 |
| RMSE   | 428      | 1112 |
| MAE    | 297      | 771  |

### 🔍 Interpretation
- Strong performance on training data
- Moderate generalization → slight overfitting
- Captures key nonlinear relationships in sales

---

# 📈 Model Explainability

## 🔷 1. Linear Regression Coefficients

### 📊 Coefficients Visualization

<img width="733" height="588" alt="image" src="https://github.com/user-attachments/assets/2ce0163c-7379-4397-b0d0-3bde691d81d4" />


### 🧠 What Coefficients Mean
- Coefficients show **direction + magnitude of impact** on sales
- Positive → increases sales  
- Negative → decreases sales  

---

### 🔝 Top Impactful Features (Linear Regression)

#### 1. `Outlet_Type_Supermarket Type3` (+3352)
- Strongest positive driver of sales  
- Being in this outlet type significantly increases predicted sales  

#### 2. `Outlet_Type_Supermarket Type1` (+1954)  
#### 3. `Outlet_Type_Supermarket Type2` (+1640)  

- All supermarket types strongly increase sales compared to baseline  
- Confirms that **store type is a dominant business factor**

---

### ⚠️ Important Note
- These are **One-Hot Encoded features**
- Interpretation is:
  > “If the item belongs to this category, sales change by X amount”

---

### 📉 Examples of Negative Effects
- `Item_Visibility` (-21.65) → Higher visibility slightly decreases sales  
- `Item_Weight` (-7.74) → Very small negative impact  

---

## 🌳 2. Tree-Based Model Feature Importance

### 📊 Feature Importance Visualization

<img width="944" height="516" alt="image" src="https://github.com/user-attachments/assets/77fa0a5f-295f-4af4-9a7d-ba3b2bb7070b" />

---

### 🧠 What Feature Importance Means
- Measures how much a feature contributes to prediction accuracy
- **Does NOT show direction (increase/decrease)**  
- Only shows **importance magnitude**

---

### 🔝 Top 5 Most Important Features

#### 1. `Item_MRP` (0.44)
- Dominates the model  
- Pricing is the most critical driver of sales  

#### 2. `Outlet_Type_Grocery Store` (0.19)
- Strong influence on predictions  
- Confirms outlet structure matters  

#### 3. `Item_Visibility` (0.099)
- Visibility affects model decisions significantly  

#### 4. `Outlet_Type_Supermarket Type3` (0.057)
- Reinforces regression findings  

#### 5. `Item_Weight` (0.051)
- Moderate contribution  

---

### ⚠️ Important Observation
- Tree-based importance is **biased toward numeric features**
- That’s why `Item_MRP` dominates heavily
- Some categorical features may appear less important than they actually are

---

## 🔄 Feature Importance vs Coefficients

| Aspect | Coefficients | Feature Importance |
|--------|-------------|-------------------|
| Direction (±) | ✅ Yes | ❌ No |
| Magnitude | ✅ Yes | ✅ Yes |
| Bias | ❌ Low | ⚠️ High (numeric bias) |
| Interpretability | ✅ High | ⚠️ Medium |

---

## 🧩 Additional Insights

### 🏪 Outlet-Level Insights
- `Outlet_Type` is the **strongest structural driver**
- Supermarket Type 3 consistently outperforms others
- `Outlet_Size` also contributes to performance

---

### 🧩 Product-Level Insights
- `Item_MRP` is the **most influential feature overall**
- `Item_Visibility` has mixed effects depending on model

---

## 📉 Sales Behavior

- Sales distribution is right-skewed
- Few high-revenue items dominate total sales

---

## ⚠️ Observations & Limitations

- Tree models show **bias toward numerical features**
- One-hot encoding increases feature dimensionality
- Some categorical levels have low representation
- Moderate overfitting observed in Random Forest

---

## 🚀 Final Recommendations to Stakeholders

### 📌 1. Pricing Strategy
- Focus heavily on optimizing **Item_MRP**
- Small price adjustments can significantly impact revenue

### 📌 2. Store Strategy
- Invest in **Supermarket Type 3 expansion**
- Prioritize high-performing outlet formats

### 📌 3. Product Placement
- Improve visibility strategies carefully  
- Visibility alone does not guarantee higher sales

### 📌 4. Inventory Optimization
- Focus on high-performing product categories
- Reduce low-impact or underperforming items

---

## 🛠️ Tech Stack

- Python 🐍  
- Pandas  
- NumPy  
- Matplotlib / Seaborn  
- Scikit-learn  

---

## 📎 Author

**Maryam Skaik**
