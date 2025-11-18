# Chapter 2 – Monkey Baseline

The monkey trader is a simple random long/flat strategy per ticker.  
Each day, for each stock, it may buy, hold, or sell based on a coin flip.  
Position is either 0 (flat) or 1 (long one unit); no shorting or leverage.  
We use a fixed random seed so results are reproducible.  
Strategy returns are: yesterday’s position × today’s price return.  
Per-ticker returns are averaged across tickers to form an equal-weight portfolio.  
We then plot the cumulative portfolio return as the monkey’s equity curve.  
A “troop” of monkeys is created by varying the seed and repeating the process.  
This baseline gives us a random benchmark future models should beat.  
If a model can’t outperform the monkeys, it’s not good enough yet.
