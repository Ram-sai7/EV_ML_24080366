# EV_ML_24080366
Predicting EV Charging Demand Using Machine Learning
This project applies machine learning to predict electric vehicle (EV) charging demand — specifically the energy delivered (kWh) per charging session. As EV adoption grows globally, accurate demand forecasting becomes essential for grid stability, energy management, and infrastructure planning. Three models are evaluated and compared across two experimental conditions to understand what drives predictive accuracy in this domain.

What This Project Does

Trains and evaluates Linear Regression, Random Forest, and XGBoost on a synthetic EV charging dataset of ~1.97 million records
Compares model performance with and without engineered temporal features (hour of day, weekday indicator, peak hour flag)
Applies GridSearchCV hyperparameter tuning to all three models
Evaluates everything using MAE, RMSE, and R²


Dataset
Synthetic EV charging dataset from Mendeley Data — fully anonymised, no personal data.
ColumnDescriptionconnectionTime_decimalHour of connection (decimal format)chargingDurationSession length in hourskWhDeliveredEnergy delivered — target variabledayIndicatorDay index used to derive temporal features
~1.97M records · No missing values · 200k sampled for training

Methodology

Exploratory Data Analysis (distributions, correlations, scatter plots)
Data preprocessing — sampling, missing value check
Feature engineering — hour, weekday, peakHour derived from connection time
80/20 train-test split
Two experiments: with and without temporal features
Baseline training → GridSearchCV tuning
Model comparison across all 12 trained models


Results Summary
ModelR² (Baseline)R² (Tuned)Linear Regression0.2840.284Random Forest0.3120.410XGBoost0.4090.411

XGBoost and Random Forest substantially outperform Linear Regression
Hyperparameter tuning improved Random Forest the most (+0.098 R²)
Temporal features had minimal impact — charging duration dominates as a predictor


How to Run
bashpip install numpy pandas matplotlib seaborn scikit-learn xgboost
jupyter notebook Untitled7.ipynb
Or open directly in Google Colab:
Show Image

Libraries
pandas · numpy · matplotlib · seaborn · scikit-learn · xgboost

Future Work

Test on real-world EV charging datasets
Add richer features (weather, vehicle type, station location)
Explore LSTM / deep learning for sequential demand forecasting
Apply SHAP for model interpretability


References

Shahriar et al. (2021). Prediction of EV Charging Behavior Using Machine Learning. IEEE Access.
Shahriar et al. (2020). ML Approaches for EV Charging Behavior: A Review. IEEE Access.
Bharathi et al. (2025). Prediction of EV Charging Behaviour Using Data-Driven Methodology. IEEE.
S, A.D., et al. (2024). Predictive Management of EV Charging Stations Using ML. IEEE.
Chen & Guestrin (2016). XGBoost: A Scalable Tree Boosting System. KDD '16.
Pedregosa et al. (2011). Scikit-learn: Machine Learning in Python. JMLR, 12, 2825–2830.
