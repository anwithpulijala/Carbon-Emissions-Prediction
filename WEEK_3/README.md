
# 🌍 CO₂ Emissions Prediction using Machine Learning

This project focuses on predicting **carbon dioxide (CO₂) emissions per capita** using a range of country-level indicators such as energy consumption, population growth, foreign investments, and urbanization. The notebook uses machine learning to train and evaluate a predictive model, which is then saved for future forecasting.

---

## 🎯 Objective

To build a machine learning model that can predict the CO₂ emissions per person based on various socioeconomic and environmental features. The project supports decision-making in sustainability, environmental policy, and global emissions tracking.

---

## 📂 Project Structure

- **`Model_Building.ipynb`**: The core notebook that performs data loading, preprocessing, feature selection, model training, evaluation, and saving.
- **`forecasting_co2_emission_model.pkl`**: A trained model (most likely Random Forest) used for forecasting emissions.
- **`final_rf_model.pkl`**: The finalized Random Forest model selected after evaluation and tuning, ready for deployment or integration.

---

## 🧾 Data Description

The dataset used contains country-level statistics, including:

- Cereal yield
- Foreign direct investment (% of GDP)
- Gross national income per capita
- Energy use per capita
- Urban population growth and density
- Protected land areas
- CO₂ emissions per capita (target)

The dataset was cleaned to remove outliers (e.g., countries with extreme values) before being used to train the model.

---

## 🧠 Model Building Process

The notebook follows a standard machine learning workflow:

1. **Data Preparation**: Loads cleaned data and selects relevant features.
2. **Feature Selection**: Uses a method called Recursive Feature Elimination with Cross-Validation (RFECV) to identify the most important predictors of CO₂ emissions.
3. **Model Training**: Trains a **Random Forest Regressor**, which is well-suited for handling non-linear relationships and variable interactions.
4. **Model Evaluation**: Assesses performance using metrics such as R² score and error rates to ensure model accuracy.
5. **Model Saving**: Stores the trained models as `.pkl` files for reuse without retraining.

---

## 🔍 Models Used

### 1. Final Random Forest Model (`final_rf_model.pkl`)
This is the best-performing model trained using the most relevant features and tuned hyperparameters. It was selected based on performance metrics and saved for production use.

### 2. Forecasting Model (`forecasting_co2_emission_model.pkl`)
This is an earlier version of the trained model, possibly used for experimentation or preliminary forecasts. It may differ slightly in the training configuration or features used.

Both models are serialized with Python's `pickle` library and can be easily reloaded for making predictions on new data.

---

## ✅ Highlights

- Uses advanced feature selection to improve model performance.
- Handles outliers by cleaning the dataset before modeling.
- Applies a powerful ensemble method (Random Forest) for robust predictions.
- Enables real-world deployment through saved model files.

---

## 👤 Author

**Anwith Pulijala**  
GitHub: [@anwithpulijala](https://github.com/anwithpulijala)

---

## 📄 License

This project is released under the MIT License. You are free to use, modify, and distribute it with attribution.
