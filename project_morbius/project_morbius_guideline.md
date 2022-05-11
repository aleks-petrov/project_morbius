# Project Morbius

## Steps
### Stage 1
1. Integrate FPGA execution with an API on an exchange
2. Be able to execute simple orders like: market, stop-loss, and limit orders
3. Build place-holder trading strategy based off a simple indicator like MA
4. Implement the trading strategy using paper trades via an API to an exchange
5. Test efficacy of implementing more complicated models like volatility modeling, etc. into strategy (ran in Python and integrated with the core strategy/order-execution)
6. Perform simple back-test trading strategy over long horizon using historical data in Python
7. Live-test trading strategy using paper trading
8. Compile documentation, create write-up 

### Stage 2
1. Develop system to find candidate stocks of pairs-trading using Python/Fundamentals (opportunistic trading strategy based on spreads wherein investor takes long-short strategy and is market-neutral and profits on reversion to spread of both stocks). Could be either risk or statistical arbitrage
2. Perform cointegration test using Python to verify candidacy for pairs-trading strategy
3. Verify sufficient volume (via forecast) and other market conditions to be able to achieve a market-neutral long-short position in the pair-trading candidates
4. Create FPGA algorithm to execute contingent orders that ensures orders are linked and legging occurs commensurately
5. Back-test strategy on candidate stocks
6. Live-test trading strategy using paper trading
7. Compile documentation, create write-up

### Alternatives
- Work towards an options straddle strategy (strategy focused on spreads)
- Perform options pricing (Black-Scholes or Binomial) in opportune market-cap/industry/volume-level/etc. and exploit arbitrages (eg. more mispricings in iliquid market, high risk-high return)
- Perform delta hedging using options pricing model to exploit time-decay (theta-gang)
- Portfolios: Create portfolio to track an index (minimize errors/residuals between portfolio and underlying), or create portfolio, optimized using standard Markowitz Model (Mean-Variance) or Mean-VaR if possible, or create zero-beta/market-neutral portfolio to "test APT"; or portfolio of pairs-trading
- Compute matrix covariance for portfolio optimization

## On Trade Execution
- "Algorithmic Trading DMA" (reference for trade execution, algorithmic trading, and market structure)
- The "Art and Science of Technical Analysis" (reference for TA)
- "Advances in Active Portfolio Management" (reference for topic in modern portfolio management)

## Server-Side/APIs 

## FPGA Related
- General: https://www.velvetech.com/blog/fpga-in-high-frequency-trading/
- Black-Scholes: https://www.researchgate.net/publication/271039667_FPGA-Based_Design_of_Black_Scholes_Financial_Model_for_High_Performance_Trading

## Trading Strategies (for reference/inspiration)
- “Systematic Trading” and “Trading Systems” (reference for developing and implementing trading strategy)
- An arbitrage guide to financial markets (reference for asset types and arbitrage opportunities)
- Pairs Trading (Market Neutral, Mean Reversion): https://en.m.wikipedia.org/wiki/Pairs_trade
- Capital Structure Arbitrage (Market Neutral): https://thebusinessprofessor.com/en_US/investments-trading-financial-markets/capital-structure-arbitrage-definition; https://www.fdic.gov/analysis/cfr/2005/apr/fyu.pdf
- General Statistical Arbitrage (Mean Reversion, Market Neutral, Arbitrage): https://en.m.wikipedia.org/wiki/Statistical_arbitrage
- General Mean Reversion (Mean Reversion): https://en.m.wikipedia.org/wiki/Mean_reversion_(finance)
- General Market Neutral (Market Neutral): https://en.m.wikipedia.org/wiki/Market_neutral
- Zero-Beta: https://www.investopedia.com/terms/z/zero-betaportfolio.asp; https://www.dallasfed.org/-/media/documents/banking/occasional/1401.pdf
- Bet Against Beta: https://www.investopedia.com/articles/investing/082515/how-aqr-places-bets-against-beta.asp

## Statistical Concepts
- Discrete vs. Continous: https://en.m.wikipedia.org/wiki/Discrete_time_and_continuous_time
- Time-Series Reference: https://otexts.com/fpp2/index.html
- Stationarity: https://en.m.wikipedia.org/wiki/Stationary_process
- Autocorrelation: https://en.m.wikipedia.org/wiki/Autocorrelation
- Autoregressive Model: https://en.m.wikipedia.org/wiki/Autoregressive_model
- Moving Average Model: https://en.m.wikipedia.org/wiki/Moving-average_model
- ARIMA Model: https://en.m.wikipedia.org/wiki/Autoregressive_integrated_moving_average
- Cointegration: https://en.m.wikipedia.org/wiki/Cointegration







