# Paisabazar Credit Score Analysis

**Domain:** FinTech / Consumer Credit  
**Tools:** Python · Pandas · Seaborn · Matplotlib · Plotly · Power BI  
**Dataset:** 100,000 customer records

---

## Project Overview

An end-to-end data analysis project on Paisabazar's credit score dataset. The goal was to identify the key factors that drive a customer's credit score classification — Good, Standard, or Poor — to help the platform improve loan eligibility decisions and reduce default risk.

The project covers the full analyst workflow: data cleaning → exploratory data analysis → bivariate analysis → correlation study → business insights → interactive Power BI dashboard.

---

## Business Problem

Paisabazar needs to assess loan eligibility accurately across a large customer base. Incorrect credit assessments lead to either rejected good customers or approved high-risk borrowers. This analysis identifies which customer attributes most strongly predict credit score category, enabling more precise and personalised loan decisions.

---

## Dataset

| Attribute | Details |
|---|---|
| Source | Paisabazar credit dataset |
| Records | 100,000 customers |
| Key Features | Annual Income, Age, Occupation, Credit Utilization Ratio, Number of Delayed Payments, Outstanding Debt, Credit History Age, Monthly Balance, Payment Behaviour |
| Target Variable | Credit Score — Good / Standard / Poor |

---

## Key Findings

- **Delayed payments is the strongest predictor** of a Poor credit score. Customers with 15+ delayed payments were overwhelmingly in the Poor category.
- **Higher annual income strongly correlates with Good scores.** Good-score customers had significantly higher income distributions vs Poor-score customers.
- **Credit utilization ratio** showed limited differentiation across credit score bands — most customers (all categories) maintained 30–40% utilization.
- **Occupation had no significant impact** on credit score — all 15 occupation categories showed similar score distributions, confirming this hypothesis.
- **Credit score distribution:** Standard 53.17% · Poor 29% · Good 17.83% — the dataset reflects a realistic skew toward standard-risk customers.

---

## Analysis Structure

```
1. Data Cleaning
   - Dropped irrelevant identifiers (ID, Customer_ID, SSN, Name)
   - Replaced placeholder 'NM' values with NaN
   - Handled nulls in Payment_of_Min_Amount
   - Cast categorical columns to correct dtype

2. Univariate Analysis
   - Credit Score distribution (bar chart)
   - Annual Income distribution (histogram)
   - Age distribution — predominantly 20–40 years, peak at 30–35
   - Occupation distribution — evenly spread across 15 categories
   - Credit Utilization distribution — healthy 30–40% range for most customers
   - Delayed Payments distribution — spread 0–25, spike at 7–20

3. Bivariate Analysis
   - Annual Income vs Credit Score (boxplot)
   - Credit Utilization vs Credit Score (boxplot)
   - Delayed Payments vs Credit Score (boxplot) ← strongest signal
   - Occupation vs Credit Score (countplot)

4. Correlation Analysis
   - Heatmap across 7 numerical features
   - Annual Income and Monthly Salary strongly correlated
   - Delayed payments negatively correlated with Monthly Balance
   - Pairplot segmented by Credit Score category

5. Business Conclusions & Recommendations
```

---

## Power BI Dashboard

An interactive dashboard was built on the same dataset to visualise findings for non-technical stakeholders.

**Dashboard Features:**
- KPI Cards: Total Customers (100K), Avg Annual Income (₹50.51K), Avg Credit Utilization (32.29), Avg Delayed Payments (13.31)
- Donut chart: Credit Score distribution breakdown
- Bar charts: Delayed Payments by Credit Score, Annual Income by Credit Score, Occupation count by Credit Score
- Slicers: Filter by Credit Score category and Age Group

> Dashboard file: `Project_Final_Module_4.pbix`  
> Dashboard screenshot: `dashboard_screenshot.png`

---

## Business Recommendations

1. **Flag customers with 15+ delayed payments** as high-risk at loan application stage — strongest single predictor of Poor score.
2. **Income-based tiering** — customers with annual income above ₹60K can be fast-tracked for standard loan products with minimal additional checks.
3. **Occupation should not be a screening criterion** — data shows no meaningful credit score variation across occupations; removing it reduces application friction without increasing risk.
4. **Next step:** Build a classification model (Random Forest / XGBoost) using these features to predict credit score category and automate the risk flagging process.

---

## Files

| File | Description |
|---|---|
| `project_module_2.ipynb` | Python EDA notebook (Google Colab) |
| `Project_Final_Module_4.pbix` | Power BI dashboard file |
| `dashboard_screenshot.png` | Dashboard preview image |

---

## How to Run

1. Clone this repository
2. Open `project_module_2.ipynb` in Google Colab or Jupyter Notebook
3. Upload `dataset.csv` when prompted
4. Run all cells in order

For the dashboard, open `Project_Final_Module_4.pbix` in Power BI Desktop (free download from Microsoft).

---

*Project completed as part of B.E. Artificial Intelligence & Machine Learning — University of Mumbai, 2025*
