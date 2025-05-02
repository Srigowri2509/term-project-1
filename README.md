# term-project-1
SUMMARY
This work focuses on forecasting tomorrow's closing value of the KOSPI index through machine learning regression models. This problem has been framed as a time series forecasting task with our employing the past history of KOSPI values (2019–2022) for model training and model evaluation against 2023. Part 1 employed lag features: yesterday's Open, Low, High, Close, and Volume. In Part 2, we made predictions more robust by adding technical indicators, including 5-day and 10-day moving averages and the Relative Strength Index (RSI). The models we experimented with included Linear Regression, Ridge Regression, Lasso Regression, and Decision Tree Regressors. We applied cross-validation on the training set and evaluated performance based on RMSE and R² on the test set. Results showed that adding extra predictors improved model accuracy, especially for linear and regularized models. Our best-performing model's performance was Linear Regression with technical features, test RMSE = ~21.34 and R² = ~0.93. We conclude that technical features might significantly enhance forecasting stock indices. Potential future directions for research may include regularization of tree models, the addition of external economic metrics, or the addition of predicted vs. actual price charts for visual inspection.

INTRODUCTION
The KOSPI index is a benchmark of the Korean stock market, widely used by investors to assess market performance. Accurate prediction of its next-day close can support investment strategies and risk management. The objective of this project is to compare regression models for forecasting KOSPI’s next-day closing price and evaluate whether adding technical indicators improves predictive performance.

MODELS
Data sources:

Training: 2019–2022 KOSPI daily data

Test: 2023 KOSPI daily data

Preprocessing:

Converted date to datetime type

Created lag features (previous day’s Open, Low, High, Close, Volume)

Added technical indicators:

5-day moving average (Close_MA5)

10-day moving average (Close_MA10)

Relative Strength Index (RSI, window 14)

Models used:

Linear Regression

Ridge Regression (with cross-validated alpha)

Lasso Regression (with cross-validated alpha)

Decision Tree Regressor

Experimental setup:

TimeSeriesSplit cross-validation on training data

Evaluation metrics: RMSE and R² on the test set

Two experiments:

Part 1: Lag features only

Part 2: Lag features + technical indicators

DISCUSSION
The analysis shows that adding technical indicators improves the prediction accuracy of regression models. Linear Regression performed best in both parts, while Ridge and Lasso are expected to further improve stability and generalization. Decision trees offer nonlinear modeling capabilities but may require hyperparameter tuning. The improvements seen with technical indicators suggest that combining trend and momentum features with price data leads to better forecasts. Future extensions could include external macroeconomic indicators, hyperparameter optimization, and ensemble methods.

CONCLUSION
We applied machine learning regression models to forecast the next-day KOSPI close. The main findings are:

- Lagged price and volume data provide strong baseline predictions.

- Adding moving averages and RSI improves performance.

- Linear models, especially Linear Regression with technical indicators, deliver the best results.

Future work should explore parameter tuning, adding global market or economic indicators, and visualizing model predictions.

REFERENCES
- James, G., Witten, D., Hastie, T., Tibshirani, R. (2021). An Introduction to Statistical Learning with Applications in Python. Springer.

- Scikit-learn documentation. https://scikit-learn.org

- Investopedia. Technical Indicators (MA, RSI). https://www.investopedia.com
