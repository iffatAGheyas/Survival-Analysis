# Survival Analysis Project

This repository contains a complete survival-analysis workflow on the built-in Lung Cancer dataset from `lifelines`. It includes data preprocessing, exploratory analyses, Cox proportional hazards models (standard, stratified, and time-varying), model diagnostics, personalized predictions, and summary outputs.

---

## 📂 Project Structure

SurvivalAnalysis/
├── README.md ← this file
├── SurvivalAnalysis1.ipynb ← Jupyter notebook with all code
├── Datasets/
│ ├── lung_dataset.xlsx ← raw data from lifelines.datasets
│ └── lung_dataset_processed1.xlsx ← preprocessed & imputed data
├── Models/
│ ├── lung_cox_forward_model.pkl ← final time-independent CoxPH
│ ├── lung_cox_stratified_model.pkl ← stratified CoxPH (sex)
│ ├── lung_cox_stratified_simple_model.pkl← simplified stratified CoxPH
│ └── lung_cox_timevarying_model.pkl ← time-varying CoxPH
└── Outputs/
├── Tables/
│ ├── life_table_actuarial.xlsx
│ ├── lung_cox_forward_summary.xlsx
│ ├── lung_cox_stratified_simple_summary.xlsx
│ ├── lung_cox_stratified_summary.xlsx
│ ├── lung_cox_timevarying_summary.xlsx
│ └── martingale_linearity_results.xlsx
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

![image](https://github.com/user-attachments/assets/456631b5-6b8d-48c8-b43d-a89753645c43)
![image](https://github.com/user-attachments/assets/e4e126af-3619-44c0-b902-19db82eb7fb8)
![image](https://github.com/user-attachments/assets/6e1ad89b-762d-4f28-ba14-0c1a92fb7b1e)
📜 License
MIT License — feel free to adapt or fork for your own learning.


