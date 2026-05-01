# Heart Disease Risk Analysis — Cleveland Dataset

![Python](https://img.shields.io/badge/Python-3.x-blue) ![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange) ![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

## Overview

An end-to-end data analysis and machine learning project exploring which clinical features best predict heart disease using the well-known UCI Cleveland Heart Disease dataset (303 patients, 13 features).

**Research question:** Can we predict the presence of heart disease from routine clinical measurements, and which features matter most?

---

## Dataset

- **Source:** [UCI Machine Learning Repository — Heart Disease Dataset](https://archive.ics.uci.edu/dataset/45/heart+disease)
- **Patients:** 303 (Cleveland cohort)
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
| `thal` | Thalassemia type |

---

## Methods

1. **Data cleaning** — handled 6 missing values in `ca` and `thal`, binarised target variable
2. **Exploratory Data Analysis** — distribution plots, correlation heatmap, feature vs outcome comparisons
3. **Modelling** — Logistic Regression and Random Forest classifiers with 5-fold cross-validation
4. **Evaluation** — accuracy, precision, recall, F1-score, confusion matrix, ROC-AUC curves

---

## Key Findings

- **Thalassemia type (`thal`) and vessels coloured (`ca`)** were the strongest predictors of heart disease
- Patients with heart disease had significantly **lower maximum heart rate** (mean ~139 bpm vs ~158 bpm)
- **Asymptomatic chest pain** (type 4) was paradoxically the strongest indicator of disease presence
- **Cholesterol** showed surprisingly weak predictive power — similar distributions across both groups
- Random Forest achieved **~85% accuracy** and **AUC ~0.92**; Logistic Regression ~83% accuracy and AUC ~0.90

---

## Results

| Model | CV Accuracy | AUC |
|-------|------------|-----|
| Logistic Regression | ~83% | ~0.90 |
| Random Forest | ~85% | ~0.92 |

---

## How to Run

### Requirements
```
pandas
numpy
matplotlib
seaborn
scikit-learn
```

Install with:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
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
│   ├── correlation_heatmap.png
│   ├── model_evaluation.png
│   └── feature_importance.png
├── heart_disease_analysis.ipynb
├── requirements.txt
└── README.md
```

---

## Skills Demonstrated

`Python` `Pandas` `NumPy` `Matplotlib` `Seaborn` `Scikit-learn` `Logistic Regression` `Random Forest` `ROC-AUC` `EDA` `Data Cleaning` `Machine Learning` `Health Data Analytics`

---

## Author

**[Your Name]**  
[LinkedIn](https://linkedin.com/in/yourprofile) | [GitHub](https://github.com/yourusername)

*Independent student building a health data analytics portfolio using open datasets and free tools.*
