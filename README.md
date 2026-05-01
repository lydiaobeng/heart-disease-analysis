# Heart Disease Risk Analysis — Cleveland Dataset

![Python](https://img.shields.io/badge/Python-3.x-blue) ![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange) ![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

## Overview

An end-to-end data analysis and machine learning project exploring which clinical features best predict heart disease using the UCI Cleveland Heart Disease dataset (303 patients, 13 features). The project includes exploratory data analysis, statistical significance testing, machine learning classification, and model evaluation with confidence intervals and precision-recall analysis.

**Research question:** Can we predict the presence of heart disease from routine clinical measurements, and which features matter most?

---

## Dataset

- **Source:** [UCI Machine Learning Repository — Heart Disease Dataset](https://archive.ics.uci.edu/dataset/45/heart+disease)
- **Originally published:** Detrano et al. (1989), Cleveland Clinic Foundation
- **Patients:** 303 (Cleveland cohort), 297 after cleaning
- **Features:** 13 clinical variables including age, cholesterol, blood pressure, chest pain type, and ECG results
- **Target:** Binary — presence (1) or absence (0) of heart disease

| Feature | Description |
|---------|-------------|
| `age` | Age in years |
| `sex` | 1 = male, 0 = female |
| `cp` | Chest pain type (1–4) |
| `trestbps` | Resting blood pressure (mmHg) |
| `chol` | Serum cholesterol (mg/dl) |
| `fbs` | Fasting blood sugar > 120 mg/dl |
| `restecg` | Resting ECG results |
| `thalach` | Maximum heart rate achieved |
| `exang` | Exercise-induced angina |
| `oldpeak` | ST depression induced by exercise |
| `slope` | Slope of peak exercise ST segment |
| `ca` | Number of major vessels coloured by fluoroscopy |
| `thal` | Thallium scintigraphy result (normal, fixed defect, reversible defect) |

---

## Methods

1. **Data cleaning** — handled 6 missing values in `ca` and `thal`, binarised target variable
2. **Exploratory Data Analysis** — distribution plots, correlation heatmap, feature vs outcome comparisons
3. **Statistical significance testing** — Mann-Whitney U tests comparing clinical features between outcome groups with p-values reported
4. **Modelling** — Logistic Regression and Random Forest classifiers with 5-fold cross-validation
5. **Model evaluation** — accuracy with 95% bootstrap confidence intervals (1,000 iterations), precision, recall, F1, F2 scores, confusion matrices, ROC-AUC and Precision-Recall curves

---

## Key Findings

- **Chest pain type (`cp`) and thallium scan result (`thal`)** were the strongest predictors of heart disease
- Patients with heart disease had significantly **lower maximum heart rate** (mean 139.1 vs 158.6 bpm, p<0.001)
- **ST depression** differed significantly between groups (mean 1.6 vs 0.6, p<0.001)
- **Cholesterol** showed only marginal significance (p=0.047), confirming its weak predictive value relative to other clinical features
- Asymptomatic chest pain was paradoxically the strongest indicator of disease — reflecting the clinical phenomenon of silent ischaemia
- Random Forest achieved **85% accuracy [95% CI: 76.63–93.33%]** with AUC 0.94 and F2 score 0.803
- Logistic Regression achieved **83% accuracy [95% CI: 73.33–91.67%]** with AUC 0.95 and F2 score 0.797

---

## Results

| Model | CV Accuracy | AUC | F1 | F2 | 95% CI |
|-------|------------|-----|----|----|--------|
| Logistic Regression | ~83% | 0.95 | 0.815 | 0.797 | [73.33–91.67%] |
| Random Forest | ~85% | 0.94 | 0.830 | 0.803 | [76.63–93.33%] |

*F2 score weights recall more heavily than precision — appropriate for clinical classification where false negatives carry greater cost than false positives.*

---

## How to Run

### Requirements
```
pandas
numpy
matplotlib
seaborn
scikit-learn
scipy
```

Install with:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy
```

### Steps
1. Clone this repository
2. Place `heart_disease_cleveland.csv` in a `data/` folder
3. Open `heart_disease_analysis.ipynb` in VS Code or Jupyter
4. Run all cells top to bottom

---

## Project Structure

```
heart-disease/
├── data/
│   └── heart_disease_cleveland.csv
├── images/
│   ├── eda_overview.png
│   ├── significance_table.png
│   ├── correlation_heatmap.png
│   ├── model_evaluation.png
│   ├── precision_recall.png
│   └── feature_importance.png
├── heart_disease_analysis.ipynb
├── requirements.txt
└── README.md
```

---

## Skills Demonstrated

`Python` `Pandas` `NumPy` `Matplotlib` `Seaborn` `Scikit-learn` `SciPy` `Logistic Regression` `Random Forest` `Bootstrap Confidence Intervals` `Mann-Whitney U Test` `ROC-AUC` `Precision-Recall` `F2 Score` `EDA` `Data Cleaning` `Statistical Testing` `Health Data Analytics`

---

## References

- Detrano, R., Janosi, A., Steinbrunn, W., Pfisterer, M., Schmid, J., Sandhu, S., ... & Froelicher, V. (1989). International application of a new probability algorithm for the diagnosis of coronary artery disease. *American Journal of Cardiology*, 64(5), 304–310.
- UCI Machine Learning Repository: https://archive.ics.uci.edu/dataset/45/heart+disease

---

## Author

**Lydia Obeng Bema**
[LinkedIn](https://www.linkedin.com/in/lydia-obeng-bema-93a647393) | [GitHub](https://github.com/lydiaobeng)


## Citation

If you use this work, please cite:

Obeng Bema, L. (2026). *Beyond Cholesterol: A Machine Learning Analysis of Heart Disease Predictors Using the UCI Cleveland Dataset* (Version 1.0.0). Zenodo. https://doi.org/10.5281/zenodo.19956655