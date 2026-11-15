# Thyroid Cancer Recurrence Prediction

Machine learning project (CT4101, University of Galway) predicting recurrence of differentiated thyroid cancer from demographic and clinicopathological features.

**Repository:** https://github.com/TravisArnt/thyroid-recurrence-prediction

## Research Question

Can demographic and clinicopathological features be used to classify whether a patient with differentiated thyroid cancer will experience recurrence?

## Dataset

- **Name:** Differentiated Thyroid Cancer Recurrence
- **Source:** UCI Machine Learning Repository (ID 915), https://archive.ics.uci.edu/dataset/915/differentiated+thyroid+cancer+recurrence
- **DOI:** 10.24432/C5632J
- **Licence:** CC BY 4.0
- **Size:** 383 records, 16 input features, binary target `Recurred` (364 records after removing 19 exact duplicates)

The CSV is included in `data/` (permitted by the licence). See `data/README.md` for details.

## Approach

- **Task:** binary classification (recurrence: yes/no)
- **Prediction setting:** information available after initial surgery and pathology. `Response` (assessed at follow-up) is excluded to avoid data leakage.
- **Split:** stratified 80/20 train/test; stratified 5-fold CV on the training set for comparison and tuning. The test set is used once, for final evaluation.
- **Models:** Dummy baseline, Logistic Regression, Decision Tree (spot-check only), Random Forest, XGBoost, Neural Network (MLPClassifier)
- **Metrics:** ROC-AUC, PR-AUC, precision, recall, F1, confusion matrix
- **Analysis:** error analysis by subgroup and permutation feature importance

## Current Results (draft, Milestone 3)

XGBoost is the current best model (test ROC-AUC 0.904, PR-AUC 0.868, recall 0.77, precision 0.74), but the top models differ by about one patient on a 73-patient test set. See the notebook for the full results table and discussion.

## Project Structure

```
data/                  dataset and data README
notebooks/01_eda.ipynb EDA, preprocessing, modelling, evaluation, error analysis
requirements.txt       package versions
```

## Setup and Run

Requires **Python 3.11**.

```bash
git clone https://github.com/TravisArnt/thyroid-recurrence-prediction.git
cd thyroid-recurrence-prediction
python3.11 -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

Then open `notebooks/01_eda.ipynb` in VS Code or Jupyter, select the `.venv` kernel and choose **Run All**. The notebook reads `../data/thyroid_recurrence.csv`, so run it from the `notebooks/` folder.

**macOS note:** if XGBoost fails to import, install the OpenMP runtime with `brew install libomp`. If you use Anaconda, build the environment with a non-conda Python.

## Responsible ML

The dataset is small and may not represent all thyroid cancer populations; no follow-up time or patient ID is available. The model relies mainly on the clinician-assigned risk category. This project is for educational purposes and must not be used as a clinical decision-support system.

## Assistance Declaration

- **Generative AI:** Claude (Anthropic) was used for guidance on the milestone requirements and notebook structure, suggested code for the baseline, MLP pipeline, results table, error analysis and feature importance, drafting interpretation text, and debugging the environment setup. I reviewed, ran and understand all submitted code and results.
- **External code:** scikit-learn and XGBoost documentation; the MLPClassifier example from the CT4101 lecture slides.
- **Collaboration:** none.

## Citation

Borzooei, S., & Tarokhian, A. (2023). Differentiated Thyroid Cancer Recurrence [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5632J