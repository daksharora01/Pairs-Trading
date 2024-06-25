# Pairs Trading Strategy Overview
Pairs trading is a market-neutral trading strategy that involves identifying two co-movable stocks and taking opposite positions in them to capitalize on temporary deviations from their historical pricing patterns. This strategy is based on the law of mean reversion, which suggests that the prices will eventually revert to their historical mean, allowing the trader to profit from this convergence.

Strategy Components
Pair Selection: The first step in pairs trading is to find two stocks that exhibit a high degree of correlation and co-movement. This typically involves statistical tests such as correlation coefficients and cointegration tests.

Signal Generation: Once a pair is identified, traders monitor the spread between the prices of the two stocks. The "spread" is the difference in price between the two stocks adjusted for certain factors like volatility.

Trade Execution: Trades are executed when the spread widens beyond a pre-determined threshold. If the spread is exceptionally high or low, it indicates that one stock is overpriced relative to the other. The trader would then short the overpriced stock and go long on the underpriced one.

Risk Management: Proper risk management techniques are employed to ensure that potential losses are kept within acceptable limits. This includes setting stop-loss orders and limiting the size of positions.

Exit Strategy: The positions are closed when the spread narrows down again, or based on specific profit targets or time frames.

# Augmented Dickey Fuller Test
Augmented Dickey Fuller test (ADF Test) is a common statistical test used to test whether a given Time series is stationary or not. It is one of the most commonly used statistical test when it comes to analyzing the stationary of a series.
ADF serves the purpose of finding out which stocks can be paired together in the pairs trading strategy. For the strategy to work effectively, it is important to find the pair of stocks that are co-integrated.
If there is a unit root present in the time series, it implies that the time series is non-stationary and the stocks are not co-integrated. Hence, stocks cannot be traded together.
Alternatively, if the null hypothesis gets rejected and the stocks show co-integration; it implies that the time series is stationary and the stocks can be traded.
For the pair of stocks to be traded in the pairs trading strategy, it is required that the time series is stationary. A stationary time series makes effective and precise predictions.
Also, a stationary time series means that the pair of stocks is co-integrated and can be traded together by generating trading signals.

# ADF Test implementation in python
Using the statsmodels.api library, we compute the Ordinary Least Squared regression on the closing price of the commodity pair and store the result of the regression in a variable.
Using the statsmodels.tsa.stattools library, we run the adfuller test by passing the residual of the regression as the input and store the result of this computation in an array. This array contains values like the t-statistic, p-value, and critical value parameters. 
