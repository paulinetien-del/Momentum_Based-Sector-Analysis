# Sector Momentum Rotator

A single-page app that applies a monthly momentum rotation to the 11 US equity sectors, using the SPDR Select Sector ETFs (XLK, XLF, XLV, XLE, XLI, XLY, XLP, XLU, XLB, XLRE, XLC).

## Strategy

1. At each month-end, calculate every sector's trailing return (adjusted close ÷ adjusted close k months earlier − 1).
2. Rank sectors from strongest to weakest.
3. **Buy** the top 3 (equal weight) and hold for the next calendar month.
4. **Avoid / sell** the bottom 3. The middle 5 are a hold.
5. Rebalance next month-end.

## Features

- Ranking table with monthly return, excess return vs SPY, BUY / HOLD / AVOID signal, and the following month's actual result
- Adjustable signal month, lookback (1, 3, 6, 12 months) and basket size (2, 3, 4)
- Rotation tracker: sectors entering and leaving the basket vs the prior month
- Backtest: growth of 100 for top basket, bottom basket, SPY and equal-weight sectors, with hit rate, max drawdown and turnover
- 12-month return heatmap with each month's top 3 and bottom 3 outlined
- Light and dark themes, works on mobile

## Data

Dividend-adjusted month-end closes from Yahoo Finance, Oct 2024 to 13 Oct 2026, embedded in `index.html`. The page does not fetch live prices. To refresh, replace the `RAW` object in the script with newer closes.

## Run it

Open `index.html` in any browser, or enable GitHub Pages (Settings → Pages → deploy from `main`, root folder).

## Disclaimer

For education and research only. Not investment advice. The backtest ignores trading costs, taxes and slippage, and covers a short window. Past momentum does not guarantee future returns.
