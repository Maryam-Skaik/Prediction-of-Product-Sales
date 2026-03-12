# Prediction-of-Product-Sales

## Project Description
This project focuses on predicting product sales for various outlets using historical sales data. The dataset contains information about products (e.g., weight, fat content, price) and outlets (e.g., type, location, establishment year), enabling us to explore patterns that influence sales and prepare data for predictive modeling.

The goal of this project is to understand the data through exploratory data analysis (EDA) and visualize relationships between product and outlet features with sales outcomes. This analysis helps identify key factors driving revenue, detect anomalies, and prepare insights for modeling.

---

## Tools Used
- Python 3
- Pandas
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## Exploratory Data Analysis (EDA)

### 1. Distribution of Item Outlet Sales
<img width="638" height="507" alt="1" src="https://github.com/user-attachments/assets/184c2e7c-a70b-4a63-960e-b187b3530cd3" />


**Interpretation:**  
The histogram shows a highly right-skewed distribution of Item_Outlet_Sales, indicating that most products generate low sales, while a few high-performing items contribute disproportionately to revenue.

---

### 2. Correlation Heatmap
<img width="767" height="682" alt="2" src="https://github.com/user-attachments/assets/37663078-d362-4de5-9778-d3ac8f4f81b5" />


**Interpretation:**  
The heatmap reveals that Item_MRP has the strongest positive correlation (0.57) with sales, suggesting that higher-priced items generally produce higher revenue. Item_Visibility shows a weak negative correlation with sales, and other numeric features show little dependency, indicating that each variable provides distinct information.

---

## Additional Insights from EDA
- **Item Weight:** A spike at `-1` indicates missing values filled for cleaning; actual weights are mostly between 5–21.  
- **Item Visibility:** Most items have low visibility, with few highly visible products.  
- **Item MRP:** The data is naturally grouped into different price tiers.  
- **Outlet Location Type:** Tier 3 outlets appear most frequently, and median sales tend to be higher in Tier 2 and Tier 3.  

---

## Next Steps
1. Feature engineering and preprocessing for predictive modeling.  
2. Implement machine learning models to predict Item_Outlet_Sales.  
3. Evaluate model performance and refine features.  

---

## Repository Contents
- `Prediction-of-Product-Sales.ipynb`: Jupyter notebook containing EDA, visualizations, and code.  
- `README.md`: This file describing the project.  

---

## How to Run
1. Clone the repository:

```bash
git clone https://github.com/Maryam-Skaik/Prediction-of-Product-Sales.git
```

2. Open the Jupyter Notebook `Prediction-of-Product-Sales.ipynb.`
3. Install required libraries if not already installed:

```bash
pip install pandas matplotlib seaborn
````

4. Run the notebook cells sequentially to reproduce the analysis and plots.
