# ECHR Voting Prediction
Project Repository for DSCI 633 – Kaggle Competition (Spring 2025)  
Rochester Institute of Technology  

---

## Overview
This project models **pro-government voting behavior** in the European Court of Human Rights (ECHR).  
Using a dataset of **10,000+ voting records** with **68 features** across judges, cases, and countries,  
we developed machine learning models to predict whether a judge will cast a **pro-government vote**.  

The competition was hosted on Kaggle, and submissions were evaluated on **accuracy**.

---

## Goals
- Explore judge, case, and country-level variables influencing voting outcomes.  
- Engineer features to capture **bias, regional alignment, and judge characteristics**.  
- Train and evaluate machine learning models for **predictive performance**.  
- Compare models and report insights on judicial voting behavior.  

---

## Dataset
- **train.csv**: Training set with ~10k voting records.  
- **test.csv**: Test set for Kaggle submission.  
- **solutions_template.csv**: Submission format.  

### Features
- **Case details**: case title, year, violation indicators, issue type, originating body, importance level.  
- **Judge characteristics**: gender, age, professional background (academic, lawyer, diplomat, etc.), term info.  
- **Country attributes**: region, EU membership, liberal democracy index, gender equality index.  
- **Voting/opinions**: dissent, concurrence, separate opinions.  

**Target variable:** `progovernment_vote` (1 = pro-government, 0 = non-pro-government):contentReference[oaicite:0]{index=0}.  

---

## Methods
1. **Exploratory Data Analysis (EDA)**  
   - Summary statistics for key features.  
   - Visualizations: voting trends by gender, EU membership, judge background, respondent country.  
2. **Feature Engineering**  
   - Encoded categorical features (judge background, country, region).  
   - Created interaction terms (e.g., `judge_home_bias`).  
   - Normalized continuous variables (age, democracy indices).  
3. **Modeling Approaches**  
   - Baselines: Logistic Regression, Naïve Bayes.  
   - Tree-based models: Decision Tree, Random Forest, Gradient Boosted Trees.  
   - Distance-based: k-Nearest Neighbors.  
   - Evaluation via **accuracy** and confusion matrix.  
4. **Submission**  
   - Generated probability predictions (`ids, progovernment_vote`).  
   - Kaggle limited to 20 submissions/day.  

---

## Results
- **Baseline accuracy** (all 0’s): ~55%.  
- **Best models achieved**:  
  - Logistic Regression with feature engineering: ~67% accuracy.  
  - Random Forest with tuned hyperparameters: ~70% accuracy.  
- **Findings**:  
  - Judges from the **respondent’s home country** are more likely to vote pro-government.  
  - **Eastern European judges** had higher pro-government vote tendencies compared to Western Europe.  
  - Gender and professional background showed weaker correlations than expected.  

---

## 🔧 Limitations & Future Work
- Dataset imbalance between **common vs. rare respondent countries**.  
- Need for **calibration metrics** beyond accuracy (e.g., F1, AUC).  
- Explore **ensemble methods** (stacking multiple classifiers).  
- Apply **interpretability tools** (SHAP, LIME) to highlight important features.  

---

## Tech Stack
- Python, Pandas, NumPy, scikit-learn, Matplotlib, Seaborn  
- Jupyter Notebook, Kaggle API  

---

## Authors
- **Zikun (Alex) Xu** – Rochester Institute of Technology  
- DSCI 633 Course Project (Spring 2025)  

---

## 📎 References
- Kaggle competition dataset provided by RIT DSCI 633:contentReference[oaicite:1]{index=1}.  
- European Court of Human Rights: [ECHR Official Site](https://www.echr.coe.int).  

