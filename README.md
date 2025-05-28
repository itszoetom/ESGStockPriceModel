# ESGStockPriceModel

This repository contains exploratory and production code for modeling electric vehicle (EV) stock returns using both financial and non-financial data sources. The primary focus is on assessing whether metal ETF prices and ESG-related signals can provide predictive power for EV-sector equity performance. The project was developed across two academic terms as part of Oregon Quantitative Group (OQG) research.

## Folder Structure

### `/data/`  
Raw and processed datasets including metal ETF prices, ESG scores, and Reddit sentiment (where applicable).

### `/figures/`  
Output visualizations from the notebooks — plots of model evaluation, Granger causality, heatmaps, etc.

## Jupyter Notebooks

### `ETF_signal_SpringProj.ipynb`  
**Main notebook for Spring term project**  
Uses Granger causality and machine learning (Ridge, XGBoost, LSTM) to test if global metal ETF prices (e.g., LIT, JJN) can predict EV stock log-returns (TSLA, NIO, BYD, TM).

### `load_metal_etf_df.ipynb`  
Downloads and formats daily metal ETF price data from Yahoo Finance using `yfinance`, standardizing it into log-returns for modeling.

### `tesla_exp.ipynb`  
**Main notebook for Winter term project**  
Focuses on predicting Tesla's stock price using ESG-related features — particularly non-financial indicators like environment, governance, and social scores. Demonstrates that ESG data alone had limited predictive power due to coarse frequency and sparse coverage.

## Archive (Exploratory Work)

### `etf_modeling_exp.ipynb`  
Tests rolling-window regressions and lag tuning for ETF data to evaluate model stability over time.

### `esg_included_NN.ipynb`  
Initial neural network experiments combining ESG data with price signals — cut due to ESG data's annual resolution and lack of history.

### `sentiment_exp.ipynb`  
Reddit scraping and sentiment modeling experiment using `PRAW` and NLP — ultimately discontinued due to inconsistent data quality.

### `pca_exp.ipynb`  
Tests principal component analysis (PCA) to reduce dimensionality of ETF data — found no performance benefit in this case.

### `neural_network_exp.ipynb`  
Generic deep learning experiments on EV stock returns using dense feedforward networks; served as a precursor to the later LSTM work.

## Summary

Despite initial Granger causality links between metal ETFs and EV stocks, predictive performance was modest across all models. ESG and sentiment-based features were limited by data granularity. Future directions include macroeconomic signal integration, regime-switching models, and ensemble learning.
