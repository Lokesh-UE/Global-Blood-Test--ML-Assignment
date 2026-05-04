🧬 Machine Learning-Based Health Risk Prediction
Global Blood Test Health Insights 2025–2026

🎓 MSc Thesis – University of Europe for Applied Sciences
👨‍🏫 Supervisor: Prof. Dr. Raja Hashim Ali
👨‍🎓 Student: Lokesh Chamakuri
📅 Date: May 2026

📋 Overview

This project presents an advanced ensemble learning framework for predicting patient health risks using blood test biomarkers.

The system integrates multiple biomarker groups and applies stacking, attention mechanisms, and explainable AI techniques to achieve:

High prediction accuracy
Robust performance under uncertainty
Clinically interpretable results
📊 Dataset
Source: Kaggle – Global Blood Test Health Insights 2025–2026
Samples: 52,000+
Features: 21 biomarkers
Targets:
Binary classification (High Risk: 0/1)
Multi-class risk categorization
🔬 Research Questions
ID	Question
RQ1	Does ensemble fusion outperform single-feature models?
RQ2	Which feature groups dominate different clinical scenarios?
RQ3	Do feature interactions improve prediction under incomplete data?
RQ4	How effective are explainability techniques (SHAP, LIME)?
RQ5	How robust is the model under noise and missing data?
RQ6	Can uncertainty improve risk prioritization?
RQ7	Does the system improve real-world clinical decision quality?
🏗️ System Architecture
BLOOD TEST INPUT DATA
(Demographics | Hematological | Lipid | Metabolic | Inflammatory | Vital)

        ↓
 ┌─────────────── Models ───────────────┐
 │   RF   |   LR   |   SVM   |   XGB    │
 │ Hemato | Metab |  Lipid  | Inflam   │
 └───────────────┬─────────────────────┘
                 ↓
      CROSS-FEATURE ATTENTION LAYER
                 ↓
         STACKING ENSEMBLE
        (Meta-Learner: Logistic Regression)
                 ↓
     UNCERTAINTY + CONFIDENCE SCORING
                 ↓
          FINAL RISK PREDICTION
📁 Repository Structure
├── data/
│   └── global_blood_test_dataset.csv
├── notebooks/
│   ├── RQ1_Model_Performance_Comparison.ipynb
│   ├── RQ2_Feature_Contribution.ipynb
│   ├── RQ3_Cross_Feature_Interaction.ipynb
│   ├── RQ4_Explainability.ipynb
│   ├── RQ5_Robustness.ipynb
│   ├── RQ6_Uncertainty_Scoring.ipynb
│   └── RQ7_End_to_End_Evaluation.ipynb
├── figures/        # High-quality visual outputs (PDF, 300 DPI)
├── tables/         # Experimental results (CSV)
├── docs/           # Thesis documentation
├── requirements.txt
└── README.md
⚙️ Methodology
Step	Description
1	Preprocessing: Imputation → Encoding → Scaling → SMOTE
2	Group Models: Separate models per biomarker group
3	Ensembles: Early Fusion / Late Fusion / Stacking / Voting
4	Interactions: Polynomial features + Attention mechanisms
5	Explainability: SHAP, LIME, Permutation Importance, PDP
6	Robustness: Noise injection + Missing data simulation
7	Calibration: Expected Calibration Error (ECE), Brier Score
📊 Expected Results
Metric	Value
Accuracy	95.8%
F1-Score	94.3%
ROC-AUC	0.987
Ensemble Gain	+13.4%

Top Risk Indicators:

Age > 65
Glucose > 126 mg/dL
Blood Pressure > 140/90
🚀 Quick Start
# Install dependencies
pip install -r requirements.txt

# Launch notebooks
jupyter notebook notebooks/RQ1_Model_Performance_Comparison.ipynb

👉 Run notebooks in order:
RQ1 → RQ2 → RQ3 → RQ4 → RQ5 → RQ6 → RQ7

📤 Submission Deliverables
Item	Location
Thesis Proposal	docs/Thesis_Proposal_Health_Risk_Prediction.docx
Code	notebooks/*.ipynb
Dataset	data/global_blood_test_dataset.csv
Figures	figures/*.pdf
Tables	tables/*.csv
⚠️ Disclaimer

This project is intended for academic and research purposes only.
It is not approved for clinical or medical deployment.

📜 License

Academic Use Only
