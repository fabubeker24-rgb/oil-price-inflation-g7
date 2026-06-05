# Do Real Oil-Price Changes Still Predict Inflation?
## Evidence from G7 Countries, 1992–2024

**EC3030 Computational Economics** · City St George's, University of London · Spring 2026

---

## Overview

This project investigates whether real crude oil price changes remain a significant predictor of CPI inflation across G7 countries over the period 1992–2024. Using a panel dataset of seven countries and annual observations, I estimate a range of econometric models — from country-level OLS to pooled panel regressions with fixed effects — to test for cross-country heterogeneity and structural change over time.

**Key finding:** The oil–inflation relationship is heterogeneous across G7 countries and has strengthened post-2008, contrasting with Blanchard & Galí's (2007) declining pass-through hypothesis.

---

## Repository Structure

```
oil-price-inflation-g7/
│
├── oil_inflation_g7_analysis.ipynb   # Main analysis notebook (Python)
├── report.pdf                         # Full written report
├── data_inflation_worldbank.csv       # CPI inflation data — World Bank WDI
├── data_crude_oil_owid.csv            # Real crude oil prices — Our World in Data
└── README.md
```

---

## Methods

| Model | Purpose |
|---|---|
| Country-level OLS | Estimate individual pass-through coefficients per G7 country |
| Pooled OLS | Baseline pooled estimate across all 231 observations |
| Panel Fixed Effects | Control for country-level baseline differences |
| Sub-period analysis | Test pre-2008 vs post-2008 structural shift |
| Lagged specification | Test whether oil price effects accumulate over time |
| Year-clustered standard errors | Address cross-sectional correlation in pooled models |

---

## Selected Results

| Country | β (OLS) | p-value | R² |
|---|---|---|---|
| United States | 0.031 | 0.0001 *** | 0.376 |
| Canada | 0.021 | 0.0023 *** | 0.263 |
| France | 0.014 | 0.0385 ** | 0.131 |
| Italy | 0.016 | 0.173 | 0.059 |
| United Kingdom | 0.012 | 0.210 | 0.050 |
| Germany | 0.010 | 0.306 | 0.034 |
| Japan | −0.007 | 0.338 | 0.030 |

**Sub-period shift (pooled):**
- Pre-2008: β = −0.005, p = 0.302 (insignificant)
- Post-2008: β = 0.024, p < 0.001 (significant)

Adding a one-year lag improves R² in every G7 country except Japan, suggesting inflation responds to oil price changes gradually.

---

## Data Sources

- **CPI Inflation:** World Bank World Development Indicators — `FP.CPI.TOTL.ZG`
- **Crude Oil Prices:** Our World in Data real crude oil series (2023 USD)

---

## Technologies

- Python 3 · pandas · NumPy · statsmodels · matplotlib
- Jupyter Notebook

---

## Limitations

- OLS captures predictive association, not causation — supply and demand shocks are not separately identified (Kilian, 2009)
- Annual data masks within-year transmission dynamics (monthly data would capture 3–9 month lags)
- 33 time-series observations limit statistical power for individual country regressions
- Monetary policy stance, exchange rates, and labour market slack are not controlled for

---

## References

- Blanchard, O. J. & Galí, J. (2007). *The Macroeconomic Effects of Oil Price Shocks.* NBER WP 13368.
- Kilian, L. (2009). Not All Oil Price Shocks Are Alike. *American Economic Review*, 99(3), 1053–1069.
- Choi, S. et al. (2018). Oil prices and inflation dynamics. *Journal of International Money and Finance*, 82, 71–96.
- Di Giovanni, J. et al. (2023). *Pandemic-Era Inflation Drivers and Global Spillovers.* NBER WP 31887.

---

*Fahad Abubeker · fabubeker24@gmail.com*
