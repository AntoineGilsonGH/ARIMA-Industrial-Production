# ARIMA Modelling of French Aeronautical and Space Production

Linear time series analysis and forecasting of the **INSEE index of industrial production in aeronautical and space construction** (France, monthly, January 1990 – February 2020).

Course project for *Linear Time Series* (ENSAE Paris, 2024), in R.
**Authors:** Antoine Gilson, Valentin Smague.

## Approach

1. **Exploration**: trend, seasonality (month plot, lag plot, decomposition), ACF and PACF. The series is cut before COVID-19 (362 observations) to keep a stable regime.
2. **Stationarity**: regression on a linear trend, ADF and KPSS unit-root tests; the series is differenced once.
3. **Model selection**: ARMA($p$, $q$) candidates on the differenced series, checked for significant coefficients and white-noise residuals, and compared by AIC and BIC. The retained model is **ARIMA(4,1,0)**.
4. **Forecasting**: predictions at $T+1$ and $T+2$, with 95% univariate intervals and an elliptical bivariate confidence region.

## Files

- [`Rapport.pdf`](Rapport.pdf) — full report, with figures and tables
- [`Project.R`](Project.R) — analysis script
- `Database.csv` — data (INSEE)
- `Consignes.pdf` — project instructions (in French)

To run `Project.R`, change the data path at the top of the script. Packages: `tseries`, `forecast`, `fUnitRoots`, `dplyr`, `ellipse`.
