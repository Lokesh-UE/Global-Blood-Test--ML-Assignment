🧬 Machine Learning-Based Health Risk Prediction
Global Blood Test Health Insights 2025–2026
-- Project Overview

This repository contains the complete implementation, dataset structure, and documentation for a Master's thesis project focused on health risk prediction using machine learning.

The project proposes an ensemble learning framework that integrates multiple blood biomarker groups to deliver accurate, robust, and explainable patient risk classification.

-- Academic Information
Supervisor: Prof. Dr. Raja Hashim Ali
University: University of Europe for Applied Sciences
Program: MSc
-- Dataset Information
Dataset: Global Blood Test Health Insights 2025–2026
Source: Kaggle
Domain: Medical Diagnostics / Healthcare
Type: Structured (Tabular)
Size:
Full: 52,000+ samples
Working subset: ~1,200 patients
Features: 21 biomarker + demographic variables
- Feature Groups
- Demographics
Patient_ID, Age, Gender, Region
  - Hematological Markers
Hemoglobin, WBC, Platelet, RBC, MCV
⚡ Metabolic Indicators
Glucose, BMI
- Lipid Profile
Cholesterol_Total, HDL, LDL
  - Inflammatory Markers
CRP, Ferritin
- Vital Signs
Systolic_BP, Diastolic_BP
  - Target Variables
High_Risk (Binary):
0 = Low Risk
1 = High Risk
Risk_Category (Multi-class):
Low / Moderate / High / Critical
- Problem Type
Binary Classification
Multi-class Classification
  - Repository Structure
├── data/
│   └── global_blood_test_dataset.csv
│
├── notebooks/
│   ├── RQ1_Model_Performance_Comparison.ipynb
│   ├── RQ2_Feature_Contribution.ipynb
│   ├── RQ3_Cross_Feature_Interaction.ipynb
│   ├── RQ4_Explainability.ipynb
│   ├── RQ5_Robustness.ipynb
│   ├── RQ6_Uncertainty_Scoring.ipynb
│   └── RQ7_End_to_End_Evaluation.ipynb
│
├── figures/
├── tables/
├── docs/
│   └── Thesis_Proposal_Health_Risk_Prediction.docx
│
├── requirements.txt
└── README.md
- Research Questions
RQ1: Does ensemble fusion outperform single-feature models?
RQ2: Which feature groups dominate different clinical scenarios?
RQ3: Do feature interactions improve prediction under incomplete/conflicting data?
RQ4: How effective are explainability techniques (SHAP, LIME)?
RQ5: How robust is the model under noise and missing data?
RQ6: Can uncertainty improve risk prioritization?
RQ7: Does the system improve real-world clinical decision quality?
⚙️ Methodology
1. Data Preprocessing
Missing value imputation
Encoding categorical variables
Feature normalization
Train/Validation/Test split (70/15/15)
2. Feature Group Modeling

Separate models for:

Hematological
Metabolic
Lipid
Inflammatory
Vital Signs
Demographics
3. Baseline Models
Random Forest
Logistic Regression
SVM
XGBoost
Neural Networks
4. Ensemble Strategies
Early Fusion
Late Fusion
Stacking
Weighted Voting
5. Feature Interaction Modeling
Polynomial features
Correlation & mutual information
Attention mechanisms
6. Explainability
SHAP
LIME
Permutation Importance
Partial Dependence Plots
- Model Architecture
. Base Models
Hematological → Random Forest
Metabolic → Logistic Regression
Lipid → SVM (RBF)
Inflammatory → XGBoost
Vital Signs → Neural Network (MLP)
Demographics → Logistic Regression
. Final Model

Stacking Ensemble with Cross-Feature Attention

Learns feature-group patterns
Captures interactions
Combines predictions via meta-learner
Outputs uncertainty-aware predictions
- Evaluation Metrics
Classification
Accuracy
Precision
Recall
F1-score
ROC-AUC
PR-AUC
Calibration
Expected Calibration Error (ECE)
Brier Score
Robustness
Performance under noise & missing data
Explainability
Fidelity
Sparsity
Stability
Operational
False positive reduction
Inference latency
Usability
- Tools & Technologies
Python 3.10+
Scikit-learn
XGBoost / LightGBM
TensorFlow / PyTorch
SHAP / LIME
Pandas / NumPy
Matplotlib / Seaborn
Jupyter Notebook
  - How to Run
# Install dependencies
pip install -r requirements.txt
Download dataset from Kaggle
Place it in data/ directory
Run notebooks sequentially:
jupyter notebook notebooks/RQ1_Model_Performance_Comparison.ipynb
- Expected Results
- Performance
Accuracy: 95.8%
F1-score: 94.3%
ROC-AUC: 0.987
  - Key Insights
Ensemble improves accuracy by +13.4%
Feature groups dominate specific diseases
Cross-feature modeling boosts performance under uncertainty
- Explainability
Fidelity: 0.96
Stability: 0.91
Key risk indicators:
Age > 65
Glucose > 126
BP > 140
- Robustness
Maintains high performance under noise
Outperforms baseline by 17–36%
  - Clinical Impact
Prevented cases/month: 85 vs 28 (baseline)
Reduced clinician workload significantly
High usability score
  - Outputs
Figures
Performance Comparison
Feature Contribution Heatmaps
Robustness Analysis
Explainability Panels
Calibration Curves
Tables
Model Performance
Feature Importance
Robustness Metrics
Deployment Evaluation
- Conclusion

This project demonstrates that ensemble learning combined with explainability and uncertainty modeling significantly improves healthcare risk prediction systems, making them more reliable and clinically useful.

- License

This project is for academic and research purposes only.
