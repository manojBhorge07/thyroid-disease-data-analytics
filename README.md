# Thyroid Disease Detection Using Data Analytics

## 📌 Project Overview

This project applies **Data Analytics and Statistical Analysis** to explore clinical data associated with thyroid disease and identify patterns that may help distinguish negative cases from other thyroid-related classifications.

The project includes data cleaning, exploratory data analysis (EDA), statistical hypothesis testing, correlation analysis, feature analysis, and an attempted comparison of machine learning classification algorithms.

> **Disclaimer:** This is an educational data analytics project, not a clinically validated diagnostic system. Its findings should not be used to diagnose or make treatment decisions.

## 🎯 Objectives

- Clean and preprocess the thyroid dataset.
- Perform exploratory data analysis to understand feature distributions.
- Analyze relationships between clinical variables and the target classification.
- Apply statistical hypothesis tests to identify significant differences and associations.
- Examine feature correlations and logistic regression coefficients.
- Explore feature importance using a Random Forest model.
- Prepare a workflow for comparing multiple classification algorithms.

## 📊 Dataset

The dataset contains clinical and demographic variables related to thyroid classification.

| Dataset detail | Value |
|---|---|
| Original records | 9,171 |
| Duplicate records removed | 102 |
| Records after cleaning | 9,069 |
| Original features | 23 |
| Features after preprocessing | 24 |
| Target type | Binary classification |

**Target encoding:** The original `class` column was converted into a binary target, with `negative` encoded as `0` and all other classes encoded as `1`.

This encoding groups all non-negative categories together. Therefore, the positive class should not automatically be interpreted as confirmed thyroid disease without validating the original class definitions.

The dataset file is not included in this repository. Use a dataset that you are authorized to access and distribute.

## 🛠️ Technologies Used

- **Python** – Data analysis and preprocessing
- **Pandas** – Data manipulation
- **NumPy** – Numerical operations
- **Matplotlib** – Data visualization
- **Seaborn** – Statistical visualizations
- **SciPy** – Statistical hypothesis testing
- **Statsmodels** – Statistical analysis
- **Scikit-learn** – Machine learning and feature analysis
- **Jupyter Notebook** – Interactive development and documentation

## 🔍 Project Workflow

### 1. Data Cleaning and Preprocessing

- Inspected the dataset structure and missing values.
- Removed 102 duplicate records.
- Standardized column names.
- Applied missing-value imputation.
- Converted the target variable into binary form.
- Applied IQR-based outlier capping to selected numerical variables, including age, TSH, T3, TT4, T4U, and FTI.

### 2. Exploratory Data Analysis (EDA)

Explored the distribution and relationships of demographic and clinical variables using descriptive statistics and visualizations.

Key variables included:

- Age and sex
- TSH and T3
- TT4, T4U, and FTI
- Medication-related indicators
- Referral source
- Thyroid-related query indicators

### 3. Statistical Hypothesis Testing

Applied statistical tests to investigate differences and associations between variables and the binary target.

- **Shapiro–Wilk test:** Assessed normality.
- **Levene’s test:** Assessed variance equality.
- **Mann–Whitney U test:** Compared numerical feature distributions between target groups.
- **Chi-square test:** Examined associations between categorical variables and the target.

The normality and equal-variance assumptions were not satisfied for the relevant analyses, motivating the use of non-parametric comparisons where appropriate.

### 4. Correlation Analysis

Examined Pearson and Spearman correlations between selected numerical features and the binary target.

Reported patterns included:

- TSH showed a positive correlation with the target.
- T3 showed a negative correlation with the target.
- TT4 showed a weaker positive correlation.
- Age, T4U, and FTI showed relatively small correlations.

Correlation does not establish causation, and the observed relationships depend on the target encoding and dataset composition.

### 5. Logistic Regression Analysis

Examined logistic regression coefficients and odds ratios to understand the direction of association between selected features and the target.

Examples of reported odds ratios:

| Feature | Reported odds ratio |
|---|---:|
| TSH | 2.289 |
| TT4 | 2.213 |
| Query hyperthyroid | 1.734 |
| T3 | 0.647 |

These are model-based associations, not evidence of causation. Their interpretation depends on preprocessing, feature coding, and the fitted model specification.

### 6. Random Forest Feature Importance

Examined impurity-based feature importance from a Random Forest model.

| Feature | Reported importance |
|---|---:|
| TSH | 0.2550 |
| T3 | 0.2182 |
| FTI | 0.1672 |
| TT4 | 0.1487 |
| T4U | 0.0907 |

These values describe the relative importance assigned by the fitted model. They do not establish clinical importance or independent predictive value.

### 7. Machine Learning Model Comparison

The notebook includes an intended comparison of:

- Logistic Regression
- Decision Tree
- Random Forest
- Support Vector Machine (SVM)
- K-Nearest Neighbors (KNN)

The intended workflow uses an 80:20 stratified train-test split with `random_state=42`.

**Important:** The final model-comparison step encountered an encoder error involving mixed integer and string values. Consequently, the notebook does not establish a valid final model comparison, a best-performing model, or a verified accuracy score.

## 📈 Key Findings

- TSH and T3 showed notable distributional differences between the binary target groups.
- TT4 also showed a statistically significant difference.
- TSH had the strongest positive correlation with the binary target among the selected numerical variables examined.
- The chi-square analysis identified associations involving sex, referral source, thyroxine use, pregnancy status, and the `query_hypothyroid` indicator.
- Random Forest feature importance ranked TSH and T3 highest among the listed features.

Statistical significance and feature importance alone do not demonstrate reliable diagnostic performance.

## ⚠️ Limitations and Future Improvements

- Validate the original target categories before interpreting the positive class as thyroid disease.
- Split the data into training and test sets before fitting imputers, outlier caps, scalers, or other learned preprocessing steps.
- Investigate potential data leakage from referral, medication, and query-related features.
- Correct the mixed-type encoding issue and rerun the full model comparison.
- Evaluate models using precision, recall, F1-score, ROC-AUC, and a confusion matrix, alongside accuracy where appropriate.
- Use cross-validation and, if available, external validation data.
- Consider the effects of multiple statistical tests when interpreting p-values.
- Review outlier treatment carefully because extreme clinical values may be meaningful rather than erroneous.

## 🚀 How to Run the Project

### Prerequisites

Install Python 3.10 or a compatible version and Jupyter Notebook.

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/thyroid-disease-data-analytics.git
cd thyroid-disease-data-analytics
```

Replace `YOUR-USERNAME` with your GitHub username.

### 2. Create a virtual environment (recommended)

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `thyroid_disease_data_analytics.ipynb` and run the cells in order.

**Dataset note:** If the notebook expects an external dataset, place your authorized dataset at the path specified in the notebook or update the data-loading cell accordingly.

## 📁 Repository Structure

```text
thyroid-disease-data-analytics/
│
├── thyroid_disease_data_analytics.ipynb
├── README.md
├── requirements.txt
├── .gitignore
└── LICENSE
```

## 🎓 Project Information

- **Project:** Data Analytics Approach for Thyroid Disease Detection
- **Track:** Minor Track – Data Analytics
- **Academic Year:** 2025–26
- **Institution:** Vishwakarma University

## 👨‍💻 Author

**Manoj Bhorge**


---

⭐ If you find this project useful for learning data analytics, statistical testing, and machine learning workflows, feel free to explore the notebook.

