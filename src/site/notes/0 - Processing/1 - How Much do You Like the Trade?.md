---
{"dg-publish":true,"permalink":"/0-processing/1-how-much-do-you-like-the-trade/"}
---


Prev Article: [[2 - General Archive/Designing Quantitative Trading Systems\|Designing Quantitative Trading Systems]]

# How Much do You Like the Trade?
##### Strategies and Forecasts
To quantify how much you like a trade, you need some rules that determine some measure by which you like the trade at every point in time. We call these rules **Strategies** and we call said measure **Forecasts**.

For example, consider a simple technical indicator-based trend-following strategy.
- Buy rule: Buy when 30-day EMA crosses 250-day EMA.
- Sell rule: Sell when 250-day EMA crosses 30-day EMA.
In this case, the forecast is a simple binary forecast of (1, -1).

The trading rule reflects your belief on the trade at any given point in time, and the forecast is the measure that quantifies it. With a forecast of 1, we quantify our belief for buying, and with a forecast of -1, we quantify our belief for selling.

##### Topics
- [[0 - Processing/1.1 - Quantitative Strategy Types\|1.1 - Quantitative Strategy Types]] - We cover the two main types of strategies in quantitative trading.
- [[0 - Processing/1.2 - Searching for Strategies\|1.2 - Searching for Strategies]] - We cover how to search and select strategies.
- [[0 - Processing/1.3 - Backtesting\|1.3 - Backtesting]] - Is an extension of 1.2, where we explore methods of backtesting.
- [[0 - Processing/1.4 - Fitting and Quantifying Forecasts\|1.4 - Fitting and Quantifying Forecasts]] - We cover how to fit our strategy, and quantify forecasts acquired from our strategy

---

Next Article: [[0 - Processing/1.1 - Quantitative Strategy Types\|1.1 - Quantitative Strategy Types]]
