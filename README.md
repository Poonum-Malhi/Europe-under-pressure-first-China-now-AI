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
https://poonum-malhi.github.io/Europe-under-pressure-first-China-now-AI/ai_risk_map.html
## Medium 
📖 [Read the full analysis on Medium](https://medium.com/@poonummalhi04/europe-under-pressure-first-china-now-b5db88ea4d68)

------
## Addendum — Why This Channel Was Not Extended to a Panel (July 2026)

Two other channels in this series (China Shock and GVC/Reshoring) were re-tested using multi-year panel
data to check whether their original cross-sectional results were driven by small sample size. This note
explains why the same approach was not applied here, as a deliberate methodological choice rather than an
oversight.

Frey and Osborne (2017) automation risk scores are occupation-level estimates of computerisation
probability. They are not a time-varying measure: a country's occupational structure changes slowly, and
no updated, comparably-constructed risk score exists for intervening years. Extending this channel to a
panel would require either treating an essentially static exposure measure as if it varied year to year,
which would not be a genuine test, or constructing an entirely new time-varying automation exposure index,
which is beyond the scope of this project.

This is flagged as a distinct category of limitation. The China Shock and Housing Shock null results were
re-tested with much larger panels and remained null, evidence that those results are not simply
underpowered. The AI Shock null result, by contrast, has not yet been tested for a power problem at all,
since the underlying exposure measure does not currently permit it. It should be read as unresolved,
not as evidence of no relationship.

## Reference
Frey, C. B., & Osborne, M. A. (2017). The future of employment: How susceptible 
are jobs to computerisation? *Technological Forecasting and Social Change*, 114, 254–280.

---
*Built as part of an Economics × AI research. *
