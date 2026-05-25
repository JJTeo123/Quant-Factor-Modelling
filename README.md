# Quant-Factor-Modelling

This repository contains a Python-based quantitative research pipeline implementing the Fama-French 3-Factor and Carhart 4-Factor models for equity asset pricing across a custom ETF universe. 

## Project Structure

### 1. `01_asset_universe_benchmarking.ipynb`
Handles the initial data engineering and exploratory data analysis (EDA) for the asset universe. 

* **Data Ingestion:** Fetches historical daily price and volume data for 31 ETFs spanning multiple asset classes (2010–2026).
* **Preprocessing:** Cleans the raw data, handles forward-filling for missing values, and computes daily and monthly log returns.
* **Baseline Analytics:** Calculates baseline performance metrics, including Annualized Return, Annualized Volatility, and Sharpe Ratios, to establish a benchmark before applying factor overlays.

### 2. `02_factor_modelling.ipynb`
Focuses on alpha signal generation, factor construction, and out-of-sample testing.

* **Signal Generation:** Constructs the Market (MKT), Size (SMB), and Value (HML) factors for the Fama-French 3-Factor model, along with the Momentum (WML) factor for the Carhart 4-Factor extension using market cap proxies and rolling metrics.
* **Factor Spreads:** Computes the daily factor spreads to isolate the premium of each specific factor.
* **Evaluation:** Splits the historical data into in-sample (train) and out-of-sample (test) periods, and plots the cumulative excess returns (alphas) of the FF3 and FF4 portfolios.