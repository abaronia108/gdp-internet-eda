# EDA: GDP per Capita vs. Internet Usage (2000–2022)

Exploratory data analysis examining the relationship between GDP per 
capita and internet adoption across 150+ countries from 2000 to 2022.

## Data Sources
- [World Bank GDP per Capita](https://data.worldbank.org/indicator/NY.GDP.PCAP.CD)
- [UN Internet Usage Data](https://data.un.org/)
- World Bank Country Metadata (region and income group classifications)

## Overview
This project merges and cleans three datasets to create a unified 
analytical dataset, then explores how GDP per capita and internet 
adoption relate globally across income groups and geographic regions.

## Key Findings
- GDP per capita and percent internet users showed strong positive 
  Spearman correlation for every year studied (minimum r = 0.89)
- In earlier years (2000–2010), internet usage grew faster than GDP 
  per capita across most countries. By the 2020s this relationship 
  reversed — GDP growth outpaced internet adoption as high-income 
  countries approached saturation
- In 2000, zero countries had high internet usage (>66%); by 2022, 
  124 countries did. Low internet usage countries dropped from 170 
  to just 22 over the same period
- Sub-Saharan Africa showed the slowest internet adoption of any 
  global region; Europe & Central Asia and North America showed 
  the fastest
- By the 2020s, internet saturation among high-income nations 
  reduced the slope of the GDP-internet trendline significantly — 
  the digital divide narrowed substantially between 2000 and 2022

## Methods
- Data cleaning and standardization across three datasets (wide-to-long 
  reshaping, country name normalization, inner/left merges)
- Log transformation of GDP per capita to address positive skew
- Spearman correlation analysis and correlation heatmaps by year
- Internet usage binning (low/medium/high) to track global adoption 
  over time
- Visualizations: line plots, scatter plots with OLS trendlines 
  (Plotly), violin plots by income group, correlation heatmaps

## Setup
```bash
pip install pandas numpy matplotlib seaborn plotly scipy
```

Then open `gdp_internet_eda.ipynb` in Jupyter or Google Colab.

## File Structure
```
├── gdp_internet_eda.ipynb        # Main analysis notebook
├── data/
│   ├── gdp_per_capita.csv        # World Bank GDP data
│   ├── internet_usage.csv        # UN internet usage data
│   └── country_metadata.csv      # Region and income group info
```
