# Europe-under-pressure-first-China-now-AI
Which export sectors in Europe face highest AI displacement risk?
Part 1 of Europe under Pressure series. Part 2: AI automation risk in EU export sectors 
# AI Shock — Europe
### Part 2 of the *Europe Under Pressure* Series

Applying Frey & Osborne (2017) automation risk scores to EU export sectors using Python.

---

## Research Question
Are countries with higher AI automation exposure also experiencing higher unemployment in Europe?

## Key Finding
Contrary to expectations, higher AI automation risk scores are **negatively associated** 
with unemployment (coefficient: -0.57, p=0.518). The result is not statistically 
significant — suggesting that as of 2021, AI exposure has not yet translated into 
measurable labor market disruption in Europe.

This mirrors the finding from Part 1: Europe consistently shows more resilience 
to trade and technology shocks than simple models predict.

## Methodology
- **Automation risk:** Frey & Osborne (2017) sector-level probabilities
- **Sector data:** World Bank API (wbgapi) — Manufacturing, Services, Agriculture
- **Exposure index:** GDP share (2021) × automation probability
- **Outcome:** Unemployment rate (2021)
- **Estimation:** OLS regression (statsmodels)
- **Countries:** 16 EU economies

## Results
| Finding | Value |
|--------|-------|
| Coefficient on AI risk score | -0.57 |
| R-squared | 0.031 |
| p-value | 0.518 |
| Most exposed country | Germany (46.5) |
| Least exposed country | Poland (42.7) |

## Tools
`Python` `pandas` `wbgapi` `plotly` `statsmodels` `Google Colab`

## Part of the Europe Under Pressure Series
| Project | Question | Finding |
|---------|----------|---------|
| [Part 1 — China Shock](https://github.com/Poonum-Malhi/china-shock-europe) | Did Chinese imports raise EU unemployment? | No — industrial upgrading offset the shock |
| Part 2 — AI Shock (this repo) | Does AI exposure raise EU unemployment? | No — not yet statistically significant |
| Part 3 — coming soon | | |

## Interative Map HTML
[🗺️ View Interactive Map](https://htmlpreview.github.io/?https://github.com/Poonum-Malhi/Europe-under-pressure-first-China-now-AI/blob/main/ai_risk_map.html)

## Reference
Frey, C. B., & Osborne, M. A. (2017). The future of employment: How susceptible 
are jobs to computerisation? *Technological Forecasting and Social Change*, 114, 254–280.

---
*Built as part of an Economics × AI research. *
