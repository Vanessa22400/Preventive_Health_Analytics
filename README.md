# Preventive Health Analytics: Understanding Healthcare Cost Drivers
*Using data analytics to identify lifestyle risk factors, predict healthcare costs, and explore prevention strategies.*

**Dataset:** Health insurance dataset (1,338 individuals)  
**Techniques:** SQL analysis, EDA, clustering (K-Means), causal inference (Propensity Score Matching), machine learning (Linear Regression & Random Forest)  
**Key Insight:** Smoking increases healthcare costs by ~**$23,500 per year**, making it the strongest cost driver in the dataset.  

---

# Project Overview

Healthcare systems face a major challenge: **a small portion of individuals generates a disproportionately large share of medical costs**.

This project explores how data analytics can help:

- identify **key drivers of healthcare costs**
- detect **high-risk population segments**
- estimate the **causal impact of lifestyle factors**
- support **preventive healthcare strategies**

The analysis combines **data analytics, statistical reasoning, and machine learning** to provide insights that are relevant for both **business decision-making and public health strategy**.

---

# Dataset

The dataset contains anonymized records for **1,338 individuals** and includes demographic and lifestyle information.

| Variable | Description |
|--------|-------------|
| age | Age of the individual |
| sex | Gender |
| bmi | Body Mass Index |
| children | Number of dependents |
| smoker | Smoking status |
| region | Geographic region |
| charges | Annual medical cost |

The average healthcare cost in the dataset is approximately **$13,270**, with a maximum value exceeding **$63,000**, indicating the presence of a **high-cost patient segment**.

---

# Analytical Workflow

The project follows a structured analytics workflow:

1. **SQL-Based Analysis**
2. Exploratory Data Analysis (EDA)
3. Risk Segmentation
4. Causal Inference
5. Predictive Modeling
6. Strategic Interpretation

This approach mirrors the type of analysis commonly performed in **data analytics, consulting, and healthcare strategy teams**.

---

# SQL-Based Analysis

Initial exploration was conducted using **SQL queries**, simulating a real analytics workflow where data is extracted from databases before further modeling.

Key questions investigated:

- How do healthcare costs differ between **smokers and non-smokers**?
- How do costs change across **age groups**?
- Does **BMI influence healthcare spending**?
- Do risk factors interact (e.g., **smoking + obesity**)?

### Smoking vs Healthcare Costs

| Smoking Status | Population | Avg Cost |
|---------------|-----------|----------|
| Non-smokers | 1064 | $8,434 |
| Smokers | 274 | $32,050 |

Smokers represent only **20% of the population** but generate **almost four times higher healthcare costs**.

---

### Age and Healthcare Costs

| Age Group | Avg Cost |
|-----------|----------|
| 18–29 | $9,182 |
| 30–39 | $11,739 |
| 40–49 | $14,399 |
| 50+ | $17,903 |

Healthcare costs increase steadily with age, reflecting the growing likelihood of chronic conditions.

---

### BMI and Healthcare Costs

| BMI Category | Avg Cost |
|--------------|----------|
| Normal | $10,282 |
| Overweight | $10,988 |
| Obese | $15,552 |

More than **50% of individuals in the dataset are classified as obese**, suggesting that weight-related health risks affect a large portion of the population.

---

### Risk Cohorts (Smoking + BMI)

| Smoking | BMI | Avg Cost |
|-------|------|----------|
| Smoker | Obese | $41,558 |
| Smoker | Overweight | $22,496 |
| Smoker | Normal | $19,839 |
| Non-smoker | Obese | $8,843 |
| Non-smoker | Overweight | $8,258 |
| Non-smoker | Normal | $7,516 |

Individuals who are both **smokers and obese generate the highest healthcare costs**, demonstrating how lifestyle risk factors can **amplify each other**.

---

# Exploratory Data Analysis

Healthcare costs show a **highly skewed distribution**, where most individuals incur moderate expenses but a small group generates very high costs.

📊 *Insert figure:*  
`Distribution_of_Healthcare_Costs.png`

This pattern is typical in healthcare systems, where **high-cost patients represent a small but critical segment**.

---

# High-Cost Patient Segment

To focus on this group, the top **20% of medical expenses** were defined as **high-cost patients**.

- High-cost threshold: **$20,260**
- High-cost population: **268 individuals**

Smoking is strongly associated with this segment:

| Smoking Status | High-Cost Patients |
|---------------|-------------------|
| Non-smoker | 60 |
| Smoker | 208 |

Smokers account for **the majority of high-cost cases**.

---

# Risk Score Analysis

A simple **health risk score** was created using:

- Smoking status
- BMI above 30
- Age above 50

| Risk Score | Avg Cost |
|-----------|----------|
| 0 | $6,477 |
| 1 | $8,045 |
| 2 | $16,066 |
| 3 | $37,032 |
| 4 | $47,369 |

Healthcare costs increase dramatically as risk factors accumulate.

📊 *Insert figure:*  
`Average_Cost_by_Risk_Score.png`

This demonstrates how **multiple lifestyle risks combine to drive healthcare spending**.

---

# Customer Segmentation (K-Means Clustering)

K-Means clustering was applied to identify **natural population segments**.

Four clusters emerged:

| Cluster | Profile | Avg Cost |
|--------|--------|---------|
| 3 | Young & Healthy | $5,397 |
| 2 | Family Segment | $10,709 |
| 0 | Older Population | $12,593 |
| 1 | High-Risk Lifestyle | $40,308 |

The **high-risk cluster** shows dramatically higher medical costs and elevated BMI levels.

This type of segmentation is commonly used to support:

- targeted prevention programs
- personalized healthcare strategies
- risk-based resource allocation

---

# Causal Inference: Smoking Impact

To estimate the **causal impact of smoking**, Propensity Score Matching (PSM) was used to compare smokers with non-smokers who have similar characteristics.

| Group | Avg Cost |
|------|----------|
| Smokers | $32,050 |
| Matched Non-Smokers | $8,540 |

Estimated causal effect:

**Smoking increases annual healthcare costs by approximately $23,500 per individual.**

This reinforces smoking as the **largest cost driver in the dataset**.

---

# Predictive Modeling

Two models were trained to predict healthcare costs.

| Model | MAE | R² |
|------|------|------|
| Linear Regression | $4,181 | 0.78 |
| Random Forest | $2,560 | 0.86 |

The Random Forest model significantly improves prediction accuracy.

📊 *Insert figure:*  
`Feature_Importance_Random_Forest.png`

Feature importance shows that:

1. **Smoking status** (strongest predictor)
2. **BMI**
3. **Age**

are the main drivers of healthcare costs.

---

# Healthcare Cost Drivers Dashboard

Insert figure:
Healthcare_Cost_Dashboard.png

This dashboard summarizes the main drivers of healthcare costs identified in the analysis.

![Healthcare Cost Dashboard](imges/Healthcare_Cost_Dashboard.png)
---

# Key Insights

Several consistent patterns emerge across the analysis:

- **Smoking is the strongest driver of healthcare costs**
- **High BMI significantly increases medical expenses**
- Risk factors **amplify each other**
- A small population segment generates **a large share of healthcare spending**

These insights highlight the potential value of **targeted prevention strategies**.

---

# Limitations

Some limitations of this analysis include:

- Small dataset (1,338 observations)
- Limited health variables
- Cross-sectional data (no longitudinal tracking)
- Simplified causal inference assumptions

Real-world healthcare analytics would benefit from **long-term medical data and richer patient information**.

---

# Future Work

Possible extensions of this project include:

- incorporating **longitudinal healthcare data**
- modeling **disease progression**
- evaluating **real prevention program outcomes**
- building **healthcare decision-support systems**

Combining predictive models with policy simulations could further support **data-driven healthcare strategies**.

---

# Conclusion

This project demonstrates how data analytics can help uncover **key drivers of healthcare costs and identify prevention opportunities**.

By combining **SQL analysis, segmentation, causal inference, and machine learning**, the analysis reveals that lifestyle factors, especially smoking and obesity, play a central role in medical spending.

These insights highlight how **data-driven strategies can improve both cost efficiency and public health outcomes**, illustrating the growing role of analytics in building more sustainable healthcare systems.
