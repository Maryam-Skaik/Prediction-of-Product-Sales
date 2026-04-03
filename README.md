# 🛒 BigMart Sales EDA

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-orange)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-blue)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-green)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Plotting-yellow)

---

## 📌 Overview
This project performs **Exploratory Data Analysis (EDA)** on the BigMart dataset to uncover patterns and identify the key factors affecting `Item_Outlet_Sales`.

The workflow includes:
- Data cleaning and preprocessing  
- Univariate and bivariate analysis  
- Visualization-driven insights  
- Business-oriented interpretation  

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

## 🧹 Data Cleaning

### 🔹 Missing Values
- **Item_Weight (~17%)**
  - Missing values are **not random** (dependent on `Item_Type`)
  - Imputed using **median per Item_Type**

- **Outlet_Size (~28%)**
  - Missing values are **not random** (dependent on `Outlet_Type`)
  - Imputed using **mode per Outlet_Type**

---

### 🔹 Data Consistency
- Standardized `Item_Fat_Content`:
  - `LF`, `low fat` → `Low Fat`
  - `reg` → `Regular`

- No duplicate records detected  

---

## 📊 Exploratory Data Analysis

### 🔹 Key Visualization 1: Price vs Sales

#### 📈 Regplot: `Item_MRP` vs `Item_Outlet_Sales`

<img width="700" height="492" alt="01" src="https://github.com/user-attachments/assets/f0adc5fa-ba35-4078-ad2c-f50084e4eb96" />

- A regression plot was used to examine the relationship between item price and sales.

**Observation:**
- There is a clear **positive correlation (≈ 0.57)** between `Item_MRP` and `Item_Outlet_Sales`.
- Sales tend to increase as price increases.
- The relationship is not perfectly linear, indicating possible pricing segments.

**Insight:**
- `Item_MRP` is the **strongest numerical driver** of sales.

**Business Interpretation:**
- Pricing strategy plays a critical role in revenue generation.
- Optimizing price ranges can significantly impact sales performance.

---

### 🔹 Key Visualization 2: Outlet Type Impact

#### 📊 Barplot + Stripplot: `Outlet_Type` vs `Item_Outlet_Sales`

<img width="736" height="485" alt="02" src="https://github.com/user-attachments/assets/78f4caa0-1f6a-45fe-b67b-1fa37d96cbb2" />

- A **barplot** (mean sales) combined with a **stripplot** (distribution) was used to analyze outlet performance.

**Observation:**
- **Supermarket Type3** has the highest average sales.
- Followed by **Supermarket Type1**.
- **Supermarket Type2** performs moderately.
- **Grocery Store** has the lowest sales.
- Stripplot shows variability and spread within each category.

**Insight:**
- `Outlet_Type` has a **strong impact** on sales performance.

**Business Interpretation:**
- Larger, well-established supermarket formats outperform smaller stores.
- Grocery stores generate significantly lower revenue.

---

## 📈 Additional Findings

### 🧩 Product-Level Insights
- `Item_MRP` → Strong positive correlation (**0.57**)  
- `Item_Visibility` → Weak negative correlation (~ -0.13)  
- `Item_Weight` → No significant impact  
- `Item_Type` → Certain categories perform better  

---

### 🏪 Outlet-Level Insights
- `Outlet_Type` → Major driver of sales  
- `Outlet_Size` → Medium outlets perform best  
- `Outlet_Location_Type` → Tier 2 & Tier 3 outperform Tier 1  
- `Outlet_Establishment_Year` → No strong relationship  

---

## 📉 Sales Behavior
- Sales distribution is **right-skewed**  
- Few items generate **very high sales**  
- Majority of items contribute moderate to low revenue  

---

## ⚠️ Observations & Limitations
- Some categorical features are **imbalanced**  
- Imputation introduces repeated values (expected)  
- Weak correlations suggest **non-linear relationships**  

---

## 🚀 Conclusion
- **Strongest drivers:** `Item_MRP`, `Outlet_Type`  
- **Moderate impact:** `Outlet_Size`, `Outlet_Location_Type`  
- **Low impact:** `Item_Weight`, `Item_Visibility`  

### 📌 Recommendations:
- Focus on **pricing optimization**  
- Invest in **high-performing outlet types**  
- Prioritize **top-selling product categories**  

---

## 📌 Next Steps
- Feature engineering (`Outlet_Age`)  
- Handle skewness (log transformation)  
- Build predictive models  
- Evaluate feature importance  

---

## 🛠️ Tech Stack
- Python 🐍  
- Pandas  
- NumPy  
- Matplotlib / Seaborn  

---

## 📎 Author
**Maryam Skaik**  
Backend Developer | Data Science Enthusiast
