# Farma-French-3-Factor-Markowitz-Portfolio-Optimization
This project combines the usage of the Farma French three factor model to calculate expected returns and Markowitz portfolio optimization to use the calculated expected returns to calculate the optimal portfolio.

Project Goal: This project aims to analyze stock returns, predict expected returns using the Fama-French three-factor model, compare these predictions with actual returns, and finally, optimize a portfolio using Markowitz portfolio optimization.

Steps:

Data Acquisition:

Historical stock price data is fetched using yfinance for a set of specified stocks (AAPL, MSFT, GOOGL, AMZN, TSLA, NVDA, JPM, GS) over a defined time period (2014-01-01 to 2018-01-01).
Fama-French three-factor data is loaded from a CSV file ('F-F_Research_Data_Factors_daily.CSV').
Data Processing:

Daily stock returns are calculated.
Data is aligned by ensuring both stock returns and Fama-French factors share the same dates.
Excess returns for each stock are calculated by subtracting the risk-free rate (RF) from the stock returns.
Regression Analysis (Fama-French Model):

For each stock:
A linear regression model is fitted using statsmodels.api with excess return as the dependent variable and the three Fama-French factors (Mkt-RF, SMB, HML) as independent variables.
The regression coefficients (betas) are stored for later use in calculating expected returns.
Comparison of Actual vs. Predicted Returns:

Expected returns are calculated using the estimated betas and the Fama-French factor values.
Graphs are generated using matplotlib.pyplot to visually compare the actual and predicted excess returns for each stock.
Markowitz Portfolio Optimization:

cvxopt is used to perform quadratic programming for portfolio optimization.
The efficient frontier is calculated by varying target returns and minimizing portfolio risk (variance).
Optimal portfolio weights are determined for a specific target return (0.0075 in this case).
The efficient frontier is plotted, along with random portfolios to illustrate the feasible region.
The market portfolio (with the highest Sharpe ratio) is highlighted.

In essence, the project combines the Fama-French model with Markowitz optimization to analyze and predict stock returns, evaluate model performance, and determine an optimal portfolio allocation.
