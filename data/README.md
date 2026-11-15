# Data

**Source:** Differentiated Thyroid Cancer Recurrence, UCI Machine Learning Repository (ID 915)
https://archive.ics.uci.edu/dataset/915/differentiated+thyroid+cancer+recurrence

**DOI:** https://doi.org/10.24432/C5632J
**Licence:** CC BY 4.0 (redistribution allowed, so the CSV is included here)

**Citation:** Borzooei, S., & Tarokhian, A. (2023). Differentiated Thyroid Cancer Recurrence [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5632J

## File

`thyroid_recurrence.csv`: the original dataset, unmodified. To download it again, use the UCI link above and save it here under this name.

## Overview

- 383 records, 16 features, binary target `Recurred` (Yes/No)
- No missing values; 19 exact duplicate rows (364 records after removal)
- No patient ID or follow-up time column

## Preparation

Done in `notebooks/01_eda.ipynb` (the CSV itself is never changed): column names are cleaned, duplicates are removed before splitting, and `Response` is excluded because it is assessed at follow-up and leaks the outcome.

## Limitations

Small dataset that may not represent all thyroid cancer populations. For educational use only, not for clinical decisions.
