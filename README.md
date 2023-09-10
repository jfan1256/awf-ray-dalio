### Introduction
Ray Dalio All Weather Portfolio's (AWP) main purpose is to perform well in any economic environment: inflation vs. deflation, economic growth vs. economic stagnation, or best of times vs. worst of times. To do this, AWP utilizes various trends to determine when to invest and how much to invest. For example, during periods of rising prices, gold and commodities tend to do well; during periods of falling prices, bonds tend to do well. The four main economic environments (inflation, deflation, rising growth, and falling growth) serve as the core ideas for which AWP follows while investing. 

The portfolio designed here implements the ideals proposed in AWP. Additionally, the base portfolio created only invests into Exchange-Traded Funds (ETF). By investing in only ETFs and combining AWP's ideals, the portfolio maintains a low volatility percentage while performing well in all four economic environments. To evaluate performance, the code compare the returns from my portfolio with the returns produced by S&P 500 with a start date of Janurary 1st, 2008 and end date of March 20, 2023.

### Code
Within the code there are four main functions that capture the trends which AWP aim to follow:

#### _Early Month Weights_
Studies have shown that stocks tend to perform better during the start of each month in a given year. To account for this, the code determines whether a given date is within the first week of a month. If so, the weights of the portfolio are adjusted to increase for stocks and decrease for bonds accordingly.

#### _Halloween Weights_
Studies have shown that stocks tend to perform better during the period of October 1st to May 1st (The Halloween Strategy). To account for this, the code determines whether a given date is  within this period. If so, the weights of the portfolio are adjusted to increase for stocks and decrease for bonds accordingly.

#### _MacroFactor Model_
To reduce drawdown periods, a MacroFactor Model has been implemented. Through calculating the Pearson Correlation Coefficient and Kendall Rank Correlation Coefficient, the code recognizes that Consumer Price Index (CPI), Gross Domestic Product (GDP), Unemployment Rate (UE), and Trade Balance (TB) are strongly correlated with the performance in S&P 500 Index. To determine dates of deflation and falling growth, function _trendChange_ detects drastic changes in trend in all four Macroeconomic Indicators. From here, the weights are adjusted so that bonds are heavily invested in. Each drawdown period is estimated as 60 days long. 

#### _Oil Weights_
Studies have shown that Oil tends to perform well during summer months and less during winter months. This is due to the fact that people tend to travel more during summer, which means demand for oil is higher. To account for this, the base portfolio invests in a small percentage of oil during summer months.

## Goal
Currently the cumulative return for the base portoflio is 103.39% while the cumulative return for S&P 500 is 169.09%. The end goal is to match the S&P 500 returns while maintaing a lower volatilty percentage and a lower drawdown period percentage. To do this, try adjusting the weights and investing in more ETFs to increase diversification and returns.
