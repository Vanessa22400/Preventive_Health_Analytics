# Preventive Health Analytics  
*Identifying healthcare cost drivers and exploring prevention strategies using analytics, causal inference and AI-assisted insights.*

**Dataset:** Health insurance dataset (1,338 individuals)  
**Techniques:** SQL analysis, exploratory data analysis (EDA), clustering (K-Means), causal inference (Propensity Score Matching), machine learning (Linear Regression & Random Forest), experimental design (A/B testing logic), Retrieval-Augmented Generation (RAG)  
**Key Result:** Smoking increases healthcare costs by approximately **$23,500 per patient per year**, making it the strongest cost driver in the dataset.

---

## Business Context

Healthcare systems face a growing challenge: medical costs continue to rise, and a significant portion of these expenses is associated with **preventable lifestyle risk factors**.

For insurers, healthcare providers and public health organizations, understanding **what drives healthcare spending** is essential for designing effective prevention strategies and allocating resources efficiently.

Key questions include:

- Which factors most strongly influence healthcare costs?
- Are there identifiable **high-risk population segments**?
- Can prevention strategies reduce long-term healthcare expenses?

Although the dataset used in this project is public, the analysis is framed as a **real strategic problem in healthcare analytics**, where data-driven insights can support both **financial sustainability and improved population health outcomes**.

---

## Dataset

The analysis uses the **Health Insurance Dataset** available on Kaggle.

Source:  
https://www.kaggle.com/datasets/mirichoi0218/insurance

Dataset characteristics:

- **1,338 observations**  
- **7 variables**

Main variables:

- `age` – age of the insured individual  
- `sex` – gender  
- `bmi` – body mass index  
- `children` – number of dependents  
- `smoker` – smoking status  
- `region` – geographic region  
- `charges` – annual healthcare costs  

The dataset is **fully anonymized** and contains no missing values.

Healthcare costs vary significantly across individuals, with values ranging from roughly **$1,000 to more than $60,000 per year**, which makes it suitable for analyzing **cost drivers and risk segmentation**.

---

## Problem Statement

Healthcare costs are highly uneven across individuals, with a relatively small group generating a large share of total expenses.

The main question guiding this project is:

**Which lifestyle and demographic factors drive healthcare costs, and how can these insights support prevention-oriented decision-making?**

The analysis aims to move beyond simple cost prediction and explore how data can support **risk identification, prevention strategies and healthcare planning**.

---

## Objectives

- Identify key drivers of healthcare costs  
- Perform structured exploratory data analysis (EDA)  
- Segment the population into meaningful **risk cohorts**  
- Estimate the causal impact of smoking on healthcare costs  
- Build predictive models to forecast medical expenses  
- Translate technical findings into **business and prevention insights**  
- Demonstrate how analytics insights can be combined with **AI-based knowledge retrieval (RAG)**

---

## Methodology

1. **SQL-Based Exploration**  
   The dataset is loaded into a SQLite database to simulate a real analytics workflow where data is first queried and explored using SQL.

2. **Exploratory Data Analysis**  
   Distribution analysis and visualizations are used to identify structural patterns in healthcare spending.

3. **Risk Cohort Segmentation**  
   Individuals are grouped into risk cohorts based on lifestyle factors such as smoking and BMI.

4. **Health Risk Scoring**  
   A simple risk score combining smoking status, BMI and age is created to measure cumulative risk exposure.

5. **Clustering (K-Means)**  
   Unsupervised learning is used to identify natural population segments.

6. **Causal Inference (Propensity Score Matching)**  
   Smokers are matched with comparable non-smokers to estimate the causal effect of smoking on healthcare costs.

7. **Predictive Modeling**  
   Linear Regression and Random Forest models are used to estimate healthcare expenses.

8. **Experiment Design (A/B Testing Logic)**  
   A conceptual experiment evaluates how smoking cessation programs could impact healthcare costs.

9. **AI Extension (RAG Prototype)**  
   A second notebook demonstrates how analytics insights can be combined with external health knowledge using Retrieval-Augmented Generation.

---

## Tools & Technologies

- Python (Pandas, NumPy)  
- Scikit-learn  
- SQL (SQLite)  
- SentenceTransformers  
- Matplotlib  
- Seaborn  
- Machine Learning (Random Forest, Linear Regression)  
- Causal Inference (Propensity Score Matching)  
- Clustering (K-Means)

---

## Exploratory Data Analysis Highlights

The exploratory analysis revealed several structural patterns:

- **Healthcare costs are highly skewed**  
  Most individuals generate moderate expenses, while a small portion of the population incurs very high medical costs.

- **Smoking strongly influences healthcare spending**  
  Smokers represent roughly **20% of the population** but generate dramatically higher costs.

- **BMI contributes to higher expenses**  
  Individuals classified as obese have average medical costs roughly **50% higher** than those with normal BMI.

These insights guided the subsequent segmentation and modeling stages.

---

## Healthcare Cost Drivers Dashboard

![Healthcare Cost Dashboard](images/Healthcare_Cost_Dashboard.png)

**Figure:** Summary dashboard highlighting cost distribution, risk score effects, BMI impact and feature importance from the predictive model.

---

## Modeling Approach

Two complementary modeling approaches were used.

**Regression Task**

Predict annual healthcare costs using demographic and lifestyle variables.

**Classification Perspective**

Identify individuals belonging to the **high-cost patient segment** (top 20% of expenses).

The goal is not only prediction accuracy but also **interpretability**, enabling the identification of actionable cost drivers.

---

## Model Performance

Linear Regression results:

- **R²:** 0.78  
- **MAE:** ~$4,181  

Random Forest results:

- **R²:** 0.86  
- **MAE:** ~$2,560  

The Random Forest model significantly improves predictive accuracy, suggesting that healthcare costs involve **non-linear interactions between risk factors**.

From a business perspective, these models help identify individuals who may generate higher medical expenses and may benefit from **preventive interventions**.

---

## Key Insights

Several important insights emerge across the analysis:

- **Smoking is the strongest cost driver**  
  Causal inference estimates that smoking increases healthcare costs by approximately **$23,500 per individual per year**.

- **Risk factors accumulate**  
  Individuals combining smoking and obesity represent the **highest-cost cohort**.

- **Lifestyle risks strongly influence healthcare spending**  
  BMI and age also contribute to increased healthcare utilization.

- **High-cost patients represent a small population segment**  
  Yet they account for a disproportionate share of healthcare expenses.

---

## Business Impact

The insights from this analysis suggest several practical applications:

**Prevention Programs**

Smoking cessation initiatives could significantly reduce long-term healthcare costs.

**Targeted Interventions**

Risk cohort identification allows healthcare organizations to prioritize individuals with multiple risk factors.

**Resource Allocation**

Predictive models can support better forecasting of healthcare expenditures.

**Strategic Planning**

Understanding cost drivers helps insurers and healthcare providers design prevention strategies that benefit both organizations and patients.

---

## Limitations

Some limitations should be considered:

- **Dataset size:** The dataset contains only 1,338 observations.  
- **Limited variables:** Important health indicators such as diet, medical history and physical activity are not included.  
- **Cross-sectional data:** The dataset represents a single moment in time rather than long-term patient histories.

Despite these limitations, the project demonstrates how analytics can reveal meaningful patterns in healthcare cost data.

---

## Next Steps

Possible future developments include:

- Incorporating additional healthcare datasets  
- Testing alternative machine learning models  
- Developing an automated SQL pipeline  
- Building an interactive dashboard for stakeholders  
- Running real experimental interventions such as smoking cessation programs

---

## Repository Structure

```
.
├── notebooks
│   ├── Preventive_Health_Analytics.ipynb
│   └── Preventive_Health_Assistant_RAG.ipynb
├── images
│   └── Healthcare_Cost_Dashboard.png
├── requirements.txt
└── README.md
```

---

## AI Extension: Preventive Health Assistant (RAG)

A second notebook in this repository demonstrates how the analytical insights can be extended using **Retrieval-Augmented Generation (RAG)**.

This prototype combines:

- insights from the main analysis  
- external health knowledge about lifestyle risks  

The system retrieves relevant information to answer questions about **health risks and prevention strategies**.

This illustrates how analytics and AI can be combined to build **decision-support tools focused on preventive healthcare**.

---

## Conclusion

This project demonstrates how structured data analysis can transform healthcare cost data into meaningful insights.

The analysis identified key lifestyle risk factors, quantified their impact on medical expenses and explored prevention-oriented strategies.

Beyond predictive modeling, the project emphasizes **interpretability, strategic insight and practical decision support**, showing how analytics and AI can contribute to more sustainable healthcare systems.
