# Mean-Variance-Optimization
The script calculates S&P500 excess returns and on the basis of a coefficient of risk aversion allocates capital between S&P500 and bonds.

Code Breakdown:

This script performs an analysis of financial data for the S&P 500, as well as certain bond market data. Here is a breakdown of what it does:

Imports necessary libraries and sets working directory: The script begins by importing the necessary Python libraries (pandas, numpy, matplotlib, statsmodels, warnings, and datetime). It then sets the current working directory to the specified path using os.chdir().

Defines the Nelson-Siegel-Svensson function: This function calculates the yield of a Zero-Coupon Bond (ZCB) given certain parameters.

Reads and preprocesses data: The script reads S&P 500 data and yield curve data (assumed to be in Nelson-Siegel-Svensson parameters format), filters them based on date ranges, merges them, and performs several preprocessing steps to prepare the data for analysis.

Calculates returns: It then calculates returns at different intervals (daily, monthly, yearly, and every 5 years) for the S&P 500.

Calculates excess returns: Excess returns are calculated as the difference between the S&P 500 returns and the risk-free rate, which is estimated based on the yield of a Zero-Coupon Bond (ZCB).

Builds a results dataframe: Finally, the script calculates the arithmetic and geometric means of both the S&P 500 returns and the excess returns for each time horizon (daily, monthly, yearly, and 5-year). These results are then stored in a pandas DataFrame, converted to percentages, and printed to the console.

In summary, the script is performing an analysis of the historical returns of the S&P 500 index and comparing them to the returns of a risk-free asset, i.e., a Zero-Coupon Bond (ZCB). This type of analysis can be useful in various financial and economic studies.

After that code calculates and prints the optimal weights of the S&P 500 and Bonds in a portfolio for different time periods (Daily, Monthly, Annual, 5-year). It does this by employing the concept of Mean-Variance Optimization in portfolio theory, which under certain assumptions gives the weights of assets in the portfolio that minimize the variance (risk) for a given expected return. Here, risk aversion coefficient A is used, which reflects the investor's willingness to accept risk.

The steps are as follows:

Initialize a new DataFrame res3 with the same index as the previously created res DataFrame, and two columns ("w: SP500" and "w: Bonds"), filled with zeros.

Define a risk aversion parameter A with value 4.

Define a function wsp500(), which takes in excess returns xret of the S&P 500, and returns the optimal weight for S&P 500 in the portfolio. This weight is calculated as the ratio of the mean of excess returns to four times the variance of excess returns. This formula is derived from the Mean-Variance Optimization in portfolio theory.

Call wsp500() with the excess returns of the S&P 500 for different time periods, and assign the results to the corresponding cells in the "w: SP500" column of the res3 DataFrame.

Calculate the weights for Bonds in the portfolio by subtracting the weights of S&P 500 from 1. This assumes a portfolio composed only of these two assets, with total weights summing to 1.

Multiply all the values in res3 by 100 (likely to convert the weights from proportions to percentages), store the result in res3_100, and then print res3_100.

The output will be a table showing the portfolio weights of the S&P 500 and Bonds in percentages for different time periods, calculated using Mean-Variance Optimization.
