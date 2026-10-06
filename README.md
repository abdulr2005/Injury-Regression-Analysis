# ⚽ Football Player Injury Duration Prediction

An end-to-end **machine learning regression project** that estimates how long a professional football player may be sidelined after an injury using information available at the time of injury.

## 🎯 Project Goal

The project explores whether injury duration can be estimated from pre-injury and injury-time information such as player age, position, injury type, and competitive context.

A major focus of the work is **preventing data leakage** so that model evaluation reflects a realistic prediction scenario.

## 🧠 Data Leakage: The Key ML Lesson

An early model produced unrealistically strong results because it included `Games missed`.

That feature is only known after an injury has already affected the player, so using it to predict recovery duration leaks information from the future into the model.

The pipeline was therefore rebuilt without post-injury information. This reduced the headline score, but produced a more honest and useful evaluation.

## 🛠️ Tech Stack

- Python
- Pandas & NumPy
- Scikit-learn
- XGBoost
- Matplotlib & Seaborn
- Jupyter Notebook

## 🤖 Models Compared

| Model | MAE ↓ | R² ↑ |
| --- | ---: | ---: |
| Linear Regression | 25.40 days | 0.220 |
| Random Forest Regressor | 24.10 days | 0.280 |
| **XGBoost Regressor** | **23.18 days** | **0.306** |

Among the evaluated models, **XGBoost achieved the strongest result**, with the lowest MAE and highest R².

## 🔍 Model Insights

Feature-importance analysis highlighted several useful signals:

- **Injury Type** — the strongest predictor in the model.
- **Player Age** — associated with differences in expected recovery time.
- **League / Competitive Context** — contributed additional predictive information.

These relationships are model-derived patterns from the project dataset and should not be interpreted as medical conclusions.

## 🚀 Run the Project

1. Clone the repository.
2. Keep `full_dataset_thesis - 1.csv` in the repository root.
3. Install the main dependencies:

```bash
pip install pandas numpy scikit-learn xgboost matplotlib seaborn jupyter
```

4. Open and run `task.ipynb`.

## 📌 Takeaway

This project demonstrates an important ML engineering principle: **a lower but trustworthy score is more valuable than an impressive score produced by leaked information**.
