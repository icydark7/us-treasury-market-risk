# Fixed-Income Market Risk Analysis Using Python

## Project Overview

This project analyzes historical US Treasury par yield curve movements from 2020 to 2025 and evaluates their implications for a hypothetical fixed-income portfolio.

The analysis explores interest-rate sensitivity, estimates historical portfolio profit and loss (P&L), and compares two approaches to measuring downside risk.

## Business Objective

To understand how changes in Treasury yields affect a hypothetical bond portfolio and estimate historical market risk using duration, DV01, Value at Risk (VaR), and Expected Shortfall (ES).

## Tools Used

- **Python** — analysis and calculations
- **Pandas** — data preparation and manipulation
- **Matplotlib** — visualizations
- **Seaborn** — correlation heatmap
- **Jupyter Notebook** — analysis workflow

## Project Workflow

1. Loaded and combined historical Treasury yield datasets.
2. Standardized column names, converted dates, and checked data quality.
3. Analyzed yield trends, daily yield changes, volatility, and correlations across maturities.
4. Constructed a hypothetical $1 million portfolio of 2-year, 10-year, and 30-year Treasury bonds.
5. Calculated bond duration and DV01 to estimate interest-rate sensitivity.
6. Estimated historical daily P&L using DV01-based approximations.
7. Calculated 95% historical VaR and Expected Shortfall.
8. Compared DV01-based P&L with cash-flow repricing estimates.

## Key Results

| Metric | Result |
|---|---:|
| Hypothetical portfolio value | $1,000,000 |
| Historical daily observations | 1,499 |
| Total portfolio DV01 | Approximately $1,066.88 per basis point |
| 95% VaR — DV01 method | $9,666.29 |
| 95% VaR — repricing method | $9,553.81 |
| 95% Expected Shortfall — DV01 method | $13,148.41 |
| 95% Expected Shortfall — repricing method | $12,973.00 |
| Correlation between P&L methods | 0.9999 |

## Interpretation

The two P&L estimation methods produced highly correlated results across the historical scenarios. Cash-flow repricing produced slightly lower estimates of 95% VaR and Expected Shortfall than the DV01 approximation.

The comparison illustrates how a linear duration-based approximation can differ from a nonlinear bond-pricing calculation.

## Limitations

- The portfolio is hypothetical and does not represent actual holdings or trading activity.
- Treasury par yields are used as simplified yield proxies for hypothetical bond valuation; they are not actual prices or bond-specific yields.
- The DV01 method is a linear approximation of bond-price sensitivity.
- The cash-flow repricing approach is illustrative and is not a fully market-calibrated valuation using a complete discount curve.
- Historical VaR and Expected Shortfall depend on the selected observation period and do not guarantee future losses will remain within the estimated thresholds.

## Data Source

The dataset is published by the U.S. Department of the Treasury. The Data.gov catalogue lists the Daily Treasury Yield Curve Rates dataset under the CC0 1.0 public-domain dedication.

Source: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?page=0&type=daily_treasury_yield_curve

Dataset metadata: https://catalog.data.gov/dataset/interest-rate-statistics-daily-treasury-yield-curve-rates

## How to Use

Open `us_treasury_market_risk.ipynb` in Jupyter Notebook or JupyterLab. The CSV input files used by the notebook must be available in the working directory before running the analysis.

## Conclusion

This project demonstrates a Python-based workflow for analyzing Treasury yield movements, estimating fixed-income interest-rate sensitivity, measuring historical downside risk, and comparing two approaches to portfolio P&L estimation.
