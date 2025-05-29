# Survival Analysis Project

This repository contains a complete survival-analysis workflow on the built-in Lung Cancer dataset from `lifelines`. It includes data preprocessing, exploratory analyses, Cox proportional hazards models (standard, stratified, and time-varying), model diagnostics, personalized predictions, and summary outputs.

---

## 📂 Project Structure

```text
SurvivalAnalysis/
├── README.md                             ← this file
├── SurvivalAnalysis1.ipynb               ← Jupyter notebook with all code
├── Datasets/
│   ├── lung_dataset.xlsx                 ← raw data from lifelines.datasets
│   └── lung_dataset_processed1.xlsx      ← preprocessed & imputed data
├── Models/
│   ├── lung_cox_forward_model.pkl        ← final time-independent CoxPH
│   ├── lung_cox_stratified_model.pkl     ← stratified CoxPH (sex)
│   ├── lung_cox_stratified_simple_model.pkl  ← simplified stratified CoxPH
│   └── lung_cox_timevarying_model.pkl     ← time-varying CoxPH
└── Outputs/
    ├── Tables/
    │   ├── life_table_actuarial.xlsx
    │   ├── lung_cox_forward_summary.xlsx
    │   ├── lung_cox_stratified_simple_summary.xlsx
    │   ├── lung_cox_stratified_summary.xlsx
    │   ├── lung_cox_timevarying_summary.xlsx
    │   └── martingale_linearity_results.xlsx
    └── Plots/
        ├── baseline_surv_cumhaz_subplots.png
        ├── calibration_plot_1y.png
        ├── km_overall.png
        ├── km_by_sex.png
        ├── life_table_actuarial_survival.png
        ├── lung_cox_stratified_forest_plot.png
        ├── martingale_meal.cal.png
        ├── martingale_pat.karno.png
        ├── martingale_ph.ecog.png
        ├── partial_effect_meal_cal.png
        ├── partial_effect_pat_karno.png
        ├── partial_effect_ph_ecog.png
        ├── partial_effect_sex.png
        ├── schoenfeld_meal.cal.png
        ├── schoenfeld_pat.karno.png
        ├── schoenfeld_ph.ecog.png
        └── schoenfeld_sex.png


---

## 🔗 GitHub Wiki

For detailed theoretical background on each method (Kaplan–Meier, CoxPH, life tables, residual diagnostics, etc.), see our project Wiki:

👉 https://github.com/iffatAGheyas/Survival-Analysis/wiki

You can clone the Wiki locally with:

```bash
git clone https://github.com/iffatAGheyas/Survival-Analysis.wiki.git

🚀 Overview of Analysis
Data Loading & Preprocessing

Imported lifelines.datasets.load_lung (228 patients, 10 columns).

Kept: time, status (0=censored, 1=death), and covariates age, sex, ph.ecog, ph.karno, pat.karno, meal.cal, wt.loss.

Converted sex from {1=male, 2=female} → {1, 0}.

Imputed missing values with K-Nearest Neighbors.

Standard CoxPH with Forward Selection

Univariate c-index screening to seed; forward‐step addition to maximize c-index.

Final model saved as Models/lung_cox_forward_model.pkl.

Diagnostics: Schoenfeld (PH), Martingale (linearity), log-rank test.

Advanced Cox Models

Time-varying CoxPH (lung_cox_timevarying_model.pkl).

Stratified CoxPH on sex with time-interaction (lung_cox_stratified_model.pkl).

Simplified Stratified CoxPH (lung_cox_stratified_simple_model.pkl).

Evaluated by in-sample & 5-fold CV c-index, calibration, forest & partial-effect plots, personalized survival/hazard predictions.

Kaplan–Meier & Life Tables

Overall & stratified KM curves (km_overall.png, km_by_sex.png).

Actuarial life-table intervals & survival estimate (life_table_actuarial.xlsx, life_table_actuarial_survival.png).

📖 How to Use
Clone this repository.

Open SurvivalAnalysis1.ipynb in Jupyter.

Run cells in order — all data, models, and outputs will be written into the Datasets/, Models/, and Outputs/ subfolders.

View detailed method explanations on the project Wiki.

🛠 Requirements
Python ≥ 3.8
Jupyter Notebook or JupyterLab 
lifelines

pandas, numpy, matplotlib, patsy, scikit-learn
📜 License
MIT License — feel free to adapt or fork for your own learning.


