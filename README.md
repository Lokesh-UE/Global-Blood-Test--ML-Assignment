🧬 Machine Learning-Based Health Risk Prediction
Global Blood Test Health Insights 2025–2026
MSc Thesis | University of Europe for Applied Sciences
Supervisor: Prof. Dr. Raja Hashim Ali | Student: Lokesh Chamakuri
Date: May 2026
📋 Overview
Ensemble learning framework that integrates blood biomarker groups for accurate, explainable patient risk classification.
Dataset: Kaggle - Global Blood Test Health Insights 2025-2026
Size: 52,000+ samples | Features: 21 biomarkers | Targets: Binary + Multi-class
🔬 Research Questions
Table
RQ	Question
RQ1	Does ensemble fusion outperform single-feature models?
RQ2	Which feature groups dominate different clinical scenarios?
RQ3	Do feature interactions improve prediction under incomplete data?
RQ4	How effective are explainability techniques (SHAP, LIME)?
RQ5	How robust is the model under noise and missing data?
RQ6	Can uncertainty improve risk prioritization?
RQ7	Does the system improve real-world clinical decision quality?
🏗️ System Architecture
plain
Copy
┌────────────────────────────────────────┐
│         BLOOD TEST INPUT DATA          │
│  Demographics | Hematological | Lipid  │
│  Metabolic    | Inflammatory | Vital   │
└──────────────┬─────────────────────────┘
               │
    ┌──────────┼──────────┬──────────┐
    ▼          ▼          ▼          ▼
┌───────┐ ┌───────┐ ┌───────┐ ┌───────┐
│  RF   │ │  LR   │ │  SVM  │ │ XGB   │
│Hemato │ │Metabolic│ │ Lipid │ │Inflam │
└───┬───┘ └───┬───┘ └───┬───┘ └───┬───┘
    │         │         │         │
    └─────────┴────┬────┴─────────┘
                   ▼
        ┌─────────────────────┐
        │ CROSS-FEATURE       │
        │ ATTENTION LAYER     │
        └──────────┬──────────┘
                   ▼
        ┌─────────────────────┐
        │ STACKING ENSEMBLE   │
        │ (Meta-Learner: LR)  │
        └──────────┬──────────┘
                   ▼
        ┌─────────────────────┐
        │ UNCERTAINTY +       │
        │ CONFIDENCE SCORE    │
        └──────────┬──────────┘
                   ▼
        ┌─────────────────────┐
        │  RISK PREDICTION    │
        │  High_Risk (0/1)  │
        │  Risk_Category    │
        └─────────────────────┘
📁 Repository Structure
plain
Copy
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
├── figures/          # PDF outputs (300 DPI)
├── tables/           # CSV outputs
├── docs/             # Thesis proposal
├── requirements.txt
└── README.md
⚙️ Methodology
Table
Step	Description
1. Preprocessing	Imputation → Encoding → Scaling → SMOTE
2. Group Models	Separate model per biomarker group
3. Ensembles	Early Fusion / Late Fusion / Stacking / Voting
4. Interactions	Polynomial features + Attention mechanisms
5. Explainability	SHAP + LIME + Permutation + PDP
6. Robustness	Gaussian noise + Missing data simulation
7. Calibration	ECE + Brier Score for uncertainty
📊 Expected Results
Table
Metric	Value
Accuracy	95.8%
F1-Score	94.3%
ROC-AUC	0.987
Ensemble Gain	+13.4%
Top Risk Indicators: Age > 65 | Glucose > 126 | BP > 140/90
🚀 Quick Start
bash
Copy
pip install -r requirements.txt
jupyter notebook notebooks/RQ1_Model_Performance_Comparison.ipynb
Run in order: RQ1 → RQ2 → RQ3 → RQ4 → RQ5 → RQ6 → RQ7
📤 Submission 1 Deliverables
Table
Item	Location
Thesis Proposal	docs/Thesis_Proposal_Health_Risk_Prediction.docx
Code	notebooks/*.ipynb
Dataset	data/global_blood_test_dataset.csv
Figures	figures/*.pdf
Tables	tables/*.csv
📜 License
Academic and research purposes only. Not for clinical deployment.
Lokesh Chamakuri | May 2026
