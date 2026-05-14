# 🫀 CardioGuard AI: Precision Heart Disease Prediction Pipeline

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange?logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-informational?logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

> **"Leveraging advanced clinical analytics to bridge the gap between reactive treatment and proactive cardiovascular diagnostics."**

---

## 📖 1. Project Overview
Cardiovascular diseases (CVDs) are the leading cause of death globally, taking an estimated 17.9 million lives each year. Early detection is not just a technical challenge—it is a critical necessity for survival.

This project implements a robust **Binary Classification Pipeline** designed to predict the likelihood of heart disease based on clinical biomarkers. By integrating automated preprocessing, exploratory data insight, and ensemble-ready modeling, this repository serves as a blueprint for high-reliability medical diagnostic systems.

---

## 🎯 2. Task Objective
As part of the **AI/ML Internship at 𝐃𝐞𝐯𝐞𝐥𝐨𝐩𝐞𝐫𝐬𝐇𝐮𝐛 𝐂𝐨𝐫𝐩𝐨𝐫𝐚𝐭𝐢𝐨𝐧**, the objective was to:
*   Develop a reproducible ML workflow using Scikit-Learn Pipelines.
*   Achieve high **Recall** and **ROC-AUC** scores to minimize clinical False Negatives.
*   Analyze feature importance to provide "Glass-Box" interpretability for medical practitioners.

---

## 📊 3. Dataset Section
The model is trained on the **Heart Failure Prediction Dataset**, a synthesized collection of five datasets previously available independently but not combined.

### Clinical Features
| Feature | Type | Description |
| :--- | :--- | :--- |
| **Age** | Numeric | Age of the patient [years] |
| **Sex** | Categorical | M: Male, F: Female |
| **ChestPainType** | Categorical | TA: Typical Angina, ATA: Atypical Angina, NAP: Non-Anginal Pain, ASY: Asymptomatic |
| **RestingBP** | Numeric | Resting blood pressure [mm Hg] |
| **Cholesterol** | Numeric | Serum cholesterol [mm/dl] |
| **FastingBS** | Binary | Fasting blood sugar [1: if FastingBS > 120 mg/dl, 0: otherwise] |
| **RestingECG** | Categorical | Normal, ST: ST-T wave abnormality, LVH: Left ventricular hypertrophy |
| **MaxHR** | Numeric | Maximum heart rate achieved [Numeric value between 60 and 202] |
| **ExerciseAngina** | Binary | Exercise-induced angina [Y: Yes, N: No] |
| **Oldpeak** | Numeric | ST depression induced by exercise relative to rest |
| **ST_Slope** | Categorical | Up, Flat, Down |
| **HeartDisease** | **Target** | 1: Presence of heart disease, 0: Normal |

**Preprocessing Insight:** Zero values in `Cholesterol` and `RestingBP` were identified as biological impossibilities and handled via **NaN-conversion followed by iterative median imputation** within the pipeline to prevent data leakage.

---

## 🛠️ 4. Tech Stack
*   **Core**: `Python 3.12`
*   **Data Science**: `Pandas`, `NumPy`
*   **Machine Learning**: `Scikit-Learn` (Pipelines, ColumnTransformers)
*   **Visualizations**: `Matplotlib`, `Seaborn` (Heatmaps, Histograms, ROC Curves)
*   **Model Management**: `Joblib`

---

## 🔄 5. Machine Learning Workflow
This project adheres to a senior-level **Standardized Engineering Workflow**:

1.  **Data Validation**: Column stripping, duplicate checks, and data type verification.
2.  **Clinical Cleaning**: Transformation of "0" markers in biomarkers to `np.nan` to ensure statistical integrity.
3.  **Automated Preprocessing Pipeline**:
    *   **Numerical Path**: Median Imputation + Standard Scaling.
    *   **Categorical Path**: Constant Imputation + One-Hot Encoding (drop first to prevent multicollinearity).
4.  **Stratified Splitting**: 80/20 train-test split with seed-locking for reproducibility.
5.  **Comparative Training**: Evaluating Logistic Regression (Baseline) against non-linear Decision Trees.
6.  **Threshold Tuning**: Analyzing the precision-recall tradeoff to optimize for medical sensitivity.

---

## 🤖 6. Models Used
| Model | Rationale | Advantage |
| :--- | :--- | :--- |
| **Logistic Regression** | Baseline clinical model. | High interpretability; provides log-odds for risk factors. |
| **Decision Tree** | Captures non-linear dependencies. | Effectively models interactions between variables like Age and MaxHR. |

**Final Selection:** The **Logistic Regression** model with `StandardScaler` was prioritized for its superior generalization and resistance to overfitting on a 918-row dataset.

---

## 📏 7. Evaluation Metrics (Clinical Context)
In healthcare, **Recall (Sensitivity)** is the "North Star" metric.
*   **Recall**: We prioritize identifying every positive case. A False Positive results in a follow-up test; a False Negative results in a missed life-saving intervention.
*   **ROC-AUC**: Measures the model's ability to distinguish between classes regardless of the probability threshold.
*   **F1-Score**: Balancing Precision and Recall for robust diagnostic performance.

---

## 💡 8. Key Results & Findings
*   **Performance**: The pipeline achieved a consistent **ROC-AUC of ~0.90**, indicating high discriminative power.
*   **Generalization**: Cross-validation scores remained within 2% of test scores, confirming that the model did not memorize the training data.
*   **Medical Insight**: `ST_Slope_Flat` and `ExerciseAngina_Y` were identified as the strongest predictors of heart disease, aligning with cardiology literature.
*   **Overfitting Prevention**: Used `SimpleImputer` and `StandardScaler` strictly within the `Pipeline` object to ensure no training statistics leaked into the test set.

---

## 🎨 9. Visualizations
The analysis includes comprehensive visuals to support data transparency:
*   **Correlation Matrix**: Visualizing multi-collinearity between clinical features.
*   **Target Class Distribution**: Confirming dataset balance (~55% Positive cases).
*   **Confusion Matrix**: Deep dive into the distribution of Type I and Type II errors.
*   **ROC Curve**: Evaluating the True Positive Rate against the False Positive Rate.

---

## 🛡️ 11. Responsible AI & Ethics
*   **Medical Disclaimer**: This tool is for research and educational purposes only. It is **not** a clinical diagnostic tool.
*   **Limitations**: The model is trained on a specific population size; performance may vary across different demographic distributions not represented in the 918 samples.
*   **Fairness**: Feature importance was analyzed to ensure the model does not rely solely on demographic proxies like `Age` or `Sex` without clinical justification.
*   **Human-in-the-loop**: This AI should serve as an "Assisted Intelligence" layer to alert doctors, not replace professional judgment.

---

## 📂 12. Project Structure
```text
Heart Disease Prediction/
│── heart-disease-prediction.ipynb    # Full End-to-End Pipeline
│── heart_disease_model.joblib        # Serialized Production Model
│── README.md                         # Technical Documentation

```

---

## 🚀 13. Installation & Usage
1.  **Install dependencies:**
    ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn joblib
    ```
2.  **Execute the analysis:**
    Open `heart-disease-prediction.ipynb` in Jupyter or VS Code and run all cells.

---

## 🔮 14. Future Improvements
*   **SHAP Implementation**: Adding SHAP values for local instance explanation (why *this* specific patient was flagged).
*   **Ensemble Methods**: Integrating XGBoost or LightGBM to improve ROC-AUC.
*   **Deployment**: Wrapping the model in a **Streamlit** dashboard for real-time risk assessment.
*   **Deep Learning**: Exploring Neural Networks if larger datasets become available.

---

## 🏁 15. Final Conclusion
This project successfully demonstrates the transition from raw clinical data to a structured, production-ready diagnostic pipeline. By focusing on **Recall** and **Interpretable Pipelines**, the resulting model offers high utility for cardiovascular risk assessment. The engineering maturity shown in the preprocessing and validation stages ensures that this model generalizes well to unseen clinical environments.

---
**Developed with ❤️ by Aneeb-Ur-Rehman during the AI/ML Internship at 𝐃𝐞𝐯𝐞𝐥𝐨𝐩𝐞𝐫𝐬𝐇𝐮𝐛 𝐂𝐨𝐫𝐩𝐨𝐫𝐚𝐭𝐢𝐨𝐧 .**
