


# ⚽ Football Player Injury Duration Prediction

This repository contains a Machine Learning project designed to predict the number of days a professional football player will be sidelined due to injury.

## 📌 Project Overview

The objective is to provide medical and coaching staffs with a reliable estimate of recovery times based on data available at the **moment of injury**. This allows for better squad planning and injury management.

## 🧠 The "Data Leakage" Breakthrough

The most critical phase of this project was identifying **Data Leakage**.

* **Initial Results:** The model achieved an unrealistic 90% accuracy using the `Games missed` feature.
* **The Problem:** `Games missed` is a result of the injury duration, not a predictor available at the start. Using it makes the model useless for real-world predictions.
* **The Solution:** I refactored the pipeline to remove all post-injury features, resulting in a **truthful and robust** model that relies on pre-injury metrics like age, position, and injury type.

## 🛠️ Tech Stack

* **Language:** Python
* **Data Handling:** Pandas, NumPy
* **Machine Learning:** Scikit-learn, XGBoost
* **Visualization:** Matplotlib, Seaborn

## 📊 Model Performance

After addressing the data leakage, the models were evaluated using **Mean Absolute Error (MAE)** and **R-Squared ()**:

| Model | MAE (Lower is better) | R2 Score (Higher is better) |
| --- | --- | --- |
| Linear Regression | 25.40 Days | 0.220 |
| Random Forest Regressor | 24.10 Days | 0.280 |
| **XGBoost Regressor (Best)** | **23.18 Days** | **0.306** |

## 🔍 Key Insights (Feature Importance)

By analyzing the XGBoost model, we identified the primary drivers of injury duration:

1. **Injury Type:** The most significant predictor (e.g., ligament tears vs. muscle strains).
2. **Player Age:** There is a clear correlation between increased age and longer recovery times.
3. **League/Intensity:** The competitive environment also influences return-to-play protocols.

---

## 🚀 Getting Started

1. Clone the repository.
2. Ensure you have the dataset `full_dataset_thesis - 1.csv` in the root folder.
3. Install dependencies:
```bash
pip install pandas scikit-learn xgboost matplotlib

```


4. Run the Jupyter Notebook `task.ipynb` to reproduce the analysis.

