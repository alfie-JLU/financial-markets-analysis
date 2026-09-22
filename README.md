# Financial Markets Analysis: S&P 500 vs FTSE 100

I made this project to practise using Python with financial data. I taught myself the pandas basics needed to compare the S&P 500 and FTSE 100, looking at their price growth, daily returns, volatility and correlation.

## Data and tools

The notebook uses daily closing index levels from Yahoo Finance, downloaded with `yfinance`. The selected period is 12 September 2016 to 10 September 2026.

The indices are:
- S&P 500: `^GSPC`
- FTSE 100: `^FTSE`

I used Python, pandas, NumPy and Matplotlib in Jupyter Notebook.

## What I did

I calculated daily returns by dividing each closing level by the previous trading day’s closing level and subtracting one. I then matched the dates across the two indices and removed rows where either return was missing.

Using these matched returns, I calculated:
- Average daily return.
- Daily volatility, measured by the sample standard deviation.
- Annualised volatility, calculated as daily volatility multiplied by the square root of 252.
- Correlation between the two indices’ daily returns.

I also plotted price growth by dividing both indices by their levels on the first shared date. This makes both lines start at 1, so their relative growth is easier to compare.

## Main findings

| Measure | S&P 500 | FTSE 100 |
|---|---:|---:|
| Average daily price return | 0.0537% | 0.0207% |
| Annualised volatility | 18.09% | 14.82% |

Daily return correlation was **0.488**.

Over the period analysed, the S&P 500 had higher average daily returns and greater price growth, but its daily returns also fluctuated more than those of the FTSE 100.

The positive correlation shows that the two return series tended to move together, although the relationship was not especially strong.

## Limitations

This comparison uses price indices, so it does not include reinvested dividends. It also does not account for exchange-rate changes or convert returns into a common currency.

The US and UK have different market holidays and closing times. Matching returns by date therefore does not always mean they cover exactly the same interval. The return statistics only include dates with data for both indices.

Annualised volatility assumes 252 trading days per year. These results describe the selected historical period and do not predict future performance.

## Running the notebook

The notebook needs Python, pandas, NumPy, Matplotlib and yfinance.

Open `financial_markets_analysis.ipynb` in Jupyter Notebook and run the cells from top to bottom. An internet connection is needed to download the data from Yahoo Finance.

## What I practised

This project gave me practice selecting columns in pandas, combining data by date, handling missing values and calculating statistics. I also used Matplotlib to present the results in charts.

A future improvement would be to include reinvested dividends and compare returns in the same currency.
