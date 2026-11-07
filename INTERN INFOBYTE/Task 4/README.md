# Task-4: Car Price Prediction Project

Predict the selling price of a used car from historical listing data (Python · Pandas · Scikit-Learn · Jupyter Notebook).

## Objective
Develop a regression model that predicts used-car prices to help buyers judge whether an asking price is fair and sellers set a competitive price.

## Datasets
| File | Rows | Used for |
|---|---|---|
| `Car_details_v3.csv` | 8,128 | **Primary dataset** (year, km, fuel, seller, transmission, owner, mileage, engine, power, seats) |
| `CAR_DETAILS_FROM_CAR_DEKHO.csv` | 4,340 | Secondary check (fewer features) |
| `car_data.csv` | 301 | Secondary check (has `Present_Price`) |

Source: Kaggle "Automobile Dataset" / CarDekho used-car data.

## Steps followed
1. **Data cleaning & preprocessing** – removed 1,202 duplicate rows, converted `mileage`/`engine`/`max_power` from text to numbers, extracted `brand`, created `age`, removed 3 impossible odometer readings, imputed missing values inside a scikit-learn pipeline, one-hot encoded categoricals, scaled numerics.
2. **Exploratory data analysis** – price distribution (log transform), price vs fuel/transmission/seller/owner, brand analysis, depreciation curve, correlation heatmap.
3. **Model training & evaluation** – Linear, Ridge, Lasso, Decision Tree, Random Forest, Gradient Boosting; 5-fold cross-validation; randomized hyper-parameter search; test-set evaluation; residual analysis; feature importance.
4. **Outcome** – saved model + `predict_price()` helper.

## Results (test set, Car_details_v3, 80/20 split)
| Model | R² (₹) | MAE (₹) |
|---|---|---|
| Linear Regression (baseline) | 0.859 | ≈ 97,900 |
| Tuned Random Forest | 0.913 | ≈ 76,700 |
| **Tuned Gradient Boosting (final)** | **0.924** | ≈ 77,600 |

Median absolute error ≈ 12.5 %; ≈ 70 % of predictions fall within ±20 % of the actual price. Most important features: car **age** and engine **power**, then engine size and brand.

## How to run
```bash
pip install pandas numpy scikit-learn matplotlib seaborn joblib jupyter
jupyter notebook Car_Price_Prediction.ipynb
```
Keep the three CSV files in the same folder as the notebook (or in a `data/` folder).

## Repository layout (suggested, inside your `INIB` repo)
```
INIB/
└── Task-4-Car-Price-Prediction/
    ├── Car_Price_Prediction.ipynb
    ├── README.md
    ├── data/  (3 CSV files)
    └── outputs/car_price_model.joblib
```

## Limitations & future work
No car variant/trim, location or condition in the data; weaker on rare luxury/very old cars. Next steps: add variant features, parse `torque`, try XGBoost/LightGBM, deploy with Streamlit.
