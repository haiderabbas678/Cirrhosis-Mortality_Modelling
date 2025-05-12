# 🏥 Predicting 6-Month Mortality Risk in Cirrhosis Patients

This project develops a machine learning model to estimate the likelihood of mortality within six months for individuals diagnosed with cirrhosis. The dataset used in this study was generated synthetically using MDClone, mimicking real-world clinical records while preserving patient anonymity.

The goal is to identify key clinical indicators and build a predictive tool that could assist healthcare providers in risk stratification and decision-making.

---

## 🗃️ Dataset Overview

- **Source**: Synthetic dataset created by MDClone
- **Content**: Simulated medical records of adult patients with cirrhosis
- **Includes**:
  - Demographic information (`age`, `gender`)
  - Laboratory measurements (`albumin`, `bilirubin`, `creatinine`, `INR`, `sodium`, `platelets`)
  - Clinical complications (`ascites`, `hepatic encephalopathy`, `varices`)
  - Scoring systems (`MELD score`)
  - Outcome: Death within six months (`binary label`)

---

## 📁 Repository Structure
Cirrhosis-Mortality-Prediction/
│
├── /Python/
│   └── Cirrhosis_Modeling.ipynb        # Jupyter notebook containing full analysis and modeling workflow
│
├── README.md                           # Project overview
└── ...
