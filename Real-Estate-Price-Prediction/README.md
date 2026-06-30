# 🏡 House Price Prediction using Multiple Linear Regression

A complete Machine Learning regression project that predicts **house prices** using **Multiple Linear Regression**. The project covers the complete ML workflow including data preprocessing, Exploratory Data Analysis (EDA), feature engineering, model building, evaluation, and comparison of three different regression models.

---

## 📌 Project Overview

The objective of this project is to predict the selling price of residential properties based on various house characteristics such as:

- Square Feet
- Number of Bedrooms
- Number of Bathrooms
- Number of Floors
- Year Built
- Garden Availability
- Swimming Pool
- Garage Size
- Location Score
- Distance to City Center

Instead of directly training a single model, three Linear Regression models were developed to analyze how feature selection affects prediction performance.

---

## 📂 Dataset Information

The dataset contains **500 residential properties** with **11 features** after removing the ID column.

| Feature | Description |
|----------|-------------|
| Square_Feet | Area of the house |
| Num_Bedrooms | Number of bedrooms |
| Num_Bathrooms | Number of bathrooms |
| Num_Floors | Number of floors |
| Year_Built | Construction year |
| Has_Garden | Garden availability (0/1) |
| Has_Pool | Swimming pool availability (0/1) |
| Garage_Size | Garage capacity |
| Location_Score | Quality score of location |
| Distance_to_Center | Distance from city center |
| Price | Target variable |

---

## 🛠 Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn

---

# Project Workflow

```
Load Dataset
      │
      ▼
Data Cleaning
(Remove ID)
      │
      ▼
Exploratory Data Analysis
      │
      ▼
Feature Engineering
(Create House Age)
      │
      ▼
Feature Selection
      │
      ▼
Feature Scaling
(StandardScaler)
      │
      ▼
Train-Test Split
      │
      ▼
Linear Regression
      │
      ▼
Model Evaluation
(RMSE & R² Score)
      │
      ▼
Model Comparison
```

---

# Exploratory Data Analysis

The dataset was analyzed before model training to understand feature distributions and relationships.

EDA includes:

- Dataset overview
- Statistical summary
- Missing value analysis
- Duplicate value checking
- Target variable distribution
- Correlation analysis
- Feature vs Target visualization
- Outlier detection

---

## 📊 Distribution of House Prices

The target variable (Price) follows an approximately normal distribution with a slight positive skew.

**Observation**

- Most houses are priced between **\$500,000 and \$700,000**
- Only one significant outlier was detected
- Distribution is suitable for Linear Regression

> **Recommended Image**
>
> `images/price_distribution.png`

---

## 📊 Correlation Analysis

A correlation heatmap was generated to identify the relationship between numerical features.

### Key Findings

- Square Feet shows a strong positive correlation with Price.
- Number of Bedrooms also has a strong influence.
- Year Built has moderate correlation.
- Distance to Center contributes very little.
- No severe multicollinearity exists among features.

> **Recommended Image**
>
> `images/correlation_heatmap.png`

---

## 📊 Feature Relationship Analysis

Scatter plots were used to study relationships between important numerical features and house prices.

Visualized Features

- Square Feet
- Location Score
- Distance to Center
- Year Built
- Garage Size

Bar plots were also generated for:

- Bedrooms
- Bathrooms
- Floors
- Garden
- Pool

---

## 📊 Outlier Detection

Outliers were detected using the **Interquartile Range (IQR)** method.

Result:

- Only **1 outlier** was detected in the Price column.

---

# Feature Engineering

A new feature was created:

```
House_Age = 2026 - Year_Built
```

Instead of using Year Built directly, House Age provides a more meaningful numerical representation of property age.

---

# Feature Scaling

Since Linear Regression performs better when numerical features are on similar scales, **StandardScaler** was applied.

The scaler standardizes each feature using:

\[
Z=\frac{x-\mu}{\sigma}
\]

where

- μ = Mean
- σ = Standard Deviation

---

# Model Building

Three Multiple Linear Regression models were developed.

---

## Model 1 — Baseline Model

### Features Used

- Square_Feet
- Num_Bedrooms
- House_Age

### Purpose

Evaluate performance using only the strongest correlated features.

### Performance

| Metric | Value |
|---------|-------|
| RMSE | **54,580.54** |
| R² Score | **0.8019** |

---

## Model 2 — Selected Features Model

### Features Used

- Square_Feet
- Num_Bedrooms
- House_Age
- Num_Bathrooms
- Num_Floors
- Has_Pool
- Has_Garden

### Purpose

Evaluate the impact of adding moderately correlated features.

### Performance

| Metric | Value |
|---------|-------|
| RMSE | **31,004.53** |
| R² Score | **0.9361** |

---

## Model 3 — Full Feature Model

### Features Used

All available features.

### Purpose

Measure the maximum predictive capability of the dataset.

### Performance

| Metric | Value |
|---------|-------|
| RMSE | **21,020.13** |
| R² Score | **0.9706** |

---

# Model Comparison

| Model | RMSE | R² Score |
|-------|-------:|---------:|
| Baseline Model | 54,580.54 | 0.8019 |
| Selected Features Model | 31,004.53 | 0.9361 |
| Full Feature Model | **21,020.13** | **0.9706** |

---

## 📈 Performance Improvement

| Model | Improvement |
|--------|-------------|
| Baseline | Strong foundation using only core structural features |
| Selected Features | Significant improvement after adding moderate predictors |
| Full Feature Model | Best overall performance with lowest prediction error |

---

# Model Evaluation

The models were evaluated using:

### Root Mean Squared Error (RMSE)

Measures the average prediction error.

Lower RMSE indicates better performance.

---

### R² Score

Measures how much variance in house prices is explained by the model.

Higher R² indicates better prediction capability.

---

## Residual Analysis

Residual plots were generated for every model to verify Linear Regression assumptions.

A good residual plot should show:

- Random distribution around zero
- No visible patterns
- Constant variance

These observations indicate that the regression model fits the dataset well.

---

# Project Structure

```
House-Price-Prediction/
│
├── dataset/
│   └── real_estate_dataset.csv
│
├── images/
│   ├── price_distribution.png
│   ├── correlation_heatmap.png
│   └── residual_plot.png
│
├── notebooks/
│   └── House_Price_Prediction.ipynb
│
├── requirements.txt
│
└── README.md
```

---

# Installation

Clone the repository

```bash
git clone https://github.com/stephinjacob007/Machine-Learning-Regression-Projects.git
```

Move into the project folder

```bash
cd Real-Estate-Price-Prediction
```

Install dependencies

```bash
pip install -r requirements.txt
```

Run the notebook

```bash
jupyter notebook
```

---

# Results

- Successfully built three Multiple Linear Regression models.
- Performed complete Exploratory Data Analysis.
- Applied Feature Engineering by creating House Age.
- Compared different feature selection strategies.
- Achieved an **R² Score of 0.9706** using all available features.
- Demonstrated that combining even weakly correlated features significantly improves prediction accuracy.

---

# Future Improvements

- Ridge Regression
- Lasso Regression
- ElasticNet Regression
- Decision Tree Regressor
- Random Forest Regressor
- XGBoost Regressor
- Feature Importance Analysis
- Hyperparameter Tuning
- Cross Validation
- Model Deployment using Streamlit or Flask
