# Regional Electricity Consumption Prediction
**SAS Data Analytics Competition 2025**

> Predicting regional electricity usage (TOTAL_ELEC) using gas consumption patterns,
> facility distribution, and spatio-temporal features.
> **Achieved 14th place** out of ~500 teams.

---

## Problem Overview
Predict monthly electricity consumption by region using infrastructure and
gas usage data across Korean administrative districts.

- **Target variable**: `TOTAL_ELEC` (regional electricity consumption)
- **Data**: ~26,000 training samples with 20 features

---

## Approach

### Feature Engineering
| Feature | Description |
|---|---|
| `CMRC_GAS_RATIO` | Commercial gas ratio (commercial / total gas) |
| `AVG_GAS_PER_BUILDING` | Average gas consumption per building |
| `FAC1/2_PER_BUILDING` | Facility density per building |
| `MONTH_SIN/COS` | Cyclical encoding of month |

### Model
- **XGBoost + LightGBM Ensemble** (VotingRegressor, weights 0.6 / 0.4)
- Hyperparameter tuning via **Optuna** (50 trials each)
- Validation: **5-Fold Cross Validation**

---

## Results
| Model | CV RMSE |
|---|---|
| XGBoost | ~327 |
| LightGBM | ~333 |
| **Ensemble** | **~325** |

---

## 🛠️ Stack
`Python` `XGBoost` `LightGBM` `Optuna` `scikit-learn` `pandas`


