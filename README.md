# Decoding the 2024 Lok Sabha Elections 🇮🇳

This repository contains an end-to-end data analysis project on the **2024 Lok Sabha Elections** of India.  
It explores **state & constituency patterns**, **party performance**, **politician profiles**, and builds **machine learning models** to study election outcomes using Python and Jupyter Notebook.

---

## 📁 Repository Structure

- `Election_Analysis.ipynb`  
  Main Jupyter Notebook containing data cleaning, EDA (Exploratory Data Analysis), visualizations, and model building.

- `reports/election Decoding the 2024 Lok Sabha Elections.pdf`  
  Analytical report summarizing key findings and visuals from the project.

- `data/` *(to be created by you)*  
  - `raw/` – Original datasets (constituency-wise, candidate-wise, party-wise election data).  
  - `processed/` – Cleaned and feature-engineered datasets used for modelling.

- `README.md`  
  Project documentation (this file).

- `requirements.txt` *(optional but recommended)*  
  Python package dependencies for reproducibility.

---

## 🎯 Project Goals

The main objectives of this project are:

1. **State & Constituency Level Analysis**  
   Understand how constituencies are distributed across states and how this links to population.

2. **Party Level Performance Analysis**  
   Study which parties:
   - Contested in the most constituencies and states.
   - Won the most constituencies.
   - Had favourable / unfavourable win–loss ratios.

3. **Politician-Level Analytics**  
   Explore:
   - Gender distribution of candidates and winners.  
   - Educational qualifications of politicians.  
   - Age and its relationship with election participation.  
   - Category-wise (General / SC / ST) representation and results.  
   - Criminal cases, assets and liabilities.

4. **Machine Learning Modelling**  
   Prepare features from the election dataset and compare multiple classification models to understand which factors are most useful for predicting election outcomes.

---

## 📊 1. State & Constituency Level Analysis

**Question:** What is the distribution of constituencies across all states?

Key points covered in the notebook & report:

- States like **Uttar Pradesh, Maharashtra, and West Bengal** have the highest number of constituencies.
- Constituency allocation is based on historical population data and remains frozen until **2026**.
- Despite changes in population (e.g., Bihar), states like West Bengal still rank highly in constituency count due to that historical rule.

A **sunburst chart** is created to show the hierarchical relationship:

- India → State → Constituency

This helps visualise how representation is distributed across states.

---

## 🏳️ 2. Party Level Analysis

### 2.1 Presence Across Constituencies & States

**Question:** Which parties have been present in the most constituencies and states?

Insights:

- **BJP (Bharatiya Janata Party)** and **INC (Indian National Congress)** are present across the maximum constituencies and states.
- **BJP** leads in number of constituencies contested.  
- **INC** maintains a wide geographical spread across states.  
- Regional parties are mostly limited to a handful of states.

### 2.2 Constituency Wins

**Question:** Which party has won the most constituencies?

- In the 2024 analysis, **BJP** remains the leading party in terms of constituencies won.
- **INC** stands second, but with significantly fewer constituencies compared to BJP.

*(Adjust exact numbers in the notebook and report as per your final dataset.)*

### 2.3 Win vs Loss Ratios

**Question:** What is the general Win vs Loss relationship for parties?

- 2024 results are highly favourable for some parties (e.g., BJP and key regional allies) compared to others.
- Many parties show a much higher **loss** count than **wins**, indicating concentrated success in a few strongholds.

### 2.4 NOTA Analysis

- The project also includes **state-wise NOTA (None Of The Above) vote count**, highlighting where NOTA participation is relatively higher.

---

## 🧑‍💼 3. Politician-Level Analytics

### 3.1 Gender Representation

- Female participation remains significantly lower than male participation.
- However, the **win percentage of female candidates** is slightly better than their participation percentage, indicating higher relative success when they do contest.

### 3.2 Educational Qualifications

**Question:** What is the educational qualification of our politicians?

- A majority of winning politicians are **Graduate+**, indicating that education may have a positive association with electoral success.
- A meaningful minority still do **not** possess a professional degree, raising questions about the role of formal education in leadership.

### 3.3 Age & Politics

**Question:** What is the relationship between age and politics?

- Politics continues to favour **middle-aged to older candidates**.
- Age-group based plots help understand which age brackets are most politically active and successful.

### 3.4 Category (General / SC / ST) and Results

**Question:** What relation does the politician category have with election results?

- Participation and winning ratios across General, SC, and ST categories are analysed.
- The General category tends to show a **higher winning ratio** than SC/ST candidates, though SC/ST representation remains important for inclusive democracy.

### 3.5 Criminal Cases

**Questions:**

- How many politicians have criminal cases?
- Does age or party correlate with criminal cases?

Insights:

- A **non-trivial number** of politicians have been associated with criminal cases.
- Multiple cases for the same person raise serious concerns.
- The project highlights the importance of **voter responsibility** in choosing candidates with clean records.

### 3.6 Assets vs Liabilities

The assets and liabilities of winning politicians are plotted (often state-wise or party-wise).

Observations:

- There is a wide variation in asset levels among winning candidates.
- No simple, linear relationship between assets and liabilities emerges in this analysis.

---

## 🤖 4. Machine Learning: Model Preparation & Comparison

### 4.1 Feature Selection & Engineering

The modelling dataset includes features such as:

- **State** and **constituency** (encoded appropriately)
- **Party**
- **Gender**
- **Age / Age group**
- **Category (General / SC / ST)**
- **Education level (grouped into High / Medium / Low)**
- **Criminal cases (count / categories)**
- **Assets & liabilities (bucketed or log-transformed where needed)**

Education is grouped into three levels, for example:

- **High Education:** `Post Graduate`, `Doctorate`, `Graduate Professional`
- **Medium Education:** `Graduate`, `12th Pass`
- **Low Education:** `10th Pass`, `8th Pass`, `5th Pass`, `Literate`,  
  `Illiterate`, `Others`, `Not Available`

You can adapt and refine these groupings as per your dataset.

### 4.2 Models & Metrics

The notebook:

- Trains **multiple classification models** (e.g., Logistic Regression, Random Forest, XGBoost, etc.) to predict whether a candidate will **win** or **lose**.
- Compares **model performance** using metrics such as:
  - Accuracy
  - Precision / Recall
  - F1-score
- Summarises which features are most influential in predicting election outcomes.

*(Refer to `Election_Analysis.ipynb` for exact models, hyperparameters, and plots.)*

---

## 🔍 Key Insights (Summary)

- Representation across constituencies is skewed toward a few large states, based on historical population data.  
- BJP dominates both in contests and victories in 2024; INC remains the second-largest national presence but with much lower wins.  
- Gender representation is highly unequal, but the win percentage for female candidates is slightly better than their participation percentage.  
- A majority of winning politicians are Graduate+, indicating that education may positively influence electoral success.  
- Age-wise, politics tends to favour middle-aged to older candidates.  
- Category-wise, General candidates have a higher winning ratio than SC/ST candidates.  
- A non-trivial number of politicians have criminal cases, raising important questions for voters and policymakers.  
- Machine learning models provide an initial lens to see which factors may contribute most to electoral success.  

---

## 🚀 Future Work & Extensions

- Add more granular features like vote share, margin of victory, turnout percentages.  
- Build state-specific models to capture regional patterns.  
- Explore time-series analysis using data from multiple election years to study trends.  
- Deploy a simple web dashboard (e.g., Streamlit) for interactive exploration of the results.  

---
