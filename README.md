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
I also checked the relationship between the previous month's economic indicators and the current month's S&P 500 returns. I used shift(1) to create lagged variables for CPI, unemployment, interest rates and GDP.

The correlations were all close to zero. GDP had the lowest correlation with 0.001, while unemployment had the highest with 0.151. I thought the results might be different when using the previous month's data, but there was not much change. 

So far I haven't found a strong relationship between these economic indicators and monthly S&P 500 returns.

