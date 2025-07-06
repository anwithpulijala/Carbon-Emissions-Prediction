
# 🌍 Carbon Emissions Prediction using Machine Learning

This repository contains a full machine learning pipeline for predicting **CO₂ emissions per capita** for various countries using historical environmental and economic data. The pipeline is divided into three major stages:

1. **Data Preparation**
2. **Data Exploration**
3. **Model Building**

---

## 🎯 Project Objective

The goal of this project is to create a predictive model that can estimate how much carbon dioxide (CO₂) a person emits on average in a given country, based on variables like energy use, foreign investment, land usage, and urbanization. The project aids in climate monitoring, policy formulation, and sustainability planning.

---

## 🗂️ Folder Structure

- `WEEK_1/1_data_preparation.ipynb`: Loads and processes raw Excel data, removes unusable fields, and converts it to a clean and structured format.
- `WEEK_2/2_data_exploration.ipynb`: Performs visual and statistical exploration to understand feature relationships and trends.
- `WEEK_3/Model_Building.ipynb`: Trains and evaluates two models for predicting CO₂ emissions per capita and saves them as `.pkl` files.
- `forecasting_co2_emission_model.pkl`: Early model built for forecasting.
- `final_rf_model.pkl`: Final model based on Random Forest algorithm, optimized and ready for deployment.

---

## 🧹 1. Data Preparation

The dataset originates from an Excel workbook containing dozens of environmental and economic indicators from multiple countries. Steps in the preparation phase include:

- **Cleaning and Filtering**:
  - Removed rows where `SCALE` or `Decimals` was marked as `Text`.
  - Filtered out missing values like `..` or empty strings.

- **Feature Selection**:
  - Kept only numeric and meaningful features such as:
    - Cereal yield
    - Foreign direct investment
    - Energy use (per capita and per GDP)
    - Urban population statistics
    - CO₂ and other GHG emissions
    - GNI and GDP
    - Protected land percentage

- **Reshaping**:
  - Converted the data into a pivoted format with countries and years as a multi-index for easier feature aggregation and selection.

---

## 📊 2. Data Exploration

Using the cleaned data, the notebook performs:

- **Descriptive Analysis**:
  - Summary statistics to understand the range and distribution of values.

- **Visualization**:
  - Correlation heatmaps to show relationships between indicators and CO₂ per capita.
  - Line and bar plots to analyze trends over time or between countries.

- **Outlier Detection**:
  - Identified countries like Qatar or Kuwait with exceptionally high emissions.
  - These outliers were removed to prevent skewing model predictions.

---

## 🧠 3. Model Building

Two models were developed to estimate CO₂ emissions per capita.

### 🔸 A. Forecasting Model (`forecasting_co2_emission_model.pkl`)
- Built using selected features and a machine learning algorithm (likely Random Forest).
- Trained to give reasonably accurate forecasts across countries and years.
- Used for initial experimentation and evaluation.

### 🔸 B. Final Model (`final_rf_model.pkl`)
- Created using **Recursive Feature Elimination with Cross Validation (RFECV)** to identify the most important predictors.
- Trained using a **Random Forest Regressor** due to its robustness to outliers and high performance with non-linear data.
- Evaluated using:
  - R² score (coefficient of determination)
  - Prediction error comparisons
- Finalized and saved using Pickle for downstream applications or integration into APIs or dashboards.

---

## 🧾 Features Used in Modeling

| Feature Name                        | Description                                      |
|------------------------------------|--------------------------------------------------|
| `cereal_yield`                     | Agricultural productivity                        |
| `fdi_perc_gdp`                     | Foreign investments                              |
| `en_per_cap`                       | Energy use per person                            |
| `co2_per_cap`                      | CO₂ emissions per capita (target)                |
| `gni_per_cap`                      | Income level of citizens                         |
| `prot_area_perc`                   | % of land under environmental protection         |
| `pop_urb_aggl_perc`               | Urban concentration                              |
| `other_ghg_ttl`, `ch4_ttl`, `n2o_ttl` | Other greenhouse gases (methane, nitrous oxide) |

---

## 📁 Model Output

Both trained models (`.pkl`) can be loaded into any Python environment for inference on unseen country data.

Usage:
```python
import pickle
model = pickle.load(open('final_rf_model.pkl', 'rb'))
```

---

## 👤 Author

**Anwith Pulijala**  
GitHub: [@anwithpulijala](https://github.com/anwithpulijala)

---

## 📄 License

This project is released under the MIT License. Free to use with proper attribution.

