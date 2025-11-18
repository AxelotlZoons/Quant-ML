# Chapter 1 – Data

We download daily equity data (one CSV per ticker) into `data/raw/equities/`.  
Each file is parsed into a DataFrame with typed columns: date, prices, volume, ticker.  
We compute basic daily returns from adjusted close prices.  
All tickers are concatenated into a single panel and sorted by `ticker, date`.  
The processed dataset is stored as `data/processed/equities/prices.parquet`.  
We use Parquet for smaller files and faster load times than CSV.  
Train/test splits are done **by date** to avoid look-ahead bias.  
The warm-up period is reserved for rolling features (not for evaluation).  
Training uses earlier years; testing uses the most recent window only.  
This dataset is the foundation for all strategies and experiments.
