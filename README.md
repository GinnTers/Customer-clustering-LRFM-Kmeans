# Customer Segmentation using LRFM & K-Means  
> Project conducted: May 2025 (was not uploaded at the time)

Applying LRFM modeling and K-Means clustering to segment customers for targeted marketing and customer lifetime value optimization.

---

## Introduction

This project aims to analyze customer transactional data to identify meaningful segments based on their purchasing behavior and relationship with the business. By leveraging **LRFM modeling (Length, Recency, Frequency, Monetary)** and **K-Means clustering**, it supports personalized marketing strategies and business decision-making.

The project was conducted as part of the **Data Science coursework at the University of Economics - University of Danang (DUE)**.

---

## Dataset

### Data Source  
- **File:** `ITBLogisticDataset.xlsx  `
- **Rows:** 180,519  
- **Columns:** 53  
- **Origin:** Transactional dataset from DataCo Global’s online sales system (2011–2014).  
- **Kaggle Dataset:** [ITBLogisticDataset](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis?select=DataCoSupplyChainDataset.csv&fbclid=IwZXh0bgNhZW0CMTAAYnJpZBExOHpkQlRZZ2Npcms0Mm1xbQEevfLmEOE3AV266rm7x1DFe5NxkfXlWzOIZEYeNJZCOYQzpDcVUmHqk-w55NM_aem_UrGbZzRO1qdZZ5Il6uounw)

### Key Fields
- `Customer Id`: Customer identifier  
- `Order Id`: Order identifier  
- `Order Date`: Purchase date  
- `Order Item Total`: Order value  
- `Days for shipping (real)`: Actual shipping days  
- `Customer Segment`: Customer type  
- `Category Name`: Product category  
- `Shipping Mode`: Shipping method

---

## Tools & Technologies

- **Languages:** Python  
- **Libraries:** pandas, numpy, scikit-learn, matplotlib, seaborn, statsmodels  
- **Techniques:** Clustering, LRFM Modeling, Hypothesis Testing (MANOVA, ANOVA, Tukey HSD)

---

## Project Workflow

### 1. Data Preparation  
- Loaded dataset and selected relevant columns.  
- Processed missing values, removed duplicates, standardized date formats.  
- Calculated LRFM metrics per customer:
  - **Length (L):** Duration between first and last purchase.
  - **Recency (R):** Days since last purchase.
  - **Frequency (F):** Total number of purchases.
  - **Monetary (M):** Total spending.

### 2. Feature Scaling  
- Normalized LRFM metrics to prepare for clustering.

### 3. Clustering with K-Means  
- Determined optimal number of clusters using **Elbow Method** and **Silhouette Score**.  
- Applied K-Means clustering to segment customers.  
- Analyzed cluster characteristics to profile customer segments.

### 4. Hypothesis Testing  
- **MANOVA:** Tested overall differences across clusters on LRFM variables.  
- **ANOVA:** Tested each LRFM variable individually across clusters.  
- **Post-hoc Analysis (Tukey HSD):** Identified specific group differences.

### 5. Customer Lifetime Value Analysis  
- Calculated **CLV** for each customer using:
- **CLV = (Monetary / Frequency) * Frequency * (Length / 365)**
- Compared average CLV across clusters and customer segments to inform marketing strategies.

---

## Results

Key customer segments identified:

| Cluster | Description | Characteristics |
|---------|-------------|-----------------|
| 0 | VIP Loyal Customers | Long relationship, high frequency and monetary value |
| 1 | Lost Customers | High recency, low length and spending |
| 2 | Potential Loyalists | Medium recency, high length and stable spending |
| 3 | Newcomers | Low length, low frequency and spending |

**Insights:**
- Cluster 0 contributes highest CLV and should be prioritized for loyalty programs.  
- Cluster 2 has potential to convert into loyal customers through engagement strategies.  
- Clusters 1 & 3 require tailored reactivation or onboarding campaigns.

For detailed insights and statistical test results, refer to **project_report.pdf**.

---

## How to Use

1. Clone this repo and open `main.ipynb`.  
2. Run the notebook sequentially to reproduce:
 - Data preparation
 - LRFM modeling
 - Clustering
 - Hypothesis testing
 - CLV calculation
3. Adjust file paths if running locally.

---

## Learning Outcomes

- Applied advanced customer segmentation techniques using LRFM and K-Means.  
- Performed statistical hypothesis testing (MANOVA, ANOVA, Tukey HSD) for validation.  
- Developed business insights to drive data-driven marketing decisions.  
- Strengthened end-to-end data science workflow implementation skills.
