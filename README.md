# Europe Under Pressure — Part 2: AI Shock

**Which export sectors in Europe face the highest AI displacement risk?**

Part 2 of the *Europe Under Pressure* series  
Applying Frey & Osborne (2017) automation risk scores to EU economies using Python.

---

## Research Question 

Are countries with higher AI automation exposure also experiencing higher unemployment in Europe?

---

## Key Finding 

In a cross-section of 16 EU countries (2021), after controlling for log GDP per capita, tertiary education enrollment, and manufacturing share, the coefficient on the AI automation risk score is **0.29** (SE = 0.73, p = 0.70).  

The association remains statistically insignificant.  

The large increase in R-squared (from 0.03 to 0.57) after adding controls indicates that standard economic variables explain unemployment far better than this AI exposure measure.

---

## Results

| Metric                        | Without Controls | With Controls |
|-------------------------------|------------------|---------------|
| Coefficient on AI risk score  | –0.57            | 0.29          |
| Standard Error                | 0.87             | 0.73          |
| p-value                       | 0.518            | 0.697         |
| R-squared                     | 0.031            | 0.571         |
| N                             | 16               | 16            |

Most exposed country: **Germany (46.5)**  
Least exposed country: **Poland (42.7)**

---

## Methodology

- **Automation risk**: Frey & Osborne (2017) sector-level probabilities  
  - Manufacturing: 0.70  
  - Services: 0.52  
  - Agriculture: 0.55  
- **Sector data**: World Bank API (`wbgapi`) — Manufacturing, Services, Agriculture (% of GDP)
- **Exposure index**: GDP share (2021) × automation probability
- **Outcome**: Unemployment rate (2021)
- **Controls**: Log GDP per capita, Tertiary education enrollment, Manufacturing share of GDP
- **Estimation**: OLS regression (`statsmodels`)
- **Sample**: 16 EU economies

---

## Limitations

- Sample size is only 16 countries → very low statistical power.
- The AI risk score uses Frey & Osborne (2017) probabilities, which predate generative AI and are not time-varying.
- Adding controls caused the coefficient to change sign, suggesting the original bivariate result was unstable.
- Multicollinearity is present because manufacturing enters both the risk score construction and the control set.
- This remains a pure cross-section; no causal claims are possible.

---

## Interactive Map

[View AI Risk Map](https://poonum-malhi.github.io/Europe-under-pressure-first-China-now-AI/ai_risk_map.html)

---

## Europe Under Pressure — Full Series

| Project | Question | Finding |
|---------|----------|---------|
| [Part 1 — China Shock](https://github.com/Poonum-Malhi/china-shock-europe) | Did Chinese imports raise EU unemployment? | No — industrial upgrading offset the shock |
| **Part 2 — AI Shock** (this repo) | Does AI exposure raise EU unemployment? | No significant association (even after controls) |
| Part 3 — Climate Shock | Does CBAM exposure raise EU unemployment? | Significant but negative association |

---

## Addendum — Why This Channel Was Not Extended to a Panel (July 2026)

Frey and Osborne (2017) automation risk scores are occupation-level estimates of computerisation probability. They are not a time-varying measure. A country’s occupational structure changes slowly, and no updated, comparably-constructed risk score exists for intervening years.

Extending this channel to a panel would require either treating a static exposure measure as if it varied year to year (which would not be a genuine test) or constructing an entirely new time-varying automation exposure index (beyond the scope of this project).

This is a distinct category of limitation. The null result should be read as **unresolved**, not as evidence of no relationship.

---

## Tools

`Python` · `pandas` · `wbgapi` · `statsmodels` · `plotly` · Google Colab

---

## Reference

Frey, C. B., & Osborne, M. A. (2017). The future of employment: How susceptible are jobs to computerisation? *Technological Forecasting and Social Change*, 114, 254–280.

---

*Built as part of an Economics × AI research project.*
