# Europe Under Pressure — Part 2: AI Shock

**Does higher AI automation exposure relate to higher unemployment in Europe?**

Part 2 of the *Europe Under Pressure* series  
Applying Frey & Osborne (2017) automation risk scores to EU economies using Python.

---

## Research Question

Are countries with higher AI automation exposure also experiencing higher unemployment in Europe?

---

## Key Finding

Using a sample of **26 EU countries** in 2021, we find **no statistically significant association** between a Frey & Osborne (2017)-based AI automation risk score and unemployment.

The coefficient on the AI risk score remains insignificant across all specifications and changes sign depending on the model. Standard economic variables — particularly tertiary education — explain substantially more variation in unemployment than the AI risk measure.

These results are consistent with the earlier smaller sample (N=16).

---

## Results

| Model                              | AI Risk Coefficient | Std. Error | p-value | R-squared | N  |
|------------------------------------|---------------------|------------|---------|-----------|----|
| Model 1: No Controls               | –0.199             | 0.273      | 0.473   | 0.022     | 26 |
| Model 2: Full Controls             | +0.153             | 0.383      | 0.694   | 0.358     | 26 |
| Model 3: Controls (no Manufacturing) | –0.141           | 0.275      | 0.612   | 0.322     | 26 |

**Notes:**
- Full Controls include: log GDP per capita, tertiary education enrollment, and manufacturing share of GDP.
- Tertiary education is the only consistently significant variable (p < 0.01).

---

## Methodology

- **Automation risk**: Frey & Osborne (2017) sector-level probabilities  
  - Manufacturing: 0.70  
  - Services: 0.52  
  - Agriculture: 0.55  
- **Exposure index**: (Sector GDP share in 2021) × (Automation probability)
- **Outcome**: Unemployment rate (2021)
- **Controls**:  
  - Log GDP per capita  
  - Tertiary education enrollment (% gross)  
  - Manufacturing share of GDP  
- **Estimation**: OLS regression (`statsmodels`)
- **Sample**: 26 EU countries (out of EU-27; one country dropped due to missing data)

---

## Limitations

- Sample size remains relatively small (N=26), limiting statistical power.
- The AI risk score is based on Frey & Osborne (2017), which predates generative AI and is not time-varying.
- The coefficient on AI risk changes sign across specifications, indicating sensitivity to model choice.
- Multicollinearity is present when manufacturing is included both in the risk score and as a control.
- This is a pure cross-section. No causal claims are possible.

---

## Interactive Map

[View AI Risk Map](https://poonum-malhi.github.io/Europe-under-pressure-first-China-now-AI/ai_risk_map.html)

---

## Europe Under Pressure — Series Overview

| Project | Question | Main Finding |
|---------|----------|--------------|
| [Part 1 — China Shock](https://github.com/Poonum-Malhi/china-shock-europe) | Did Chinese imports raise EU unemployment? | No clear evidence |
| **Part 2 — AI Shock** (this repo) | Does AI automation exposure raise unemployment? | No significant association |
| Part 3 — Climate Shock | Does CBAM exposure raise unemployment? | Significant but negative association |

---

## Addendum — Why No Panel Analysis

Frey & Osborne (2017) scores are essentially static. A country’s occupational/sectoral structure changes slowly, and no updated comparable risk scores exist for later years.  

Treating this measure as time-varying would not constitute a meaningful test. Constructing a new time-varying AI exposure index is beyond the scope of this project.  

The null result should therefore be interpreted as **unresolved**, not as strong evidence of no relationship.

---

## Tools

`Python` · `pandas` · `wbgapi` · `statsmodels` · `plotly` · Google Colab

---

## Reference

Frey, C. B., & Osborne, M. A. (2017). The future of employment: How susceptible are jobs to computerisation? *Technological Forecasting and Social Change*, 114, 254–280.

---

*Built as part of an Economics × AI research project.*

New updated file entitled as "AI_Shock_Revised Version"
