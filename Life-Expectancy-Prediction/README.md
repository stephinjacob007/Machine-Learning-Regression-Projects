# Life Expectancy Prediction using Machine Learning

An end-to-end regression analysis and machine learning framework designed to predict global life expectancy using demographic, socioeconomic, and healthcare-related factors. This project implements comprehensive data preprocessing, exploratory data analysis (EDA), and compares baseline linear models against tree-based ensembles to determine the strongest predictive indicators of longevity.

---

## 📌 Project Overview
Predicting life expectancy is critical for public health policy, resource allocation, and identifying regional disparities. Utilizing the World Health Organization (WHO) dataset, this project uncovers hidden socioeconomic trends and benchmarks regression models to determine the primary global drivers of life expectancy. 

Our findings indicate that **HIV/AIDS prevalence**, **Income Composition of Resources (HDI)**, and **Adult Mortality rates** carry the highest predictive weight. The final optimized ensemble model achieves an **$R^2$ score of 0.967**.

---

## 📊 Dataset & Features
The model operates on a heavily curated dataset comprising 2,928 samples across 22 primary features spanning the years 2000–2015. 

### Key Feature Engineering:
* **Log Transformations:** Applied to highly skewed features (`gdp`, `population`, `percentage_expenditure`, `measles`) to improve linear relationships.
* **Aggregated Indices:** Generated unified health columns including `avg_vaccination` (combining Polio, Hepatitis B, and Diphtheria rates) and `avg_thinness`.
* **Socioeconomic Grouping:** Extracted a structured `continent` feature mapping from raw geographical country indices.

---

## 🛠️ Tech Stack & Dependencies
* **Core Environment:** Python 3.10+, Jupyter Notebook
* **Data Manipulation:** `pandas`, `numpy`
* **Visualization:** `matplotlib`, `seaborn`
* **Machine Learning Framework:** `scikit-learn`
* **Geospatial Processing:** `pycountry`, `pycountry-convert`

---

## 📈 Exploratory Data Analysis (EDA) Highlights
Before model construction, rigorous EDA was executed to establish baseline domain contexts:
* **Global Trends:** Life expectancy demonstrates an upward trajectory year-over-year.
* **Economic Stratification:** Marked categorical differences in age ceilings are observed when isolating Developed vs. Developing nation statuses.
* **Correlative Clusters:** Strong positive links exist between structured education (`schooling`) and higher life expectancy, while inverse linear paths exist alongside disease indexing.

---

## 🤖 Model Performance & Evaluation

We evaluated baseline performance via standard **Ordinary Least Squares (OLS) Linear Regression** and contrasted it against a non-linear **Random Forest Ensemble**.

### Performance Metrics Summary

| Model Metric | Linear Regression | Random Forest Regressor |
| :--- | :---: | :---: |
| **Mean Absolute Error (MAE)** | 2.826 | **1.052** |
| **Root Mean Squared Error (RMSE)** | 3.686 | **1.686** |
| **$R^2$ Coefficient of Determination** | 0.8430 | **0.9671** |

### 1. Baseline Model: Linear Regression
The linear baseline captures 84.3% of target variance. However, residual diagnostics revealed minor signs of heteroscedasticity, signaling non-linear trends within socioeconomic metrics.

<p align="center">
  <img width="860" height="677" alt="image" src="https://github.com/user-attachments/assets/4443ef36-4662-4c2f-b77f-0f7e5113daa7" />

    
  <img width="869" height="678" alt="image" src="https://github.com/user-attachments/assets/4a0f820a-92c1-4cce-a7d1-6edca937636b" />

</p>

### 2. Champion Model: Random Forest Regressor
By capturing intricate feature interactions without forcing monotonic assumptions, the Random Forest model slashed prediction errors drastically—slashing RMSE to **1.686 years**.

<p align="center">
  <img width="862" height="681" alt="image" src="https://github.com/user-attachments/assets/53caf868-9281-4aff-9cdd-e680d5d194c9" />

  <img width="860" height="679" alt="image" src="https://github.com/user-attachments/assets/4d7db396-d68a-472d-aa65-d88f79db79b9" />

</p>

---

## 🔑 Feature Importance Insights

The Gini-importance calculations extracted from our champion Random Forest architecture illustrate where the model uncovers the highest predictive signal:

<p align="center">
  <img width="439" height="378" alt="image" src="https://github.com/user-attachments/assets/1df8fd19-5a63-4495-93cf-b14c355b3979" />

</p>

> **Key takeaway:** Over **58.7%** of predictive variance is driven uniquely by a country's `hiv/aids` footprint, followed closely by economic indicators like the `income_composition_of_resources` (**19.2%**). Global health strategies targeted directly at these spaces have the most immediate structural correlation with lengthened life expectancies.

---

## 🚀 How to Run Locally

### 1. Clone the repository
```bash
git clone [https://github.com/stephinjacob007/Machine-Learning-Regression-Projects.git](https://github.com/stephinjacob007/Machine-Learning-Regression-Projects.git)
cd Machine-Learning-Regression-Projects/Life-Expectancy-Prediction
