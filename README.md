# stock-market_analysis
Analysing the relationship between US economy indicators and S&amp;P500


# Motivation
I wanted to understand why the stock market does not always move in the same direction as the economy. For example, even when economic conditions seem strong, stock prices may decline due to inflation or changes in interest rates. This made me curious about how different economic indicators interact with the stock market and whether they can help explain its movements.



# Initial finding
After looking at the correlation results, I found that the GDP had the strongest positive correlation with the S&P 500 with 0.968 and unemployment had a negative correlation with -0.625, while interest rates had a positive correlation with 0.608. CPI had a weaker positive correlation with 0.325.
I was surprised that interest rates and the S&P 500 had a positive correlation because I expected higher interest rates to make it harder for businesses to borrow money and could negatively affect stock prices. However, I'm aware that these results do not necessarily mean that one causes the other and I also need to look more closely at the relationship between GDP and the S&P 500 since they both tend to increase over time.


# Analysing using monthly S&P 500 Returns
After calculating monthly S&P 500 returns, I noticed that the correlation results were very different from the previous analysis. GDP had almost no correlation with monthly S&P 500 returns with 0.003, even though it had a very strong positive correlation with the S&P 500 index (0.968). This showed me that the relationship between economic indicators and the stock market can look very different depending on how stock performance is measured.


# Analysis using lagged economic indicators
I also looked at whether the previous month's economic indicators were related to the current month's S&P 500 returns. I used shift(1) to create lagged variables for CPI, unemployment, interest rates and GDP.

All the correlations were close to zero. GDP had the lowest correlation with 0.001, while unemployment had the highest with 0.151. I thought the results might be different when using the previous month's data, but there was not much change. 

So far I haven't found a strong relationship between these economic indicators and monthly S&P 500 returns.


# Model evaluation
I used Linear Regression to predict monthly S&P 500 returns based on the previous month's economic indicators.

The model had an MAE of 2.96 and an R-squared value of -0.214. I also compared it with a baseline model that always predicted the average return from the training data. The baseline model had a lower MAE of 2.85.

This shows that the Linear Regression model didn't perform better than the baseline model. I also noticed that the model had difficulty predicting months with large market changes, especially in 2022. For example, the actual return in May 2022 was -7.99%, but the model predicted 2.40%.

Overall, the economic indicators I used didn't provide enough information to accurately predict monthly S&P 500 returns.



# Decision tree dept comparison

I also tested different maximum tree depths (2,3, and 4). The model with a depth of 2 had the lowest MAE with 5.47, compared to 5.74 for depth 3 and 5.69 for depth 4.

I found that making the tree more complex did not improve its performance. All three versions also had higher MAEs than the baseline model.

# Main finding

Overall, I found that the relationships between economic indicators and the S&P 500 depended on how stock performance was measured. Although GDP had a strong correlation with the S&P 500 index, it had almost no correlation with monthly returns. The prediction models also did not perform better than the simple baseline model.

# Limitations

One limitation is that I only used about 170 months of data, which may not be enough to capture different market conditions.

I also only included four economic indicators: CPI, unemployment, interest rates, and GDP. Other factors, such as company performance and investor sentiment could also affect stock returns.

Another limitation is that GDP is reported quarterly so I had to convert it into monthly data by repeating each quarterly value for three months. This may not fully represent monthly economic changes.


# Future improvements

In the future, I'd like to try adding more variables, such as company earnings and market volatility. I'd also like to use more historical data and see whether other models perform better.
