📖 Project Overview
Fed-CASP is a privacy-preserving, personalized survival prediction framework designed for patients with locally advanced non-small cell lung cancer (LA-NSCLC) treated with radiotherapy (including immunotherapy-era cohorts). It integrates federated learning (FL) with causal inference to address key challenges in multi-center clinical AI:
Data isolation (privacy protection without raw data sharing)
Inter-institutional heterogeneity (patient populations, imaging protocols, treatment paradigms)
Lack of individualized treatment sensitivity estimation
The framework enables clinicians to predict survival outcomes under alternative treatments (e.g., immunotherapy vs. standard RT, 60Gy vs. 74Gy) and provides interpretable attention maps to support clinical decision-making.
🔑 Core Features
Feature	Description
Privacy-Preserving Federated Learning	Multi-center model training without sharing raw CT/mask data or patient records
Causal Adaptive Aggregation	Federated propensity score weighting + personalized gradient reweighting to mitigate negative transfer
Individualized Counterfactual Prediction	Predicts survival curves for alternative treatments for the same patient
Clinical Interpretability	Grad-CAM attention maps highlighting tumor regions driving survival risk
Web-Based Clinical Deployment	User-friendly Streamlit app for radiotherapy workflow integration
Robust Generalization	Validated across heterogeneous cohorts (real-world + clinical trial data)
📊 Key Results
Fed-CASP outperforms standard federated learning (FedAvg) and independent local models, closely approximating centralized model performance:
Model	External Test C-index	Immunotherapy Cohort C-index	60Gy Cohort C-index	74Gy Cohort C-index
Fed-CASP	0.735 (95% CI: 0.70-0.77)	0.724	0.718	0.681
Centralized (Gold Standard)	0.741	0.738	0.725	0.692
FedAvg	0.678	0.665	0.684	0.645
Independent Local	0.624	0.615	0.641	0.608
Clinical Utility: Accurate risk stratification (log-rank p<0.001) and decision curve analysis showing superior net clinical benefit
Efficiency: Converges in 8 communication rounds (vs. 50+ for FedAvg) with 97% reduced communication cost
Temporal Transfer: Effective for modern immunotherapy cohorts using historical pre-immunotherapy data
