# Analysis Approach – Environmental Toxin Analysis in River Systems  

**Author:** Joe Woods  
**Project:** Environmental Toxin Analysis in River Systems  
**Dataset:** National_River_Toxin_Dataset_1.csv

---
  
## 1. Objective

The aim of this project was to perform a comprehensive exploratory data analysis (EDA) on water quality and toxin concentrations across major global river systems. The focus was on understanding heavy metal pollution (Lead, Mercury, Arsenic), nutrient levels, and key water chemistry parameters, and identifying statistically meaningful differences between river systems.

---

## 2. Dataset Overview

* **Source File:** National_River_Toxin_Dataset_1.csv
* **Records:** 1,305 observations
* **Time Period:** January 2018 – December 2022
* **Key Variables:** 
   - Date
   - River System
   - pH Level
   - Temperature
   - Lead
   - Mercury
   - Arsenic
   - Nitrates
   - Phosphates
   - Dissolved Oxygen

---

## 3. Analysis Workflow

### Step 1: Environment Setup & Imports
Required libraries were imported for data manipulation, visualization, and statistical analysis:
   * `pandas` & `numpy` → data handling
   * `matplotlib` & `seaborn` → visualization
   * `scipy.stats` → hypothesis testing
   * `sklearn.linear_model` → linear regression
   * `statsmodels` → time-series decomposition

### Step 2: Data Loading
The dataset was loaded using `pd.read_csv()`.

### Step 3: Initial Data Exploration
- Examined the first few rows with `.head()`
- Checked data types and basic statistics with `.info()` and `.describe()`
- Identified the shape and structure of the data

### Step 4: Missing Value Handling
- Checked for missing values across all columns with `.isnull().sum()`
- Filled missing values in numeric columns only using mean imputation to preserve data integrity without introducing bias into categorical or date fields

### Step 5: Data Type Conversion
- Converted the Date column to proper datetime format to enable time-based analysis and visualization using `pd.to_datetime()`

### Step 6: Descriptive Statistics – Average Toxin Levels
Calculated the mean concentration of each toxin (Lead, Mercury, Arsenic) across the entire dataset to establish a global baseline.

**Key Observation:**
- Arsenic and Lead recorded the highest average numerical concentrations across the dataset
- Mercury concentrations were considerably lower in comparison

### Step 7: Ranking Most Polluted River Systems
Grouped the data by River_System and calculated average Lead concentrations. Sorted the results in descending order to identify the top polluted systems.

**Key Observation:**
- Yangtze and Mississippi recorded the highest average lead concentrations among the five river systems
- The Amazon recorded the lowest average lead concentration

### Step 8: Visualization of Average Lead Levels
Created a bar chart to compare average lead concentrations across the five river systems. This provided a clear visual representation of differences in average lead concentrations, making comparisons between river systems easier to interpret.

### Step 9: Temporal Analysis of Lead Concentrations (Jan 2018-Dec 2022)
Visualised lead concentrations over time using a line graph, comparing the five river systems to identify temporal fluctuations, potential trends, and notable variations throughout the observation period.

### Step 10: Correlation Analysis Between pH and Toxin Concentrations
Calculated Pearson correlation coefficients to examine the direction and strength of linear relationships between pH levels and lead, mercury and arsenic concentrations. This analysis helped assess whether changes in pH were associated with variations in individual toxin concentrations.

### Step 11: Correlation Heatmap of Environmental Parameters
Generated a correlation heatmap using Pearson correlation coefficients to visualise the strength and direction of linear relationships between numerical variables across the dataset, including toxin concentrations, pH, temperature, nitrates, phosphates and dissolved oxygen. This provided an overview of potential relationships between environmental parameters and helped identify correlations warranting further investigation.

### Step 12: Hypothesis Testing (Independent Samples T-Test)
Performed an independent two-sample t-test to compare average Lead concentrations between the Amazon and Nile river systems, assessing whether the observed difference was statistically significant.

**Results:**

- T-statistic ≈ -20.24
- P-value ≈ 1.34 × 10⁻⁶⁷ (Extremely low, near zero)
- Conclusion: The results provide strong statistical evidence of a significant difference in average Lead concentrations between the Amazon and Nile river systems, with the Nile recording the higher average.

### Step 13: Linear Regression Analysis

Fitted a simple linear regression model to examine the relationship between pH levels and Lead concentrations.

**Results:**

- Positive regression coefficient (≈ 0.803)
- Higher pH levels were associated with higher Lead concentrations.
- The model explained approximately 10.2% of the variation in Lead concentrations (R² ≈ 0.102), indicating limited explanatory power.

### Step 14: Conclusion & Interpretation

Synthesised findings from the analysis to draw key insights:

- Identified differences in average toxin concentrations across river systems.
- Highlighted the importance of river-specific environmental management strategies.
- Emphasised the value of continued monitoring of heavy metals and other water-quality parameters.

## 4. Tools & Techniques Used

| Technique                        | Purpose                                      |
|----------------------------------|----------------------------------------------|
| Descriptive Statistics           | Baseline understanding of toxin levels       |
| GroupBy Aggregation              | Compare river systems                        |
| Bar Charts & Line Graphs         | Visual communication of findings             |
| Independent Two-Sample T-Test    | Test for significant differences             |
| Linear Regression                | Explore relationship between pH and Lead     |
| Missing Value Imputation         | Ensure data quality                          |
| Datetime Conversion              | Enable temporal analysis                     |

## 5. Key Takeaways from the Approach

1. **Data Quality First** – Cleaning and handling missing values was performed early to ensure reliable results.
2. **Progressive Analysis** – Started with global averages → moved to system-level comparisons → applied statistical tests.
3. **Visualization + Statistics** – Combined visual storytelling with rigorous statistical testing.
4. **Actionable Insights** – Focused on findings that support real-world environmental decision-making.

## 6. Files Related to This Analysis

- Full interactive analysis: `Notebooks/Environmental Toxin Analysis in River Systems.ipynb`
- PDF report: `Docs/Environmental Toxin Analysis in River Systems (1).pdf`
- Visualization screenshots: `Assets/`
- Cleaned dataset: `Dataset/Clean/National_River_Toxin_Dataset_1.csv`

---

*This document outlines the structured analytical approach followed throughout the project.*