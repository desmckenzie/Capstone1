# Capstone 1: U.S. Housing Market Analysis  

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/desmckenzie/Capstone1/blob/main/Capstone1_Destiny_McKenzie.ipynb)
---

## Project Overview  
This project analyzes long‑term trends in the U.S. housing market using the Federal Housing Finance Agency (FHFA) House Price Index (HPI). The goal is to evaluate how single‑family home values have changed over time, identify patterns in appreciation, and assess market variability using descriptive statistics and exploratory data analysis (EDA).

The analysis is performed in Google Colab, and all code, data, and documentation are stored in this GitHub repository for reproducibility.

---

## Dataset Description  
The FHFA HPI dataset contains historical housing price index values for single‑family homes across the United States. The dataset includes seasonally adjusted and non‑seasonally adjusted index values, standard errors, and categorical indicators.

### **FHFA HPI Attribute Table**

| Column       | Description                                                   | Measurement Type | Appropriate Statistics                     | Missing-Value Notes                                      |
|--------------|---------------------------------------------------------------|------------------|---------------------------------------------|-----------------------------------------------------------|
| yr           | Calendar year of observation                                  | Ordinal          | Mean, median, std, range                    | No missing values                                         |
| period       | Month or quarter of observation (categorical)                 | (categorical)  | Frequencies, mode only                      | No missing values; treat as categorical                   |
| index_nsa    | Non-seasonally adjusted House Price Index                     | Ratio            | Mean, median, std, range                    | Missing values are structural (not available for all areas) |
| index_sa     | Seasonally adjusted House Price Index                         | Ratio            | Mean, median, std, range                    | Missing values are structural (seasonal adj. not always computed) |
| rstderr      | Standard error of the index estimate                          | Ratio            | Mean, median, std, range                    | Missing when FHFA does not publish uncertainty            |
| note         | FHFA notes or flags for specific observations                 | Nominal          | Frequency counts                            | Missing means “no note”; safe to retain                   |

---

## Summary Statistics  
Summary statistics were computed only for variables with appropriate measurement types.

### Mean & Median  
Calculated for:  
- `yr`  
- `index_nsa`  
- `index_sa`  
- `rstderr`  

Excluded for:  
- `period` (categorical)  
- `note` (nominal)

### Mode  
Mode was computed for all variables, but:

- Continuous variables (`index_nsa`, `index_sa`, `rstderr`) rarely repeat → mode is **not meaningful**  
- Pandas returns `NaN` for these columns → these missing values are **structural**, not errors  
- Only `yr` has a meaningful mode because years repeat  

**Decision:**  
Mode will be interpreted only for `yr`.  
Missing mode values for continuous variables are retained and treated as “not applicable.”

---

## Missing-Value Strategy  
Missing values in the FHFA dataset are **structural**, not accidental.

- **index_sa:** Missing when seasonal adjustment is not available  
- **rstderr:** Missing when FHFA does not publish uncertainty  
- **note:** Missing simply means “no note”

**Handling Approach:**  
- No imputation(replacing missing data) performed  
- Missing values retained  
- Excluded only when a specific analysis requires complete numeric data  
- Time‑series and categorical analyses use all available rows  

---

## Exploratory Data Analysis (EDA)
### **1. HPI Trend Over Time**
The average non‑seasonally adjusted HPI increases steadily over time, showing long‑term appreciation in single‑family home values.  
Periods of rapid growth (early 2000s, post‑2012) and slower growth (post‑2008 recession) highlight market volatility.

### **2. Seasonal Patterns**
Grouping HPI by `period` reveals predictable seasonal variation.  
This supports FHFA’s use of seasonally adjusted indices and explains why `index_sa` is consistently higher than `index_nsa`.

### **3. Distribution of HPI Values**
The distribution of HPI values is right‑skewed.  
This explains why the mean is higher than the median and indicates that extreme appreciation periods pull the average upward.

---

## Supporting Dataset: Zillow Home Value Index (ZHVI)  
ZHVI is used to validate FHFA findings and represents the typical home value (35th–65th percentile) using Zillow’s neural Zestimate model.

ZHVI supports FHFA trends by showing:
- long‑term appreciation  
- regional variation  
- right‑skewed distributions  
- seasonal patterns  




