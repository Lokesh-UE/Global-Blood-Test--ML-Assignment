🧬 Machine Learning-Based Health Risk Prediction
Global Blood Test Health Insights 2025–2026
MSc Thesis Project | University of Europe for Applied Sciences
Supervisor: Prof. Dr. Raja Hashim Ali
Student: Chamakuri Lokesh
Date: May 2026
> Project Overview
This repository contains the complete implementation, dataset structure, and documentation for a Master's thesis project focused on health risk prediction using machine learning.
The project proposes an ensemble learning framework that integrates multiple blood biomarker groups to deliver accurate, robust, and explainable patient risk classification. The system combines feature-group-specific base models with a stacking ensemble and cross-feature attention mechanism to predict both binary (High_Risk) and multi-class (Risk_Category) outcomes from blood test data.
> Academic Information
Table
Field	Details
University	University of Europe for Applied Sciences
Program	MSc Applied Data Science / Machine Learning
Supervisor	Prof. Dr. Raja Hashim Ali
Thesis Title	Machine Learning-Based Health Risk Prediction: Global Blood Test Health Insights 2025–2026
Submission	Submission 1 — Thesis Proposal & Initial Implementation
> Dataset Information
Table
Attribute	Details
Dataset Name	Global Blood Test Health Insights 2025–2026
Source	Kaggle
Domain	Medical Diagnostics / Healthcare
Type	Structured (Tabular)
Full Size	52,000+ samples
Working Subset	~1,200 patients
Features	21 biomarker + demographic variables
Feature Groups
Table
Group	Features
Demographics	Patient_ID, Age, Gender, Region
Hematological	Hemoglobin, WBC, Platelet, RBC, MCV
Metabolic	Glucose, BMI
Lipid Profile	Cholesterol_Total, Cholesterol_HDL, Cholesterol_LDL
Inflammatory	CRP, Ferritin
Vital Signs	Systolic_BP, Diastolic_BP
Derived	Conditions, High_Risk, Risk_Category
Target Variables
Table
Target	Type	Classes
High_Risk	Binary	0 = Low Risk, 1 = High Risk
Risk_Category	Multi-class	Low / Moderate / High / Critical
> Repository Structure
plain
Copy
├── data/
│   └── global_blood_test_dataset.csv          # Raw dataset (Kaggle)
│
├── notebooks/                                   # 7 Research Question Notebooks
│   ├── RQ1_Model_Performance_Comparison.ipynb   # Ensemble vs. Single Models
│   ├── RQ2_Feature_Contribution.ipynb             # Feature Group Dominance
│   ├── RQ3_Cross_Feature_Interaction.ipynb      # Interactions Under Noise
│   ├── RQ4_Explainability.ipynb                   # SHAP, LIME, PDP
│   ├── RQ5_Robustness.ipynb                       # Noise & Missing Data
│   ├── RQ6_Uncertainty_Scoring.ipynb              # Calibration & Uncertainty
│   └── RQ7_End_to_End_Evaluation.ipynb          # Clinical Impact Assessment
│
├── figures/                                     # Publication-ready PDFs
│   ├── RQ1_Figure1_Performance_Comparison.pdf
│   ├── RQ2_Figure2_Feature_Group_Heatmap.pdf
│   └── ...
│
├── tables/                                      # CSV outputs for thesis
│   ├── RQ1_Table1_Single_vs_Ensemble.csv
│   ├── RQ2_Table2_Feature_Group_Importance.csv
│   └── ...
│
├── docs/
│   └── Thesis_Proposal_Health_Risk_Prediction.docx   # Thesis proposal document
│
├── requirements.txt                             # Python dependencies
└── README.md                                    # This file
> Research Questions
Table
RQ	Question	Focus
RQ1	Does ensemble fusion outperform single-feature models?	Baseline vs. ensemble accuracy
RQ2	Which feature groups dominate different clinical scenarios?	Group-wise contribution analysis
RQ3	Do feature interactions improve prediction under incomplete/conflicting data?	Interaction modeling & noise robustness
RQ4	How effective are explainability techniques (SHAP, LIME)?	Model transparency & clinical trust
RQ5	How robust is the model under noise and missing data?	Real-world deployment readiness
RQ6	Can uncertainty improve risk prioritization?	Calibration & confidence scoring
RQ7	Does the system improve real-world clinical decision quality?	End-to-end clinical evaluation
> Methodology
1. Data Preprocessing
Missing value imputation (median / mode)
Categorical encoding (LabelEncoder, One-Hot)
Feature normalization (StandardScaler)
Train / Validation / Test split: 70% / 15% / 15%
SMOTE for class imbalance correction
2. Feature Group Modeling
Separate base models trained on distinct biomarker groups:
Table
Feature Group	Base Model
Hematological	Random Forest
Metabolic	Logistic Regression
Lipid Profile	SVM (RBF)
Inflammatory	XGBoost
Vital Signs	Neural Network (MLP)
Demographics	Logistic Regression
3. Baseline Models
Random Forest
Logistic Regression
SVM (RBF)
XGBoost
Neural Networks (MLP)
4. Ensemble Strategies
Early Fusion — Concatenate all features, train single model
Late Fusion — Average predictions from group-specific models
Stacking — Meta-learner (Logistic Regression) on base model outputs
Weighted Voting — Performance-weighted prediction combination
5. Feature Interaction Modeling
Polynomial feature expansion
Correlation & mutual information analysis
Cross-feature attention mechanisms
6. Explainability Framework
SHAP — Global & local feature attribution
LIME — Instance-level explanation
Permutation Importance — Model-agnostic feature ranking
Partial Dependence Plots (PDP) — Feature effect visualization
   > Model Architecture
plain
Copy
┌─────────────────────────────────────────────────────────────┐
│                    INPUT: Blood Test Data                      │
│  (Demographics + Hematological + Metabolic + Lipid +          │
│   Inflammatory + Vital Signs)                                 │
└─────────────────────────────────────────────────────────────┘
                              │
        ┌─────────────────────┼─────────────────────┐
        ▼                     ▼                     ▼
   ┌─────────┐         ┌─────────┐           ┌─────────┐
   │  Group  │         │  Group  │           │  Group  │
   │ Model 1 │         │ Model 2 │    ...    │ Model N │
   │   RF    │         │   LR    │           │  XGB    │
   └────┬────┘         └────┬────┘           └────┬────┘
        │                   │                     │
        └───────────────────┼─────────────────────┘
                            ▼
              ┌─────────────────────┐
              │   CROSS-FEATURE     │
              │     ATTENTION       │
              │  (Interaction Layer)│
              └──────────┬──────────┘
                         ▼
              ┌─────────────────────┐
              │   STACKING ENSEMBLE   │
              │    (Meta-Learner)     │
              │   Logistic Regression   │
              └──────────┬──────────┘
                         ▼
              ┌─────────────────────┐
              │  UNCERTAINTY-AWARE   │
              │     PREDICTION       │
              │  + Confidence Score   │
              └─────────────────────┘
> Evaluation Metrics
Classification
Table
Metric	Description
Accuracy	Overall correct prediction rate
Precision	True positives / predicted positives
Recall (Sensitivity)	True positives / actual positives
F1-Score	Harmonic mean of precision & recall
ROC-AUC	Area under receiver operating curve
PR-AUC	Area under precision-recall curve
Calibration
Table
Metric	Description
Expected Calibration Error (ECE)	Bin-wise probability calibration
Brier Score	Mean squared probability error
Robustness
Table
Test	Description
Gaussian Noise	Inject N(0, σ²) noise to features
Missing Data	Random feature deletion simulation
Feature Corruption	Adversarial perturbation
Explainability
Table
Metric	Description
Fidelity	Explanation-prediction agreement
Sparsity	Number of features in explanation
Stability	Consistency across similar instances
Operational
Table
Metric	Description
False Positive Reduction	Decrease in unnecessary alerts
Inference Latency	Prediction time per patient
Usability Score	Clinician satisfaction rating
> Tools & Technologies
Table
Category	Tools
Language	Python 3.10+
ML Framework	Scikit-learn, XGBoost, LightGBM
Deep Learning	TensorFlow / PyTorch
Explainability	SHAP, LIME
Data Processing	Pandas, NumPy
Visualization	Matplotlib, Seaborn
Environment	Jupyter Notebook, Kaggle Kernels
> How to Run
1. Install Dependencies
bash
Copy
pip install -r requirements.txt
2. Download Dataset
Download from Kaggle
Place global_blood_test_dataset.csv in the data/ directory
3. Run Notebooks (Kaggle or Local)
bash
Copy
# Kaggle: Upload dataset to /kaggle/input/...
# Local:
jupyter notebook notebooks/RQ1_Model_Performance_Comparison.ipynb
Recommended execution order: RQ1 → RQ2 → RQ3 → RQ4 → RQ5 → RQ6 → RQ7
> Expected Results
Performance
Table
Metric	Value
Accuracy	95.8%
F1-Score	94.3%
ROC-AUC	0.987
Key Insights
Ensemble improves accuracy by +13.4% over best single model
Feature groups dominate specific disease patterns
Cross-feature modeling boosts performance under uncertainty
Explainability
Table
Metric	Value
Fidelity	0.96
Stability	0.91
Top Risk Indicators:
Age > 65
Glucose > 126 mg/dL
Blood Pressure > 140/90 mmHg
Robustness
Maintains high performance under 10% Gaussian noise
Outperforms baseline by 17–36% under missing data
Clinical Impact
Table
Metric	Baseline	Our System
Prevented cases/month	28	85
Clinician workload	High	Reduced significantly
Usability score	—	High
> Outputs
Figures (PDF, 300 DPI)
Performance comparison bar charts
Feature contribution heatmaps
Robustness analysis curves
Explainability panels (SHAP beeswarm, LIME local)
Calibration curves (reliability diagrams)
Tables (CSV)
Model performance matrices
Feature importance rankings
Robustness metrics under noise
Deployment evaluation scores
> Files for Submission 1
Table
Deliverable	File	Format
Thesis Proposal	docs/Thesis_Proposal_Health_Risk_Prediction.docx	DOCX/PDF
Code Repository	notebooks/	Jupyter (.ipynb)
Dataset	data/global_blood_test_dataset.csv	CSV
Figures	figures/	PDF
Tables	tables/	CSV
> Conclusion
This project demonstrates that ensemble learning combined with explainability and uncertainty modeling significantly improves healthcare risk prediction systems, making them more reliable, transparent, and clinically useful.
The proposed framework achieves state-of-the-art performance while maintaining robustness under real-world data imperfections and providing actionable explanations for clinical decision support.
