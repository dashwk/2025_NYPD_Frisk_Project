# 2025_NYPD_Frisk_Project
Personal Project of Data Analysis/Data Science To Investigate Frisk Data in NYC 2025

**Full Report - [https://github.com/dashwk/2025_NYPD_Frisk_Project/blob/main/2025_frisk_report.pdf]** | **Jupyter Notebook - [https://github.com/dashwk/2025_NYPD_Frisk_Project/blob/main/sqf-2025.ipynb]**

## Summary

  This analysis proceeded in three steps to triangulate the central question from different angles. First, I calculated overall frisk rates by race and sex, finding substantial disparities: Black suspects represented the largest group by stop volume and were frisked at more than twice the rate of White suspects. Because raw gaps can reflect legitimate differences in stop circumstances rather than differential treatment, I then fit a series of logistic regression models that started with a baseline (the race of the suspect), and progressively added controls for demographic factors (sex and age), stop location and suspected crime, and officer-reported suspicion flags (including if the suspect was known to carry a weapon, etc). The racial gap in frisk probability shrank dramatically as controls were added, falling from roughly 29 percentage points in the unadjusted comparison to 3 percentage points and statistical insignificance in the full model.
  
  This finding does not establish the absence of racial bias. I show that the same controls that explain away the raw gap are themselves racially patterned: Black suspects are flagged for concealed weapon possession at roughly three times the rate of White suspects, and are stopped for suspected weapon possession at nearly three times the rate. "Controlling for" a racially patterned variable can absorb rather than explain the disparity it captures. To investigate further, I applied an outcome test on weapon recovery rates among frisked suspects. After accounting for stop context and stated suspicions, frisks of Black suspects recovered weapons 4.6 percentage points less often than frisks of White suspects (p = 0.006), a pattern consistent with officers applying a lower threshold of suspicion when deciding to frisk Black suspects. Taken together, the three analyses suggest that racial disparities in this dataset may operate less at the moment of the frisk decision itself than at the upstream decision of when to characterize a suspect as potentially armed.


## Methodology

This analysis uses a three-part strategy: descriptive frisk rate analysis, a logistic regression staircase that progressively adds controls, and an outcome test (hit rate analysis) based on Knowles, Persico, and Todd (2001).

See the full report for details on the data, methods, and findings.

## Repository contents

- `2025_frisk_report.pdf` — the full writeup
- `sqf-2025.ipynb` — the Jupyter notebook with all analysis code
- `sqf-2025.xlsx` — the source dataset (or a link to it if too large)

## Data source

NYPD Stop, Question, and Frisk Data, 2025, via NYC OpenData. [https://www.nyc.gov/site/nypd/stats/reports-analysis/stopfrisk.page]

## Tools

Python, pandas, statsmodels, matplotlib, seaborn.
