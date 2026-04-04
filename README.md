# Digital Divide Analysis: GDP vs Internet Adoption

## Overview

This project analyzes how economic development relates to internet adoption across countries
using UN and World Bank data (2000–2022). The goal is to quantify expected internet usage based on
GDP per capita and identify countries that overperform or underperform relative to their
income level.

---

## Key Insights
- GDP per capita strongly predicts internet adoption
- Some countries outperform expectations given their income level
- Others underperform, suggesting structural barriers beyond income

---

## Objective

* Measure the relationship between GDP per capita and internet usage
* Estimate expected internet adoption using a regression model
* Identify countries that exceed or fall short of expectations

---

## Dataset

* Source: World Bank
* Coverage: 150+ countries
* Timeframe: 2000–2022
* Key variables:
  + GDP per capita (USD)
  + Internet users (% of population)

---

## Methodology

### Data Preparation

* Cleaned and merged multi-year datasets
* Standardized country names and column names across datasets
* Applied log transformation to GDP per capita to address skew
* Added internet usage bins (Low / Medium / High) and ratio-based features

### Exploratory Analysis

* Analyzed global and regional trends in internet adoption over time using line plots
* Examined correlation between GDP and internet usage via Spearman correlation heatmaps for each year studied
* Visualized income-based disparities using a faceted violin plot across all years
* Visualized the GDP vs internet usage relationship across all years using a faceted scatterplot

### Regression-Based Analysis (2022)

A log-linear regression model was used to estimate expected internet adoption:

* Internet Usage ~ log(GDP per capita)

Residuals (actual − predicted) were used to measure performance:

* **Positive residual** → overperformance
* **Negative residual** → underperformance

This approach identifies countries performing above or below expectations given their
economic level.

---

## Key Findings

* GDP per capita strongly predicts internet adoption, with diminishing returns at higher income levels
* The correlation between GDP and internet usage was strong and consistent across all years studied (minimum Spearman r = 0.89)
* Significant variation exists across countries beyond what income alone explains
* High-income countries showed wide variation in internet usage in 2000 that narrowed significantly by 2022 as adoption saturated
* Some countries outperform expectations, suggesting stronger infrastructure or policy
* Others underperform relative to income, indicating potential barriers to access
* Sub-Saharan Africa showed the slowest internet adoption; Europe & Central Asia and North America showed the fastest

---

## Limitations

* The regression model is cross-sectional (2022) and not causal
* Linear regression can produce predicted values above 100% at high income levels due to saturation effects
* Does not explicitly account for factors like infrastructure, policy, or inequality

---

## Technologies Used

* Python (Pandas, NumPy)
* Statsmodels (OLS regression)
* Matplotlib / Seaborn
* Plotly Express
* Jupyter Notebook

---

## How to Run

1. Clone the repository
2. Install dependencies:
   `pip install -r requirements.txt`
3. Place data files in the `data/` folder
4. Open the notebook and run all cells

## File Structure
```
├── gdp_internet_eda.ipynb        # Main analysis notebook
├── data/
│   ├── gdp_per_capita.csv        # World Bank GDP data
│   ├── internet_usage.csv        # UN internet usage data
│   └── country_metadata.csv      # Region and income group info
```
