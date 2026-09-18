[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/desmckenzie/Capstone1/blob/main/Capstone1_Destiny_McKenzie.ipynb)

# Capstone 1: U.S. Housing Market Analysis  

---

## 📌 Overview  
This project analyzes long‑term trends in the U.S. housing market using the Federal Housing Finance Agency (FHFA) House Price Index (HPI). The goal is to evaluate how single‑family home values have changed over time, identify patterns in appreciation, and assess market volatility using descriptive statistics and visualizations.

The analysis is performed in **Google Colab**, and all code, data, and documentation are stored in this GitHub repository for transparency and reproducibility.

---

## 📊 Objectives  
- Load and explore the FHFA HPI dataset  
- Compute descriptive statistics (mean, median, mode, range, standard deviation)  
- Visualize summary statistics and index trends  
- Identify missing values and data quality issues  
- Interpret findings about the typical single‑family home  
- Support conclusions using an external dataset (Zillow ZHVI)

---


---

## 🏛️ Data Sources  

### **1. FHFA House Price Index (Primary Dataset)**  
The FHFA HPI dataset was obtained directly from the Federal Housing Finance Agency.  
It measures changes in single‑family home values using a repeat‑sales methodology.

- **Original Source:** FHFA House Price Index Data Portal  
- **Dataset Name:** HPI Master Data  
- **Source URL:** *[insert the exact CSV link you used]*  
- **Date Downloaded:** September 2026  
- **Storage:** The dataset is included in this repository under `/data/` for reproducibility.

The notebook loads the dataset either directly from FHFA or from the GitHub raw file link.

### **2. Zillow Home Value Index (Supporting Dataset)**  
The Zillow Home Value Index (ZHVI) is used to validate FHFA findings.  
ZHVI represents the typical home value (35th–65th percentile) using Zillow’s neural Zestimate model.

- **Source:** Zillow Research  
- **Dataset:** Zillow Home Value Index (ZHVI)  
- **Purpose:** Supports conclusions about long‑term appreciation and market variability.

---

## 🔧 Methods & Tools  
- **Python (Google Colab)**  
- **Pandas** for data loading, cleaning, and descriptive statistics  
- **Matplotlib & Seaborn** for visualizations  
- **GitHub** for version control and reproducibility  

---

## 📈 Key Analyses  
- Summary statistics (mean, median, mode, std, range)  
- Missing value identification  
- Distribution analysis  
- Time‑series visualization of index values  
- Comparison between seasonally adjusted and non‑adjusted indices  
- Interpretation of housing market trends  
- External validation using Zillow ZHVI  

---

## ▶️ How to Run the Notebook  
You can open the notebook directly in Google Colab:

1. Navigate to the notebook in this repository.  
2. Click **“Open in Colab”**  
   or  
3. Use this format:  
https://colab.research.google.com/github/desmckenzie/Capstone1/blob/main/Capstone1_Destiny_McKenzie.ipynb

The notebook will automatically load the FHFA dataset from GitHub or the FHFA URL.

---



