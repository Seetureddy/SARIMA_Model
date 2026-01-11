# SARIMA_Model

Lightweight toolkit for univariate time‑series forecasting using Seasonal ARIMA (SARIMA). Includes preprocessing utilities, model fitting, diagnostics, and forecast evaluation.

## Features
- Data loading, resampling and imputation helpers
- SARIMA training (manual and automated order selection)
- Model diagnostics (residuals, ACF/PACF, Ljung–Box)
- Forecasting with prediction intervals and evaluation metrics
- Jupyter notebooks and CLI-style scripts for examples

## Requirements
- Python 3.8+
- Core packages: numpy, pandas, statsmodels, matplotlib, seaborn, scikit-learn
- Optional: pmdarima (for auto_arima)

Install:
pip install -r requirements.txt
(or pip install numpy pandas statsmodels matplotlib seaborn scikit-learn pmdarima)

## Quick start
1. Place a CSV in `data/` with a date column and a single value column.
2. Run the training script (adjust args as needed):
```bash
python scripts/train_sarima.py \
  --data data/series.csv --date-col date --value-col value \
  --freq D --train-size 0.8 \
  --order 1 1 1 --seasonal-order 1 1 1 12 \
  --out-dir outputs/
```
3. Check `outputs/` for model summary, forecasts and plots.

## Typical workflow
1. Inspect and preprocess series (resample, impute, transform).
2. Split time-based train/test.
3. Select orders (ACF/PACF or auto_arima).
4. Fit SARIMA, validate with diagnostics and holdout.
5. Produce final forecast and save model + preprocessing steps.

## Evaluation
Common metrics: RMSE, MAE, MAPE. Also inspect residuals and prediction interval coverage.

## Contributing
Contributions welcome. Please open issues or PRs for bug fixes, examples, tests, or documentation improvements.

## License & Contact
MIT License (default — check LICENSE file). For questions, open an issue or contact the maintainer: Seetureddy.
