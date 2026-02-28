# Loan Default Risk Prediction & Credit Risk Analytics

A machine learning project that builds predictive models to assess loan default risk, combining statistical analysis, exploratory data analysis, and responsible AI practices in the context of credit risk management.

---

## Project Overview

This project addresses a critical challenge in financial institutions: predicting whether a borrower will default on a loan. Using real-world lending data, the project spans the full data science lifecycle — from research and planning through EDA, model building, and ethical evaluation.

**Key Objectives:**
- Analyze borrower behavior and identify features correlated with loan default
- Build and evaluate classification models (Logistic Regression, Decision Tree, Random Forest)
- Interpret model results from a risk management perspective
- Assess model limitations, bias, and regulatory considerations

---

## Repository Structure

```
├── data/                          # Dataset reference / data loading scripts
├── notebooks/
│   ├── 01_eda_hypothesis_testing.ipynb    # EDA and hypothesis testing
│   └── 02_model_building_evaluation.ipynb # Model training and evaluation
├── reports/
│   ├── research_report.pdf                # Credit risk research report
│   └── action_plan.pdf                    # Project planning document
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Dataset Description

The dataset contains borrower-level information from a lending platform, including:

- **Borrower demographics:** Income, employment length, home ownership
- **Loan characteristics:** Loan amount, interest rate, loan grade, loan term
- **Credit history:** Credit score, number of credit lines, derogatory marks
- **Target variable:** Loan status (Default / Non-Default)

> **Dataset Reference:** 
Dataset Source: Kaggle
Dataset Link:
https://www.kaggle.com/datasets/wordsforthewise/lending-club/code

---

## Environment Setup

### Requirements

- Python 3.8+
- Jupyter Notebook / JupyterLab

### Installation

```bash
# Clone the repository
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

# Create and activate a virtual environment
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter lab
```

Key libraries used: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `scipy`, `statsmodels`

---

## Modeling Approach

### 1. Data Preprocessing & Feature Engineering
- Handling missing values and outliers
- Encoding categorical variables (loan grade, home ownership, etc.)
- Feature scaling for logistic regression
- Train-test split strategy

### 2. Models Implemented

| Model | Purpose |
|-------|---------|
| Logistic Regression | Baseline model — interpretable, probability outputs |
| Decision Tree | Non-linear patterns, feature importance |
| Random Forest *(optional)* | Ensemble method for improved performance |

### 3. Evaluation Strategy

Models are evaluated using:
- **Accuracy** — Overall correctness
- **Precision** — Of predicted defaults, how many are actual defaults
- **Recall** — Of actual defaults, how many are caught
- **Confusion Matrix** — Visualizing false positives vs false negatives

> In credit risk, **false negatives (missed defaults)** carry higher financial cost than false positives. Recall is therefore weighted heavily in model selection.

---

## Exploratory Data Analysis Highlights

The EDA notebook covers:
- Default rate distribution across loan grades and interest rate bands
- Relationship between credit score / income and default probability
- Loan term and repayment behavior analysis
- Hypothesis tests:
  - *H₁: Higher interest rate loans have a higher default probability*
  - *H₂: Borrowers with lower credit scores default more frequently*

---

## Key Findings

> *(To be updated after completing analysis)*

- Loan grade and interest rate are strong predictors of default
- Lower credit scores correlate significantly with higher default rates
- Logistic Regression achieves baseline accuracy of ~XX% with recall of ~XX%
- Class imbalance (fewer defaults than non-defaults) impacts model performance

---

## Model Limitations & Responsible Use

- **Bias in credit data:** Historical data may encode systemic biases against certain demographic groups, leading to discriminatory model outputs
- **Class imbalance:** Defaults are typically underrepresented; techniques like SMOTE or class weighting are necessary for fair evaluation
- **False prediction consequences:** Incorrectly denying credit to a creditworthy borrower (false positive) or approving a defaulter (false negative) both carry real-world costs
- **Regulatory considerations:** Models used in lending must comply with regulations such as the Equal Credit Opportunity Act (ECOA) and Fair Housing Act
- **Human oversight:** Predictive models should assist, not replace, human credit officers — final lending decisions must involve human judgment

---

## License

This project is for educational purposes only. Dataset usage is subject to the terms of the original data provider.
