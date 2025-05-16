# 592finalproject

# Weekly Retail Sales Forecasting (ISU CS 592 Final Project)

This repository contains code and data for a two‐stage hybrid forecasting pipeline that combines classical time-series decomposition (SARIMA) with modern gradient-boosted trees (LightGBM & XGBoost) to predict weekly Walmart store sales.  

---

## 📂 Repository Structure

.
├── data/
│ ├── train.csv # Historical store–dept daily sales (2010–2012)
│ ├── features.csv # Exogenous drivers: temperature, fuel price, CPI, unemployment, holiday flags
│ ├── stores.csv # Store metadata: type, size
│ └── test.csv # Hold-out set for final submission
│
├── notebooks/
│ └── neural_networks.ipynb # (Optional) Neural-network experiments on the same data
│
├── submissions/
│ ├── submission_lightgbm.csv # LightGBM-only forecast
│ ├── submission_xgboost.csv # XGBoost-only forecast
│ └── submission_ensemble.csv # Blended SARIMA+LightGBM+XGBoost forecast
│
├── README.md # You are here
└── requirements.txt # Python dependencies

yaml


---

## 🚀 Quickstart

1. **Clone the repo**

   ```bash
   git clone https://github.com/tharani247/592finalproject.git
   cd 592finalproject
Create & activate a Python 3.10 environment


conda create -n retail_forecast python=3.10
conda activate retail_forecast
pip install -r requirements.txt
Run the end-to-end pipeline (optional: via Jupyter or Python scripts):

Data prep & feature engineering
See 01_data_prep.py & 04_features.py for merging, cleaning, encoding, and residual feature creation.

Exploratory analysis
Inspect 02_eda.ipynb or equivalent scripts for time-series plots, ACF/PACF, heatmaps.

SARIMA modeling
Fit & forecast with SARIMA in 03_sarima_model.py.

Residual modeling
Train LightGBM/XGBoost via 05_train_gbts.py (with time-series cross-validation).

Hyperparameter tuning
Launch Optuna search in 06_tune_optuna.py.

Ensembling & submission
Blend forecasts and export final CSV using 07_ensemble.py.

Inspect submissions
The .csv files in submissions/ follow Kaggle’s “Id, Weekly_Sales” format.

🛠️ Requirements
All dependencies are pinned in requirements.txt. Key libraries include:

pandas >=2.2

numpy >=1.24

scikit-learn >=1.2

statsmodels >=0.14

lightgbm >=4.6

xgboost >=3.0

optuna >=3.1

matplotlib, seaborn

Install via:


pip install -r requirements.txt
📈 Results
Hybrid SARIMA + LightGBM

Validation (10 % hold-out):

RMSE = 4 671.35

MAE = 2 815.58

MAPE = 12.4 %

Test (12 weeks hold-out): 43 % error reduction vs. SARIMA alone, 22 % vs. pure LightGBM.

Benchmarks:

SARIMA: RMSE = 8 234.00

Pure LightGBM: RMSE = 5 959.00

XGBoost: RMSE ≈ 4 834.00

Ensemble: RMSE ≈ 4 671.00

📚 References
Please see our paper (IEEE format) for full citations. Key works include:

Box et al., “Time Series Analysis: Forecasting and Control,” Wiley, 2015.

Zhang, “Time series forecasting using a hybrid ARIMA and neural network model,” Neurocomputing (2003).

Chen & Guestrin, “XGBoost: A scalable tree boosting system,” KDD 2016.

Ke et al., “LightGBM: A highly efficient gradient boosting decision tree,” NeurIPS 2017.

Akiba et al., “Optuna: A next‐generation hyperparameter optimization framework,” 2019.

🤝 Contact
Tharani Vadde tvadde@iastate.edu
Navyatha Gandlaparthi ngandlap@iastate.edu

Iowa State University, Ames, IA, USA
Course: CS 592 – Advanced Machine Learning (Spring 2025)








