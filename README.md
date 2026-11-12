# Financial Volatility Modelling

A quantitative-finance notebook exploring the modelling of time-varying volatility in financial return data.

Financial returns often exhibit volatility clustering, where periods of elevated variability tend to be followed by further elevated variability. This project provides a computational setting for examining volatility dynamics using the specifications implemented in the notebook.

## Repository Contents

- `Volatility_Modeling.ipynb` — primary analysis notebook.

## Topics

Consult the notebook for the exact model specifications, data, assumptions, estimation procedure, and diagnostics. The broader modelling context includes conditional heteroskedasticity, volatility clustering, conditional variance estimation, residual diagnostics, and volatility forecasting.

## Technology

Python · Jupyter Notebook · NumPy · pandas · Matplotlib · statistical modelling libraries used in the notebook

## Run

```bash
pip install numpy pandas matplotlib scipy statsmodels arch jupyter
jupyter notebook
```

Open `Volatility_Modeling.ipynb` and execute the analysis from top to bottom. Install any additional dependency identified by the notebook if required.

## Research Considerations

Assess volatility models using residual diagnostics and out-of-sample forecast evaluation, not only in-sample fit. Forecasts are sensitive to asset, return frequency, sample period, distributional assumptions, and market regime.

## Disclaimer

For research and educational purposes only. Model outputs are not investment advice or guarantees of future risk.
