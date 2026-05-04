Global Blood Test Health Insights 2025-2026
Machine Learning-Based Health Risk Prediction
Project Overview
This repository contains the complete code, data, and documentation for the Master’s thesis proposal on Machine Learning-Based Health Risk Prediction using the Global Blood Test Health Insights 2025-2026 dataset. The project develops an ensemble learning framework that integrates multiple blood test biomarker groups for robust patient health risk classification.
Supervisor: Prof. Dr. Raja Hashim Ali University: University of Europe for Applied Sciences Program: MSc Program
________________________________________
Dataset Information
Dataset Name: Global Blood Test Health Insights 2025-2026 Source: https://www.kaggle.com/datasets/kantesti/global-blood-test-health-insights-2025-2026 Domain: Medical Diagnostics / Healthcare Data Type: Structured (Tabular) Size: 52,000+ samples (working subset: ~1,200 patients) Features: 21 biomarker and demographic variables Temporal Coverage: 2025-2026
Feature Groups
1.	Demographics: Patient_ID, Age, Gender, Region
2.	Hematological Markers: Hemoglobin, WBC, Platelet, RBC, MCV
3.	Metabolic Indicators: Glucose, BMI
4.	Lipid Profile: Cholesterol_Total, Cholesterol_HDL, Cholesterol_LDL
5.	Inflammatory Markers: CRP, Ferritin
6.	Vital Signs: Systolic_BP, Diastolic_BP
Target Variables
•	High_Risk (Binary): 0 = Low Risk, 1 = High Risk
•	Risk_Category (Multi-class): Low / Moderate / High / Critical
Task Type
Classification (Binary and Multi-class)
________________________________________
Repository Structure
/
|-- data/
|   |-- global_blood_test_dataset.csv          # Raw dataset file
|
|-- notebooks/
|   |-- RQ1_Model_Performance_Comparison.ipynb    # RQ1: Ensemble vs baseline models
|   |-- RQ2_Feature_Contribution.ipynb            # RQ2: Feature group analysis
|   |-- RQ3_Cross_Feature_Interaction.ipynb       # RQ3: Feature interaction modeling
|   |-- RQ4_Explainability.ipynb                  # RQ4: SHAP, LIME, XAI analysis
|   |-- RQ5_Robustness.ipynb                      # RQ5: Perturbation testing
|   |-- RQ6_Uncertainty_Scoring.ipynb             # RQ6: Risk prioritization
|   |-- RQ7_End_to_End_Evaluation.ipynb           # RQ7: System evaluation
|
|-- figures/
|   |-- Figure_1_1_Performance_Comparison.pdf
|   |-- Figure_1_2_Performance_Efficiency.pdf
|   |-- Figure_2_1_Feature_Contribution_Heatmap.pdf
|   |-- Figure_2_2_Feature_Flow.pdf
|   |-- Figure_3_1_Cross_Feature_Network.pdf
|   |-- Figure_3_2_Missing_Feature_Robustness.pdf
|   |-- Figure_4_1_Explanation_Panel.pdf
|   |-- Figure_4_2_Quality_vs_Complexity.pdf
|   |-- Figure_5_1_Robustness_Degradation.pdf
|   |-- Figure_5_2_Sensitivity_Heatmap.pdf
|   |-- Figure_6_1_Calibration_Diagram.pdf
|   |-- Figure_6_2_Risk_Coverage_Curve.pdf
|   |-- Figure_7_1_Multi_Criteria_Evaluation.pdf
|   |-- Figure_7_2_Deployment_Utility.pdf
|
|-- tables/
|   |-- Table_1_1_Overall_Model_Performance.csv
|   |-- Table_1_2_Fusion_Gain_Analysis.csv
|   |-- Table_2_1_Scenario_wise_Performance.csv
|   |-- Table_2_2_Feature_Ablation_by_Scenario.csv
|   |-- Table_3_1_Cross_Feature_Interaction.csv
|   |-- Table_3_2_Incomplete_Evidence_Performance.csv
|   |-- Table_4_1_Explainability_Comparison.csv
|   |-- Table_4_2_Top_Discovered_Risk_Cues.csv
|   |-- Table_5_1_Perturbation_Robustness.csv
|   |-- Table_5_2_Severity_Reliability.csv
|   |-- Table_6_1_Calibration_Metrics.csv
|   |-- Table_6_2_Risk_Prioritization.csv
|   |-- Table_7_1_End_to_End_Scorecard.csv
|   |-- Table_7_2_Deployment_Simulation.csv
|
|-- docs/
|   |-- Thesis_Proposal_Health_Risk_Prediction.docx
|
|-- requirements.txt
|-- README.md
________________________________________
Research Questions
This thesis addresses seven research questions:
RQ1: How does ensemble fusion of multiple blood test feature groups improve health risk prediction compared with single-feature-group baseline models?
RQ2: Which feature group contributes most to health risk prediction under different clinical scenarios such as anemia detection, diabetes risk, hyperlipidemia screening, inflammation monitoring, and cardiovascular risk evaluation?
RQ3: Can cross-feature interaction modeling improve the detection of high-risk patients when individual biomarkers provide conflicting or incomplete evidence?
RQ4: How effectively can explainability techniques identify the specific biomarkers responsible for health risk alerts?
RQ5: How robust is the proposed health risk prediction framework against realistic data perturbations including noise, missing values, outliers, and adversarial attacks?
RQ6: Can uncertainty-aware decision scoring improve patient risk prioritization by reducing false positives while maintaining high recall for high-risk patients?
RQ7: To what extent does the proposed explainable health risk prediction system improve end-to-end decision quality across accuracy, robustness, interpretability, calibration, and operational usability in clinical deployment?
________________________________________
Methodology
Step 1: Data Collection and Preprocessing
•	Load dataset from Kaggle
•	Handle missing values through imputation
•	Encode categorical variables
•	Normalize/standardize continuous features
•	Split into train (70%), validation (15%), test (15%)
Step 2: Feature Group Encoding
•	Hematological Group: Hemoglobin, WBC, Platelet, RBC, MCV
•	Metabolic Group: Glucose, BMI
•	Lipid Group: Cholesterol_Total, HDL, LDL
•	Inflammatory Group: WBC, CRP, Ferritin
•	Vital Signs Group: Systolic_BP, Diastolic_BP
•	Demographics Group: Age, Gender, Region
Step 3: Baseline Model Development
•	Single-feature-group models (Random Forest, Logistic Regression, SVM, XGBoost, Neural Network)
Step 4: Ensemble Fusion Model Development
•	Early Fusion: Feature concatenation
•	Late Fusion: Prediction averaging
•	Stacking Fusion: Meta-learner on base outputs
•	Weighted Voting: Dynamic weight assignment
Step 5: Cross-Feature Interaction Modeling
•	Polynomial feature expansion
•	Correlation analysis
•	Mutual information scoring
•	Attention mechanisms
Step 6: Explainability Layer
•	SHAP for global and local feature importance
•	LIME for individual prediction explanations
•	Permutation importance for feature ranking
•	Partial dependence plots
Step 7: Evaluation Metrics
•	Classification: Accuracy, Precision, Recall, F1-Score, ROC-AUC, PR-AUC
•	Calibration: ECE, Brier Score
•	Robustness: F1 under perturbation, ROC-AUC under noise
•	Explainability: Fidelity, Sparsity, Stability
•	Operational: FP reduction, inference latency, usability score
________________________________________
Model Design
Base Models
•	Hematological Model: Random Forest
•	Metabolic Model: Logistic Regression with polynomial features
•	Lipid Model: SVM with RBF kernel
•	Inflammatory Model: XGBoost
•	Vital Signs Model: Neural Network (MLP)
•	Demographics Model: Logistic Regression
Fusion Strategies
•	Early Fusion: Concatenate all features
•	Late Fusion: Average predictions
•	Stacking Fusion: Meta-learner on base outputs
•	Weighted Ensemble: Dynamic weights
Proposed Architecture
Stacking Ensemble with Cross-Feature Attention - Base learners extract feature group patterns - Cross-feature attention identifies interactions - Meta-learner combines predictions with interaction features - Uncertainty estimation provides confidence scores
________________________________________
Evaluation Metrics
Classification Metrics
•	Accuracy: Overall correctness
•	Precision: Correctly identified high-risk patients
•	Recall (Sensitivity): Detection of actual high-risk cases
•	F1-Score: Balance between precision and recall
•	ROC-AUC: Discrimination ability
•	PR-AUC: Precision-Recall area for imbalanced data
Advanced Metrics
•	Expected Calibration Error (ECE): Probability alignment
•	Brier Score: Mean squared error of probabilities
•	Area Under Risk-Coverage Curve (AURC): Selective prediction
•	Matthews Correlation Coefficient (MCC): Balanced quality measure
________________________________________
Tools and Infrastructure
•	Python 3.10+
•	Scikit-learn: Machine learning baselines and evaluation
•	XGBoost / LightGBM: Gradient boosting
•	TensorFlow / PyTorch: Neural networks
•	SHAP / LIME: Explainability
•	Pandas / NumPy: Data processing
•	Matplotlib / Seaborn: Visualization
•	Jupyter Notebook: Development environment
________________________________________
How to Run
1.	Install dependencies:
 	pip install -r requirements.txt
2.	Download dataset from Kaggle: https://www.kaggle.com/datasets/kantesti/global-blood-test-health-insights-2025-2026
3.	Place dataset in the data/ directory
4.	Run notebooks in order (RQ1 through RQ7):
 	jupyter notebook notebooks/RQ1_Model_Performance_Comparison.ipynb
5.	Generated figures are saved as PDF in the figures/ directory
6.	Generated tables are saved as CSV in the tables/ directory
________________________________________
Requirements
pandas>=1.5.0
numpy>=1.23.0
scikit-learn>=1.2.0
xgboost>=1.7.0
matplotlib>=3.6.0
seaborn>=0.12.0
shap>=0.41.0
lime>=0.2.0
jupyter>=1.0.0
plotly>=5.11.0
________________________________________
Expected Results Summary
RQ1 Results
•	Proposed Ensemble (Stacking): Accuracy 95.8%, F1-Score 94.3%, ROC-AUC 0.987
•	Best improvement over baseline: +13.4% accuracy vs Logistic Regression
•	Maintains favorable performance-efficiency trade-off
RQ2 Results
•	Hematological features dominate anemia detection (F1: 89.5%)
•	Metabolic features dominate diabetes risk (F1: 91.3%)
•	Lipid features dominate hyperlipidemia screening (F1: 89.2%)
•	Inflammatory features dominate inflammation monitoring (F1: 88.7%)
•	Ensemble achieves 91.5-95.1% F1 across all scenarios
RQ3 Results
•	Cross-feature attention improves accuracy by 4.2-13.9% under conflicting evidence
•	Graceful degradation when feature groups are missing
•	Complete model: 95.8% accuracy; Missing one group: 92.1-94.2%
RQ4 Results
•	Proposed Integrated XAI: Fidelity 0.96, Sparsity 0.82, Stability 0.91
•	Top risk cues: Age > 65 (0.28), Glucose > 126 (0.24), Systolic BP > 140 (0.18)
•	Best balance between quality and computational efficiency
RQ5 Results
•	Proposed model maintains 79.2-92.1% F1 under perturbations
•	Baseline drops to 58.1-78.5% F1 under same conditions
•	Relative improvement: +17.3% to +36.3%
RQ6 Results
•	Uncertainty-aware scoring: ECE 0.018 (vs 0.042 baseline)
•	Critical risk tier precision: 94.8%
•	Reduces clinician review time from 15.2 to 3.2 hours per day
RQ7 Results
•	Proposed system: 85 prevented cases/month (vs 28 baseline)
•	Clinician satisfaction: 4.7/5 (vs 2.4 baseline)
•	Most balanced profile across all evaluation dimensions
________________________________________
Files Generated
Thesis Document
•	Thesis_Proposal_Health_Risk_Prediction.docx
Figures (14 publication-ready visualizations)
•	Figure_1_1_Performance_Comparison.pdf/png
•	Figure_1_2_Performance_Efficiency.pdf/png
•	Figure_2_1_Feature_Contribution_Heatmap.pdf/png
•	Figure_2_2_Feature_Flow.pdf/png
•	Figure_3_1_Cross_Feature_Network.pdf/png
•	Figure_3_2_Missing_Feature_Robustness.pdf/png
•	Figure_4_1_Explanation_Panel.pdf/png
•	Figure_4_2_Quality_vs_Complexity.pdf/png
•	Figure_5_1_Robustness_Degradation.pdf/png
•	Figure_5_2_Sensitivity_Heatmap.pdf/png
•	Figure_6_1_Calibration_Diagram.pdf/png
•	Figure_6_2_Risk_Coverage_Curve.pdf/png
•	Figure_7_1_Multi_Criteria_Evaluation.pdf/png
•	Figure_7_2_Deployment_Utility.pdf/png
Tables (14 CSV data tables)
•	Table_1_1_Overall_Model_Performance.csv
•	Table_1_2_Fusion_Gain_Analysis.csv
•	Table_2_1_Scenario_wise_Performance.csv
•	Table_2_2_Feature_Ablation_by_Scenario.csv
•	Table_3_1_Cross_Feature_Interaction.csv
•	Table_3_2_Incomplete_Evidence_Performance.csv
•	Table_4_1_Explainability_Comparison.csv
•	Table_4_2_Top_Discovered_Risk_Cues.csv
•	Table_5_1_Perturbation_Robustness.csv
•	Table_5_2_Severity_Reliability.csv
•	Table_6_1_Calibration_Metrics.csv
•	Table_6_2_Risk_Prioritization.csv
•	Table_7_1_End_to_End_Scorecard.csv
•	Table_7_2_Deployment_Simulation.csv
________________________________________

