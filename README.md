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
Loan-Default-Risk-Prediction/
│
├── data/
│ └── README.txt
│
├── models/
│ ├── loan_default_model.pkl
│ └── scaler.pkl
│
├── notebooks/
│ └── 01_EDA.ipynb
│
├── reports/
│ ├── Research_Report_Credit_Risk.pdf
│ ├── Project_Action_Plan.pdf
│ └── Project_Presentation.pptx
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Dataset Description

The dataset used in this project is sourced from the **Lending Club Loan Dataset** available on Kaggle.

It contains borrower-level financial and loan information used to predict loan default risk.

### Dataset Source
Kaggle Dataset:  
https://www.kaggle.com/datasets/wordsforthewise/lending-club

### Dataset Overview
### Dataset Overview

- Total observations used for modeling: **44,006**
- Train set size: **35,204**
- Test set size: **8,802**
- Number of features after preprocessing: **16**
- Data type: Structured tabular financial data
- Target variable: `loan_status` (Binary classification: Default vs Non-Default)

The original dataset contains multiple loan status categories such as:
- Fully Paid
- Charged Off
- Current
- Late (31–120 days)
- In Grace Period

For modeling purposes, the problem was simplified into a binary classification task distinguishing **Default vs Non-Default** borrowers.

### Feature Categories

1. **Borrower Demographics**
   - Annual income
   - Employment length
   - Home ownership status

2. **Loan Characteristics**
   - Loan amount
   - Interest rate
   - Loan grade
   - Loan term

3. **Credit History**
   - Credit score
   - Number of credit lines
   - Derogatory marks

### Important Note

The dataset file is not included in this repository due to GitHub file size limitations.

To reproduce this project:

1. Download the dataset from the Kaggle link above.
2. Extract the CSV file.
3. Place it inside the `data/` directory as: data/loan_data.csv

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

- Loan grade and interest rate show strong correlation with default probability.
- Borrowers with lower credit scores demonstrate higher default likelihood.
- Class imbalance is present in the dataset, with non-default cases significantly outnumbering default cases.
- Logistic Regression was implemented as the baseline model for interpretability and probability estimation.
- Model performance evaluation was conducted using accuracy, precision, recall, and confusion matrix analysis.
---

## Model Limitations & Responsible Use

- **Bias in credit data:** Historical data may encode systemic biases against certain demographic groups, leading to discriminatory model outputs
- **Class imbalance:** Defaults are typically underrepresented; techniques like SMOTE or class weighting are necessary for fair evaluation
- **False prediction consequences:** Incorrectly denying credit to a creditworthy borrower (false positive) or approving a defaulter (false negative) both carry real-world costs
- **Regulatory considerations:** Models used in lending must comply with regulations such as the Equal Credit Opportunity Act (ECOA) and Fair Housing Act
- **Human oversight:** Predictive models should assist, not replace, human credit officers — final lending decisions must involve human judgment

The dataset exhibits class imbalance, with non-default loans significantly outnumbering default loans. 
This imbalance impacts model performance and requires careful evaluation using recall and confusion matrix analysis.

---

## License

This project is for educational purposes only. Dataset usage is subject to the terms of the original data provider.
