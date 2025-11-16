# Bank Marketing Campaign Optimization

> Predicting customer term deposit subscriptions using machine learning to optimize marketing performance.

---

## Objective
- This project aims to optimize bank telemarketing campaigns by predicting which clients are most likely to subscribe to a term deposit.  
By identifying high-potential customers, marketing teams can target outreach efficiently, reduce costs, and increase campaign success rates.
---

## 📊 Dataset
- **Source:** [UCI Machine Learning Repository – Bank Marketing Dataset](https://archive.ics.uci.edu/ml/datasets/Bank+Marketing)  
- **File used:** `bank-additional-full.csv`  
- **Records:** 41,188  
- **Features:** 20 predictors + 1 target variable (`y`: client subscribed = yes/no)  
- **Period:** May 2008 – November 2010  

---

## Methodology
1. **Data Preprocessing**
   - Removed duplicates and handled missing values.
   - Encoded categorical variables using Label Encoding.
2. **Addressing Class Imbalance**
   - Original ratio: ~89% “no” vs. 11% “yes”.
   - Applied SMOTE (Synthetic Minority Oversampling Technique) to balance the training data.
3. **Model Development**
   - Trained a Random Forest Classifier on the balanced dataset.
   - Tuned hyperparameters and validated using stratified train/test split.
4. **Evaluation**
   - Evaluated on the untouched (real-world) test set.
   - Used Precision, Recall, F1-score, ROC-AUC, and PR-AUC metrics.
5. **Visualization**
   - Created ROC and Precision–Recall curves.
   - Generated Feature Importance charts for model interpretation.

---

## Results

| Metric | Score |
|---------|-------|
| **Accuracy** | 0.91 |
| **Precision (yes)** | 0.59 |
| **Recall (yes)** | 0.66 |
| **F1-score (yes)** | 0.62 |
| **ROC-AUC** | **0.94** |
| **PR-AUC (Average Precision)** | **0.62** |

> After applying SMOTE, recall for subscribers improved from **0.43 → 0.66**, and ROC-AUC increased to **0.94**, indicating robust model discrimination and improved sensitivity to positive outcomes.

---

## Summary of Insights

**Campaign Performance**  
- The model accurately distinguishes deposit subscribers from non-subscribers (AUC = 0.94) and captures 66% of true positives, enabling smarter marketing targeting.

**Key Predictive Factors**  
- **Duration** of the last contact was the most influential predictor — longer calls correlate with higher subscription likelihood.  
- **Economic indicators** (`euribor3m`, `nr.employed`, `emp.var.rate`) significantly impact customer response, reflecting sensitivity to economic conditions.  
- **Consumer sentiment** (`cons.conf.idx`, `cons.price.idx`) affects investment willingness — optimism leads to higher deposit uptake.  
- **Contact method** and **timing (month)** influence conversion rates — mobile outreach and certain campaign periods perform better.

**Model Interpretation**  
Behavioral engagement and macroeconomic context are stronger drivers of campaign success than demographics, indicating that timing and communication strategy matter more than static customer attributes.

---

## Recommendations

The following recommendations can help optimize future campaigns:

1. **Prioritize meaningful, longer customer interactions.**  
   Train agents to engage clients effectively — call duration is the strongest success driver.

2. **Time campaigns during favorable economic conditions.**  
   Launch campaigns when interest rates (Euribor) are low and employment levels are stable.

3. **Target responsive customer profiles.**  
   Focus on middle-aged professionals and clients with positive prior campaign outcomes.

4. **Leverage high-performing channels.**  
   Emphasize mobile communication for better connection rates and engagement.

5. **Integrate predictive insights into operations.**  
   Deploy the model into a dashboard or API to help marketing teams identify high-likelihood leads in real time.

6. **Monitor macroeconomic indicators.**  
   Refresh model inputs regularly to maintain accuracy under changing economic conditions.

---

## Tools & Libraries
- **Python**
- **Pandas**
- **Scikit-learn**
- **Imbalanced-learn**
- **Seaborn**
- **Matplotlib**
- **Joblib**

---

## References
Moro, S., Cortez, P., & Rita, P. (2014). *A Data-Driven Approach to Predict the Success of Bank Telemarketing*. Decision Support Systems, 62, 22–31.  
DOI: [10.1016/j.dss.2014.03.001](https://doi.org/10.1016/j.dss.2014.03.001)

---

## Future Enhancements
- Add SQL/AWS integration for scalable data storage and deployment.
- Build a Power BI or Streamlit dashboard for interactive campaign optimization.
- Experiment with XGBoost or LightGBM for improved performance.
- Perform feature engineering on call outcomes and economic trends.

---




