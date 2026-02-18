# 🛒 A/B Testing: E-commerce Landing Page Analysis

## 📌 Project Overview
An e-commerce company developed a new web landing page with the goal of increasing the user conversion rate. Before a full rollout, an A/B test was conducted to determine if the new page (Treatment Group) performs significantly better than the old page (Control Group).

**Final Verdict:** The analysis shows that the new page **did not** outperform the old one. Therefore, the recommendation is to **keep the original page**.

---

## 🛠️ Technologies & Tools
* **Language:** Python 3
* **Libraries:** Pandas, NumPy, Statsmodels, Matplotlib, Seaborn.
* **Technique:** Hypothesis Testing (Z-Test for Proportions), Data Wrangling.

---

## 🔍 Analysis Workflow

### 1. Data Cleaning (Data Wrangling)
The original dataset contained approximately 294,000 records. Rigorous cleaning was required to ensure statistical validity:
* **Mismatch Removal:** Identified and removed **3,893 records** where the `group` (control/treatment) did not match the expected `landing_page` (old/new).
* **Duplicate Removal:** Verified and removed duplicate user IDs to ensure independent sampling.

### 2. Exploratory Data Analysis (EDA)
After cleaning, the observed conversion rates were:
* **Control Group (A):** 12.04%
* **Treatment Group (B):** 11.88%

Initial observation suggested that the new page was actually performing slightly worse than the original.

### 3. Statistical Testing
To confirm if this difference was statistically significant or just random noise, a **One-Tailed Z-Test** was performed with a confidence level of 95% ($\alpha = 0.05$).

* **Null Hypothesis ($H_0$):** $p_{new} \leq p_{old}$ (The new page is not better).
* **Alternative Hypothesis ($H_1$):** $p_{new} > p_{old}$ (The new page leads to higher conversions).

---

## 📊 Results

| Metric | Value |
| :--- | :--- |
| **Z-Score** | -1.3109 |
| **P-Value** | 0.9051 |

### Interpretation
The calculated **P-Value (0.9051)** is significantly higher than the alpha level (0.05).
This means we **fail to reject the Null Hypothesis**. There is no statistical evidence that the new page increases conversions. In fact, the negative Z-score indicates the new page performed worse than the control.

---

## 🚀 Business Recommendation
Based on the data-driven analysis, the advice to the product team is:

1.  **Do NOT implement the new landing page.** The data does not support the hypothesis that the new design drives more sales.
2.  **Retain the Old Page:** The original version is currently performing better.
3.  **Investigate UX Issues:** The design team should review the new page to understand why it failed to engage users.

---
*Author: Agatha Barros*
*🇧🇷 [Leia em Português](README_PT.md)*
