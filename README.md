# 🏥 Scalable Healthcare Readmission Risk Prediction Pipeline

This project demonstrates a **real-world, scalable ML pipeline** for predicting 30-day unplanned hospital readmissions using **PySpark**, **SMOTE**, **XGBoost**, and **Delta Lake**, ending with interactive **Apache Superset dashboards**.

---

## 📌 Problem Statement

Hospital readmissions are costly — financially and in patient outcomes. Identifying high-risk patients early enables hospitals to intervene proactively.

Using **synthetic healthcare data modeled after California public records (2011–2023)**, this pipeline:

- Predicts likelihood of readmission
- Addresses class imbalance using **SMOTE**
- Generates explainable ML predictions
- Exports results to **Delta Lake**
- Visualizes insights using **Apache Superset**

---

## 📁 Project Structure

<details>
<summary>📂 Expand Project File Tree</summary>

```
scalable-readmission-pipeline/
├── Scalable_Healthcare_Readmission_Pipeline_PySpark_XGBoost_DeltaLake.ipynb  # Full notebook
├── allcauseunplanned30-dayhospitalreadmissionratecalifornia2011_2023.csv     # Raw dataset
├── 8dd44ad7-9e78-4c1a-9910-f58a47e402af-data-dictionary.csv                   # Column reference
├── readmission_model_data.csv                                                # Cleaned dataset
├── xgboost_predictions.csv                                                   # Prediction output
├── superset_visuals/                                                         # 📊 Visuals for dashboards
│   ├── dashboard_overview.png
│   ├── precision_recall_curve.png
│   ├── feature_importance_rf.png
│   └── feature_importance_xgb.png
└── README.md
```
</details>

---

## ⚙️ Pipeline Overview

| Step | Description |
|------|-------------|
| **1. Ingest Data** | Load raw hospital readmission data |
| **2. Clean & Transform** | Normalize columns, encode categories, engineer features |
| **3. Balance Classes** | Apply **SMOTE** to address severe class imbalance |
| **4. Train Models** | Run **Random Forest** and **XGBoost** with threshold tuning |
| **5. Export to Delta Lake** | Save model output for real-time querying |
| **6. Visualize** | Build dashboards with **Apache Superset** |

---

## 📊 Superset Dashboards

Predictions are exported to **Delta Lake**, queried directly inside Superset for interactive exploration.

### 📍 Dashboard Snapshots

- Prediction outcomes by payer type
- Readmission breakdown by comorbidity and age
- Precision-recall curve for model evaluation

📸 **Screenshots:**

![Dashboard Overview](superset_visuals/dashboard_overview.png)  
![Precision Recall Curve](superset_visuals/precision_recall_curve.png)

---

## 🧠 Feature Importance Visualizations

These charts explain what influenced model decisions — critical for clinical transparency and regulatory compliance.

### 🎯 Random Forest

![Random Forest Feature Importance](superset_visuals/feature_importance_rf.png)

---

### ⚡ XGBoost (Gain Score)

![XGBoost Feature Importance](superset_visuals/feature_importance_xgb.png)

---

## 🧪 Sample Prediction Output

| payer     | age_group | comorbidity_count | year | actual | predicted | probability |
|-----------|-----------|-------------------|------|--------|-----------|-------------|
| Self-Pay  | 65-84     | 0                 | 2021 | 0      | 1         | 0.543       |

---

## 🛠️ Technologies Used

- **PySpark** – Distributed ETL and ML processing  
- **XGBoost & RandomForest** – Tree-based modeling  
- **SMOTE** – Oversampling to fix imbalance  
- **Delta Lake** – Lakehouse storage for real-time querying  
- **Apache Superset** – BI-style dashboards  
- **Matplotlib** – Inline visualizations and explainability  

---

## 📚 Key Learnings

- How to build ML pipelines in **Spark** for healthcare
- Using **threshold tuning** to boost model recall
- Creating **auditable ML workflows** with Superset + Delta Lake
- Real-time predictions on structured health data  

---

## 🚀 Run It Yourself

1. Upload this repo into [Databricks Community Edition](https://community.cloud.databricks.com/)
2. Run the notebook: `Scalable_Healthcare_Readmission_Pipeline_...ipynb`
3. Export predictions to a Delta table
4. Open [Apache Superset](https://superset.apache.org/) and connect to the Delta table
5. Create your own dashboards or use the ones provided in `/superset_visuals`

---

## 🪪 License

MIT License © 2025 [Skyllar Savona](https://github.com/skysavona)
