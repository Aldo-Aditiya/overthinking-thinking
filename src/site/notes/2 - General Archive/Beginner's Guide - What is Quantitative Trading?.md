---
{"dg-publish":true,"permalink":"/2-general-archive/beginner-s-guide-what-is-quantitative-trading/"}
---


### What is Quantitative Trading?
#### What it is vs What it's Not
##### What it's not:
- Magically knowing where the market is going to go.
- Magically finding patterns in the market.
- Magically improving profits while reducing risk.
- Magically generate the trading signal for you.
- Doing the market analysis for you

##### What it is:
- Using past data (and more) in the hopes that the same patterns that happen within the past data will happen again in the future.
	- Note: We don't know where the market is going to go, we just hope the same patterns happen again. Just need to find those patterns.
- We have to construct our own hypothesis about patterns, and then falsify if those hypothesis are incorrect by using quant methods. (i.e. statistics, mostly)
	- Note: You can actually use statistics paired with data mining, but this is frowned upon because of multiple comparisons bias (which will be your arch nemesis in quant trading)
- Quantifying the risk you are going to take, and balancing it with profit target that you want to achieve. Higher profit targets necessarily means more risk.
- Trading signals are based on a trading strategy that you **designed** and **optimized**, not a black-box learned strategy. 
	- Note: a lot of quants are iffy about using ML because overfitting and black box nature (overfitting will be your other arch nemesis).
- Since you have to make your own hypothesis, you have to know how to analyze markets in the first place.

##### Conclusion
**Main takeaway:** You can't use Quantitative Trading by itself to make money. You need to understand how to analyze markets first, then use Quantitative Trading to assist you in finding statistical-provably good strategies.

**Main Goal**: To find a trading strategy that you think is good enough to trade with.

Note: This writing focuses on non-derivative trading. 
Derivative trading are more involved and requires advanced math methods (stochastic calculus, stochastic process, etc.). (Derivatives are also not halal, I dont think.)

#### What Makes a Good Trading Strategy
##### Wait, What is a Trading Strategy?
Trading Strategy: Some method that translates some data to a set of buy and sell choices in the market.

e.g. you might use bollinger bands on price data to set when you buy and when you sell. Or you might use stock fundamentals and stop losses to know when to buy and sell.

##### Criteria
Criteria are:
- Has been backtested on a large enough distirbution to make the metrics statistically significant (e.g. on long enough time, or tested on multiple financial instruments)
- Achieves good metrics
- Avoiding the biases within testing and development. (most specifically backtesting, data prep, and optimization)
- Does good on paper trade, and actual trade.

As a general rule, you wont' be 100% sure of any strategy's real performance unless you actually trade it on real data. Backtesting is useful to filter out obviously bad strategies.

##### Main Metrics
% Returns
- Price change in percentage. Can be calculated over whatever period we want (daily, annual, etc.)

Cumulative Returns
- Cumulated returns over certain period (usually monthly or annually).
- e.g. if in 2 days you get 5% returns each, then cumulative returns is 10.25%.

Volatility
- Standard deviation from the mean of prices.
- Is the main notion of "Risk" 

Sharpe Ratio
- Risk adjusted returns (or, returns/volatility)
- Usually the mainly used metric, because investors usually seek the highest amount of returns for the lowest amount of risk. Very useful for leverage if you are into that thing.

Drawdown and Drawdown Length
- The maximum % that the capital decreases over the testing period.
- Length is how long the capital stays underwater.

![Pasted image 20221020010809.png](data:image/png;base64,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)
![Pasted image 20221020010815.png](data:image/png;base64,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mHz45moTgdJMh9psW+a01on45ptvuk6dOhWsJhEy6YTbtWvnrTAsPXOlIQBuwg+/d+/e7vzzz/f7xtmqCKm+8cYbbs6cOb5A9pPfdNNNrmPHju5vf/ube++99xx4n3322W7SpEnuhRde8LtxIM233nrL/eEPf3AjR450p59+urdmr776avfvf//bYYGPGjXKE+oDDzzgvvCFL/g+fPjhh93mzZt9mPSJEycWtkGi6yuvvOKQwTFx3HjjjT7MP0iVbZqzZ892V111lS9n1qxZnni5UXz99df7yWH69Onu5ptvdljvjz32mLfeyf/Xv/7VffWrX3VDhw719RNnrnYQqHtS5gTNksMaeuqppzwBiIxD/bDUWMe89dZb3cCBA8MkCzeBQIgnFu6SJUvca6+95pctWFt+/PHH3S233OL69OnjfvOb37h7773Xk+jMmTPdHQ37RE899VS/OwbiW7p0qZ84zzvvPD9BXnvttd5yXrFihd+zDvnST+RlaQNiZPlh6tSp7o9//KO3aL/85S+7999/31vap5xyiid8mkAfQ7hMCMi0atXK9ejRw61reIAJQmYSYfJgPzu63HfffZ78R48e7V566SX3yCOPuG9961u+TrZqMtnQTvRnS+aaNWv8fvgQjyags+QMIVD3pMxlHpesaeRMPERZqcs9HhrBcuKEjDkuT7HMdNmKjJ1cMaTS48ALkqJfeVgHIubynnVa1ohZW76w4YGpp59+2l1zzTV+8mOihECxhiFIxgPlYMXSVyeeeKK3TrG4cZDllVde6X796197K/v11193p512midqJgPyMwlomYFJgrFGmdSPFQu5Yi2fddZZXi/Sly9f7pda7rzzTnfxxRe7l19+2a1cudI/Jbpx40Y/lrHecVj7EDI6nXPOOX6ygJSZJHjQyVxtIlD3pIzVwE2bYne0P/jgAz/oK0F+Oim5ARVznMTa41wJfWI61GpcOPFecskl7rvf/a4nYiZCSBei1JUIkx8WKlcjP/vZz9zbb7/trde5c+e6n/zkJ4WJkD4If2DDWKKPuNEHMWL1Qp5YycQff/zxrn///t66RZ6li+HDhxMsuPHjx3uip96HHnrIrw8zAfAQEz7EzuRNeejPsgpPiuKYXCBdiP2ZZ57xEwRr4CynQNDoUepNzYJCFsgMAnVPylhLONb+OAlDp5N40aJF/oaLLJlQ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)
Strategy Skew
- The skew of the strategy. Divided into two:
	- Negative Skew: produce more consistent positive returns but with occasionally drastic downside.
	- Positive Skew: produce consistently small losses, but with occasionally big upside

##### Biases
Overfitting
- Strategy is too complex, so it only works on historical data and not out of sample data.
- Happens if you use historical data for testing multiple times. That is, if you've already seen and used the data for testing, then you optimize your strategy based on that test data, you are already overfitting.
- Also happens if you optimize too much on a specific kind of data.

Multiple Comparisons Bias
- We only use the best statistical test, and ignoring all the others which performed worse.
- Happens quite a lot if you do data mining. Basically the more strategy you test, the higher the chances are that "winning strategies" found are actually winning because of random chance.

Regime Shifts 
- Change in the financial world, which makes older strategies not work as well. (e.g. financial crises).

Overcrowding (or Alpha Decay)
- Certain strategies are overused by the market
- Since not (yet) lots of people use quantitative or systematic trading strat in Indonesia, a good opportunity to tap into it

Survivorship Bias
- Data does not consist of bankrupted companies. It should contain them.

Look-Ahead Bias
- Data consist of information that we won’t know in the past. (e.g. index rebalance).

Representativeness Bias
- Tendency to interfere and stop the algorithm because psychological tendencies.

#### Is it For You?
Do you want to verify that your strategy performs well statistically?

Do you want to know whether there are any correlations between an instrument's price and some other data?

Do you want to know how to mathematically optimize the tradeoff between risk and profit?

Are you comfortable letting your strategy run by itself, automatically?

If you answer yes to the questions, then this is for you!

### Resources
Basic Resources to Start With
- Book: Algorithmic Trading by Ernest P. Chan
- Book: Systematic Trading by Robert E. Carver
- https://www.quantstart.com/articles/Beginners-Guide-to-Quantitative-Trading/
