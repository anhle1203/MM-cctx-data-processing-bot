# Crypto Market-Making Toolkit: Data Preprocessing from CCTX Library and Risk Management

## Overview

CCTX (CryptoCurrcency eXchange Trading Library) is an open-source Python-based library designed for cryptocurrency trading and market data retrieval. This repository provides a foundational framework to fetch real-time order book data for Market Makers, calculate important trading metrics, and assess risk using Options Greeks (in progress).

In this example, I utilized the **Kraken** cryptocurrency exchange, though it can be easily adapted for other exchanges by changing a few configuration settings.

### Key Features
- **Real-Time Order Book Fetching:** Fetches order book data for a given cryptocurrency pair from Kraken (default: BTC/USD).
- **Data Preprocessing:** Cleans and processes order book data for analysis, extracting bids, asks, timestamps, and more.
- **Metric Calculations:** Computes mid-price, bid-ask spread, VWAP (Volume Weighted Average Price), order imbalance, market depth, and more.
- **Risk Management:** Implements calculation of key Greeks like Delta, Gamma, Vega to assess and manage risk in a volatile market.

## Getting Started

### Prerequisites

I have gathered all libraries needed for the program to work.

Install required dependencies with:
```bash
pip install -r requirements.txt
```

## Repository Structure
```bash
/data
  /raw        # Directory to save raw order book data
  /processed  # Directory to save processed order book metrics

/notebooks
  /data_preprocessing.ipynb  # Main script for fetching and processing order book data
/README.md             # This documentation
/requirements.txt      # Libraries needed for install
```

## How to Use

1. Clone the repository to local machine:
```bash
git clone https://github.com/anhle1203/cctx-data-preprocessing.git
cd your-repo-name
```

2. Run the Jupyter notebook to fetch orderbook data and calculate metrics
```bash
jupyter notebook data_preprocessing.ipynb
```

3. Output Files:
- Raw Data: Saved in the data/raw directory, with filenames like order_book_BTCUSD_YYMMDD_HH:MM:SS.csv.
- Processed Metrics: Saved in the data/processed directory, with filenames like order_book_metrics_BTCUSD_metrics.csv.

3. Key Calculations in the Notebook

- Mid Price: The average of the best bid and ask prices.
- Bid-Ask Spread: The difference between the highest bid and lowest ask.
- VWAP (Volume-Weighted Average Price): Provides an average price weighted by volume.- Order Imbalance: Measures the relative pressure between buy and sell volumes.
- Market Depth: The cumulative volume on the bid and ask sides at various price levels.

## Continuous 24/7 Trading Considerations

Consider using **cron jobs** (maybe I will do that later as well) or other scheduling tools to automate the script and fetch data periodically. Monitor the market for volatility, and adjust your risk management strategies (such as stop-loss or take-profit mechanisms) based on market conditions.

## Contributing

If you would like to contribute:

1.	Fork the repository.
2.	Create a feature branch: git checkout -b feature/your-feature.
3.	Commit your changes: git commit -m 'Add some feature'.
4.	Push to the branch: git push origin feature/your-feature.
5.	Open a pull request.

