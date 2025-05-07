# Weather Severity Classification

## Project Overview

The primary objective of this project is to develop a classification model using weather data to predict the **severity of weather**. The model classifies weather into three categories — **Severe**, **Mild**, or **Normal** — based on various meteorological parameters such as temperature, humidity, wind speed, and visibility.

---

## Libraries and Dependencies

The project utilizes the following Python libraries:

- **pandas**: For data manipulation and analysis  
- **numpy**: For numerical computations  
- **matplotlib**: For data visualization  
- **seaborn**: For statistical data visualization  
- **scikit-learn**: For machine learning and model evaluation  
- **pickle**: For saving and loading trained models and preprocessing tools

> You can install all dependencies using:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

---

## Files in the Project

| File Name                 | Description |
|--------------------------|-------------|
| `extreme_weather_model.pkl` | Trained Random Forest model for predicting weather severity |
| `label_encoder.pkl`      | Label encoder used for encoding severity labels (`Severe`, `Mild`, `Normal`) |
| `scaler.pkl`             | StandardScaler used for normalizing features |
| `weatherHistory.csv`     | Dataset containing historical weather data |

---

## Data Preprocessing

The dataset goes through a comprehensive preprocessing pipeline:

- **Irrelevant Column Removal**: Columns such as `Loud Cover` and `Daily Summary` are dropped.
- **Missing Value Handling**: Rows with missing values are removed.
- **Feature Engineering**:
  - Convert `Formatted Date` to datetime format
  - Extract `Month` and `Hour` features
- **Severity Labeling**: Weather summaries are categorized into:
  - `Severe`
  - `Mild`
  - `Normal`
- **Categorical Encoding**: Columns like `Precip Type` are encoded to numerical values for compatibility with machine learning models.

---

## Model Training

A **Random Forest Classifier** is used for training. It is an ensemble algorithm that combines multiple decision trees to:

- Improve predictive performance
- Reduce overfitting

Features such as temperature, humidity, wind speed, and visibility are used for training. The model is split into training and testing sets to evaluate performance.

---

## Model Evaluation

The model is evaluated using:

- **Accuracy**
- **Precision**
- **Recall**
- **F1-score**
- **Confusion Matrix**: To visualize the classification performance across severity classes

---

## Model Export

After training and evaluation, the model and its components are saved using `pickle`:

- `extreme_weather_model.pkl`: Trained model
- `label_encoder.pkl`: For consistent label transformation
- `scaler.pkl`: For consistent feature scaling on new data

These files ensure the model can be reused without retraining.

---

