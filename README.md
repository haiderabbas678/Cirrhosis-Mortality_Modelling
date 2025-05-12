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
Cirrhosis-Mortality-Prediction<br>
│<br>
├── /Python/<br>
│   └── Cirrhosis_Modeling.ipynb        # Jupyter notebook with full analysis and modeling pipeline<br>
│<br>
├── README.md                           # Project overview and documentation<br>
└── ...

---

## 🔬 Methodology

### 1. **Data Inspection & Exploration**
- Loaded synthetic EHR data representing cirrhosis cases.
- Conducted exploratory data analysis to understand variable distributions and patterns of missingness.

### 2. **Study Population**
- Focused on adults with confirmed cirrhosis diagnoses.
- Target outcome: Whether the patient died within six months of follow-up.

### 3. **Feature Engineering**

#### Selected Features:
| Category             | Variables Included |
|----------------------|--------------------|
| Patient Characteristics | Age, Gender |
| Lab Results           | Platelets, Bilirubin, Albumin, Creatinine, INR, Sodium |
| Clinical Indicators   | MELD Score |
| Complications         | Presence and severity of ascites, hepatic encephalopathy, varices |

- Categorical features were one-hot encoded.
- Additional derived metrics like Fib-4 index were also incorporated.

### 4. **Data Preparation**
- Missing values were handled via median imputation for numerical fields.
- Dataset was divided into:
  - Training set: 80%
  - Testing set: 20%

### 5. **Model Development**
- Compared several classification algorithms:
  - Logistic Regression
  - Random Forest
  - XGBoost (**selected due to superior performance**)
- Hyperparameter optimization was conducted using `GridSearchCV` with 3-fold cross-validation.
  - Tuned parameters included:
    - `n_estimators`
    - `max_depth`
    - `learning_rate`
    - `gamma`
    - `subsample`
    - `colsample_bytree`

### 6. **Evaluation Metrics**
- Final model evaluated on test data using:
  - **Accuracy**
  - **Area Under the Precision-Recall Curve (AUPRC)**
- Interpreted model predictions using **SHAP values** to assess feature contributions.

---

## 📊 Model Performance

### ✅ Evaluation Results (Test Set):
| Metric                        | Value     |
|------------------------------|-----------|
| Accuracy                     | 0.77      |
| AUPRC                        | 0.74      |

### 🔍 Most Influential Features (via SHAP):
- **Fib-4 Index**
- **Age**
- **Blood Urea Nitrogen (BUN)**

These findings suggest that markers of liver fibrosis, advanced age, and impaired kidney function are among the strongest predictors of short-term mortality in cirrhotic patients.

---

## 🧠 Discussion

Despite being trained on synthetic data, the model demonstrates solid predictive capability and aligns with clinical expectations. The use of interpretable methods like SHAP enhances transparency and supports potential integration into clinical settings.

Future steps may involve validating the model on real-world datasets and evaluating its impact in prospective clinical trials.

---

## 🛠️ Tools and Libraries Used

- **Programming Language**: Python
- **Libraries**: pandas, scikit-learn, xgboost, matplotlib, seaborn, shap
- **Development Environment**: Jupyter Notebook
- **Synthetic Data Engine**: MDClone
