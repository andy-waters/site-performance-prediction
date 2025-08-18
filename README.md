# 🧠 Site Performance Prediction

This project predicts the likelihood of clinical trial sites completing their studies successfully using historical data from [ClinicalTrials.gov](https://clinicaltrials.gov/). It was developed as a hands-on, end-to-end ML project focused on real-world challenges in clinical trial operations.

---

## 📦 Project Structure

```
site-performance-prediction/
├── data/
│   ├── raw/
│   │   └── aact-data/                 # Extracted AACT pipe-delimited files
│   └── site_performance.csv          # Cleaned and enriched dataset
├── notebooks/
│   ├── 01_prepare_site_data.ipynb        # ETL: loads, joins, cleans AACT data
│   └── 02_model_site_performance.ipynb  # Modeling and evaluation
├── README.md                         # Project overview and instructions
```

---

## 📊 Problem Statement

Clinical trial site performance (completion vs. dropout) is critical to successful studies. By modeling historical data, we aim to:

- Identify high-risk sites *before activation*
- Surface factors that influence site success
- Support predictive trial planning

---

## 🧪 Data Source

Data is sourced from the [AACT (Aggregate Analysis of ClinicalTrials.gov)](https://aact.ctti-clinicaltrials.org/) public dataset:

- `studies.txt`, `facilities.txt`, `sponsors.txt`, etc.
- Pipe-delimited format
- Updated monthly by CTTI

---

## 🚀 How to Run

1. **Clone this repo** and download the AACT dataset  
   (see instructions at [AACT Download](https://aact.ctti-clinicaltrials.org/snapshots))  
2. **Extract AACT files** into `data/raw/aact-data/`
3. Open Jupyter and run:

```bash
jupyter notebook notebooks/01_prepare_site_data.ipynb
```

4. Then run the modeling notebook:

```bash
jupyter notebook notebooks/02_model_site_performance.ipynb
```

---

## 🤖 Models Used

- Random Forest Classifier
- Logistic Regression
- XGBoost (optional)
- Evaluation via Accuracy, Precision, Recall, F1, ROC-AUC

---

## 📈 Sample Features

| Feature Name        | Description                              |
|---------------------|------------------------------------------|
| `phase`             | Phase of the clinical trial              |
| `enrollment`        | Target enrollment number                 |
| `study_type`        | Interventional, Observational, etc.      |
| `location_country`  | Site location                            |
| `duration_days`     | Trial duration                           |
| `num_sites`         | Number of sites per study                |
| `site_status`       | Outcome label (Completed/Terminated)     |

---

## 📌 Output

- `site_performance.csv`: final dataset for modeling
- `.pkl` model file: saved trained model for reuse
- Performance plots and feature importance charts

---

## 📍 Next Steps

- ✅ Develop an interactive dashboard (e.g., Streamlit or Dash)
- 🔜 Publish a blog post or case study on this work
- 🔜 Add Docker + API for full deployment

---

## 🛠️ Possible Enhancements

- Incorporate SHAP or LIME for explainability
- Add hyperparameter tuning via Optuna or GridSearchCV
- Include a small synthetic dataset to make the repo self-contained

---

## 👨‍💻 Author

Andy Waters  
Sr. Director of Software Engineering

---

## 📜 License

MIT (or update as appropriate)
