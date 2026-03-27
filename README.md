# Digital Divide Analysis: GDP vs Internet Adoption

## Overview  
This project analyzes how economic development relates to internet adoption across countries using World Bank data (2000–2022). The goal is to quantify expected internet usage based on GDP per capita and identify countries that overperform or underperform relative to their income level.

---

## Objective  
- Measure the relationship between GDP per capita and internet usage  
- Estimate expected internet adoption using a regression model  
- Identify countries that exceed or fall short of expectations  

---

## Dataset  
- Source: World Bank  
- Coverage: 150+ countries  
- Timeframe: 2000–2022  
- Key variables:
  - GDP per capita (USD)  
  - Internet users (% of population)  

---

## Methodology  

### Data Preparation  
- Cleaned and merged multi-year datasets  
- Standardized country-level data  
- Applied log transformation to GDP per capita to address skew  

### Exploratory Analysis  
- Analyzed global trends in internet adoption over time  
- Examined correlation between GDP and internet usage  
- Visualized regional and income-based disparities  

### Regression-Based Analysis (2022)  
A log-linear regression model was used to estimate expected internet adoption:

- Internet Usage ~ log(GDP per capita)

Residuals (actual − predicted) were used to measure performance:
- **Positive residual** → overperformance  
- **Negative residual** → underperformance  

This approach identifies countries performing above or below expectations given their economic level.

---

## Key Findings  
- GDP per capita strongly predicts internet adoption, with diminishing returns at higher income levels  
- Significant variation exists across countries beyond what income alone explains  
- Some countries outperform expectations, suggesting stronger infrastructure or policy  
- Others underperform relative to income, indicating potential barriers to access  

---

## Limitations  
- The model is cross-sectional (2022) and not causal  
- Linear regression can produce predicted values above 100% at high income levels due to saturation effects  
- Does not explicitly account for factors like infrastructure, policy, or inequality  

---

## Technologies Used  
- Python (Pandas, NumPy)  
- Statsmodels (OLS regression)  
- Matplotlib / Seaborn  
- Jupyter Notebook  

---

## How to Run  
1. Clone the repository  
2. Install dependencies:  
   `pip install -r requirements.txt`  
3. Open the notebook and run all cells  

## File Structure
```
├── gdp_internet_eda.ipynb        # Main analysis notebook
├── data/
│   ├── gdp_per_capita.csv        # World Bank GDP data
│   ├── internet_usage.csv        # UN internet usage data
│   └── country_metadata.csv      # Region and income group info
```
