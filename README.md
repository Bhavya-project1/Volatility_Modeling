# ARCH, GARCH and EWMA Volatility Forecasting

A Python notebook comparing three approaches to modelling and forecasting the volatility of **JPMorgan Chase (JPM)** daily returns:

- ARCH(1)
- GARCH(1,1)
- Exponentially Weighted Moving Average (EWMA)

The notebook estimates conditional volatility from historical returns and examines short-horizon forecasts against a realised-volatility observation.

## Data and Setup

- Instrument: JPM
- Main estimation window: 2022-01-01 to 2025-01-01
- Return convention: daily percentage change for ARCH/GARCH; daily decimal returns for the EWMA section
- EWMA decay parameter: λ = 0.94
- ARCH/GARCH forecast horizon: five trading days

The notebook also contains an earlier JPM price-history download beginning in 2015 for inspection.

## Methodology

### ARCH(1)

Models conditional variance as a function of the previous period's squared innovation.

### GARCH(1,1)

Adds a lagged conditional-variance term, allowing volatility persistence to be represented.

### EWMA

Updates variance recursively using a decay parameter, assigning greater weight to recent squared returns.

## Cached Example Output

The executed notebook contains the following historical comparison for the five-day volatility forecasts at the end of the 2024 estimation sample:

| Model | Mean forecast volatility | Realised volatility |
|---|---:|---:|
| ARCH(1) | 1.5563% | 1.6919% |
| GARCH(1,1) | 1.6210% | 1.6919% |

These are cached notebook outputs, not live forecasts. They should be interpreted cautiously: the exact realised-volatility calculation and forecast aggregation convention should be checked before treating the values as a formal accuracy comparison. The EWMA section is implemented separately in the notebook.

## Repository Contents

- Volatility_Modeling.ipynb — model estimation, forecasting, and comparison.

## Technology

Python · NumPy · pandas · yfinance · arch · Jupyter Notebook

## Run

~~~bash
pip install -r requirements.txt
jupyter notebook
~~~

Open the notebook and execute the cells in sequence. Yahoo Finance data is downloaded at runtime.

## Validation Priorities

A research-grade extension should evaluate rolling one-step-ahead forecasts, compare against realised variance using a consistent horizon, use QLIKE and MSE where appropriate, examine standardised residuals and squared residuals, and report forecast performance over multiple market regimes.

## Disclaimer

Educational volatility-modelling exercise only. Forecasts are model-dependent and are not investment advice or guarantees of future risk.
