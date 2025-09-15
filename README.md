# 🏦 Loan Default Prediction

##  Executive Summary
This project develops a data-based solution to identify **high-risk loan applicants before loan disbursement**. Using historical loan performance records, we performed extensive exploratory data analysis (EDA) and built classification models to assess default risk.  

We tested and tuned three models: **Logistic Regression, Decision Tree, and Random Forest**. The **threshold-optimized Random Forest** emerged as the best-performing solution, with:

- **Accuracy:** 91%  
- **Precision:** 84%  
- **Recall:** 68%  
- **ROC AUC:** 0.96  
- **F1-score:** chosen as the main evaluation metric to balance precision and recall  

Key predictors of loan default were found to be:  
- **DEBTINC** (Debt-to-Income Ratio)  
- **DELINQ** (Delinquent Credit Lines)  
- **DEROG** (Derogatory Reports)  
- **CLAGE** (Credit Line Age, negatively correlated)  

---

##  Dataset Description
The **Home Equity dataset (HMEQ)** contains information on **5,960 home equity loans**. The target variable is `BAD`, indicating whether a client defaulted.  

- **BAD:** 1 = default, 0 = repaid  
- **LOAN:** Loan amount  
- **MORTDUE:** Balance due on existing mortgage  
- **VALUE:** Current property value  
- **REASON:** Loan purpose (HomeImp, DebtCon)  
- **JOB:** Job type (Mgr, Self, etc.)  
- **YOJ:** Years at present job  
- **DEROG:** Number of major derogatory reports  
- **DELINQ:** Number of delinquent credit lines  
- **CLAGE:** Age of oldest credit line (months)  
- **NINQ:** Recent credit inquiries  
- **CLNO:** Number of existing credit lines  
- **DEBTINC:** Debt-to-income ratio  

---

##  Key Insights from EDA
- **Default Rate:** ~20% of applicants defaulted → clear class imbalance.  
- **Loan Amount (LOAN):** Smaller loans defaulted more frequently.  
- **Property Value (VALUE):** Defaulters had slightly lower property values.  
- **Mortgage Due (MORTDUE):** Defaulters had lower balances.  
- **Debt-to-Income (DEBTINC):** Strong predictor — higher ratios → higher default risk.  
- **Delinquencies (DELINQ):** More delinquencies → higher probability of default.  
- **Credit Age (CLAGE):** Longer credit history reduced default likelihood.  
- **Employment Tenure (YOJ):** Less than 2 years at job → higher default risk.  
- **Loan Purpose (REASON):** Home improvement loans had higher defaults than debt consolidation.  
- **Job Role (JOB):** Managers/professionals defaulted less; sales/independent roles defaulted more.  

---

##  Methods
- **Data Preprocessing:** Missing values handled, categorical encoding applied.  
- **EDA:** Statistical tests and visualizations to identify risk indicators.  
- **Modeling:** Logistic Regression, Decision Tree, Random Forest.  
- **Evaluation Metrics:** Accuracy, Precision, Recall, ROC AUC, F1-score.  
- **Threshold Optimization:** Tuned to maximize F1-score.  
- **Model Explainability:** SHAP/PDP suggested for interpretability.  

---

##  Final Solution
- **Model:** Random Forest Classifier  
- **Performance:** Balanced trade-off between precision and recall, high F1-score.  
- **Deployment Plan:** Integrate into loan underwriting workflows with human oversight.  

---

##  Recommendations for Implementation
**Actions:**
- Deploy Random Forest model in loan processing system.  
- Use optimized decision threshold alongside human judgment.  
- Monitor model performance regularly.  

**Benefits:**
- Improved detection of high-risk borrowers.  
- Reduced default rates and stronger loan portfolio.  
- Faster, consistent, and scalable evaluations.  

**Costs:**
- Infrastructure for real-time scoring.  
- Staff training for model use and interpretation.  
- Ongoing maintenance and retraining.  

**Risks & Mitigation:**
- **Model Drift:** Regular retraining and monitoring.  
- **Interpretability:** Use SHAP/PDP for regulatory compliance.  
- **Fairness:** Audit for bias and discrimination.  

**Further Analysis:**
- Add external credit bureau/alternative data.  
- Evaluate separate models for housing vs personal loans.  
- Continuous refinement and feature engineering.  

---
