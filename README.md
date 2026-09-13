# 📊 Data Analytics Portfolio

> **Turning raw data into decisions.**

A collection of data analytics and machine learning projects focused on discovering patterns, explaining their business meaning, and translating analytical findings into practical decisions.

This portfolio brings together **exploratory data analysis, statistical analysis, machine learning, customer segmentation, regression, NLP, and interactive data visualization** across four different real-world-style business problems.

---

## 🧠 About This Portfolio

This portfolio is built around one simple idea:

**Data analysis should not stop at a graph or model score.**

The goal of each project is to move through the complete analytical process:

**Business Problem → Data → Analysis → Visualization → Findings → Problem Solved → Decision Making**

Each case study explains not only *what the data shows*, but also:

* What problem is being investigated
* What data is being used
* Why a particular analytical method was selected
* What the graphs are actually telling us
* What patterns were discovered
* What problem the analysis helps solve
* How the findings can support business decisions
* What the model or statistical analysis achieved

---

# 🚀 Projects

## 01 — Telco Customer Churn

### 🎯 Business Problem

Customer churn directly affects recurring revenue. The objective of this project is to understand which customer characteristics are associated with churn and identify areas where retention efforts can be focused.

### 📊 Dataset

**IBM Telco Customer Churn Dataset**

* Customers: **7,043**
* Target: Customer churn
* Main variables explored:

  * Tenure
  * Monthly Charges
  * Total Charges
  * Contract
  * Tech Support
  * Fiber Internet

### 🔬 Methods Used

* Exploratory Data Analysis
* Variance Inflation Factor (VIF)
* Mann-Whitney U Test
* Random Forest
* SHAP-based feature importance
* ROC-AUC evaluation

### 📈 Key Results

* **ROC-AUC:** 0.84
* **Mann-Whitney U test:** p < 0.0001
* Contract and tenure appear among the strongest displayed model-related features.

### 💡 What the Analysis Tells Us

The analysis indicates that churn is not evenly distributed across customers.

Contract type, customer tenure, and monthly charges are important areas to investigate when looking for customers with higher churn risk.

The statistical test also shows a significant difference in the displayed MonthlyCharges distributions between churned and retained customers.

### 🛠 Problem Solved

Instead of treating all customers equally, the analysis provides a way to identify customer characteristics that deserve greater attention in retention analysis.

### 🧭 Decision Making

Businesses can use these findings to:

* Prioritize retention efforts around month-to-month customers
* Investigate pricing and service combinations associated with churn
* Develop lifecycle-specific retention strategies
* Use customer tenure as an additional factor when designing retention campaigns

---

# 02 — RFM Customer Segmentation

### 🎯 Business Problem

A business with thousands of customers cannot efficiently use the same marketing strategy for everyone.

The objective is to identify meaningful customer groups based on purchasing behavior and understand how customer groups contribute to business value.

### 📊 Dataset

**UCI Online Retail Dataset**

Transactional customer data is transformed into behavioral features for segmentation.

### 🔬 Methods Used

* RFM-style customer analysis
* Feature transformation
* Box-Cox transformation
* Standardization
* K-Means Clustering
* Silhouette Score

### 📈 Key Results

* Best displayed cluster count: **K = 4**
* Silhouette Score: **0.62**
* Core Champions:

  * Approximately **14% of customers**
  * Approximately **58% of displayed revenue contribution**

### 📊 What the Graphs Tell Us

The silhouette-score graph compares different values of K.

| Clusters | Silhouette Score |
| -------- | ---------------: |
| K=2      |             0.48 |
| K=3      |             0.53 |
| K=4      |         **0.62** |
| K=5      |             0.55 |
| K=6      |             0.49 |

The highest displayed score occurs at **K=4**, suggesting that four clusters provide the strongest separation among the tested options.

The revenue-contribution visualization shows that the Core Champions group contributes a disproportionately large share of business value compared with its customer count.

### 🛠 Problem Solved

The analysis changes the customer base from one large population into meaningful behavioral groups.

This allows businesses to think about customers differently based on their purchasing behavior and value.

### 🧭 Decision Making

The segmentation can support:

* High-value customer retention
* Loyalty programs
* Targeted marketing campaigns
* Re-engagement of inactive customers
* More efficient marketing-budget allocation
* Different strategies for different customer groups

---

# 03 — Ames House Price Forecasting

### 🎯 Business Problem

Property pricing can be difficult when many property characteristics influence the final sale price.

The objective is to build a model that can estimate property prices while also examining how reliable those predictions are.

### 📊 Dataset

**Ames Housing Dataset**

### 🔬 Methods Used

* Data preprocessing
* Target transformation
* Log transformation
* XGBoost Regression
* Residual analysis
* R²
* RMSE

### ⚙️ Model Configuration

The portfolio uses XGBoost with:

* Estimators: **500**
* Learning rate: **0.03**
* Maximum depth: **4**
* Subsample: **0.8**
* Random state: **42**

### 📈 Key Results

* **R²:** 0.912
* **RMSE:** $14,200

### 📊 What the Graphs Tell Us

The residual distribution is concentrated around the center.

Displayed residual counts:

| Position | Observations |
| -------- | -----------: |
| -3σ      |            3 |
| -2σ      |           14 |
| -1σ      |           68 |
| 0        |      **145** |
| +1σ      |           62 |
| +2σ      |           12 |
| +3σ      |            2 |

This means the majority of displayed residual observations are relatively close to the center, while extreme residuals occur much less frequently.

The performance metrics communicate two different things:

* **R² = 0.912** indicates strong model fit on the reported transformed target.
* **RMSE = $14,200** communicates the reported magnitude of prediction error.

### 🛠 Problem Solved

The project provides a repeatable, data-supported approach to property price estimation instead of relying entirely on subjective valuation.

Residual analysis also helps identify cases where predictions may deserve additional human investigation.

### 🧭 Decision Making

The model can support:

* Initial property valuation
* Price estimation
* Identification of unusual predictions
* Human review of properties with larger errors
* Monitoring model performance over time

---

# 04 — Financial News Sentiment Analysis

### 🎯 Business Problem

Financial analysts can face large volumes of financial news and headlines.

The objective is to automatically classify financial text into sentiment categories so that large collections of information can be processed and reviewed more efficiently.

### 📊 Sentiment Classes

* Negative
* Neutral
* Positive

### 🔬 Methods Used

* NLP
* TF-IDF
* Unigrams + Bigrams
* Complement Naive Bayes
* Classification Report
* Macro F1

### ⚙️ Text Processing

The TF-IDF vectorizer uses:

* Unigrams and bigrams
* `sublinear_tf=True`
* `max_df=0.85`
* `min_df=3`

The classifier uses:

* Complement Naive Bayes
* `alpha=0.5`

### 📈 Key Results

**Macro F1:** 0.854

### 📊 What the Graphs Tell Us

The sentiment distribution shows:

| Sentiment | Distribution |
| --------- | -----------: |
| Neutral   |      **60%** |
| Positive  |          25% |
| Negative  |          15% |

The graph highlights an important characteristic of the dataset: **Neutral headlines are the majority class**.

The classification visualization compares actual sentiment categories with predicted categories.

Displayed values:

* Predicted Negative: **84 / 11 / 5**
* Predicted Neutral: **10 / 89 / 7**
* Predicted Positive: **6 / 8 / 86**

The strongest values appear on the corresponding class positions, while the off-diagonal values represent instances where the classifier confused one sentiment category with another.

### 🛠 Problem Solved

The project converts unstructured financial headlines into structured sentiment information.

Instead of manually reviewing every headline individually, sentiment classification can provide an additional layer of automated information organization.

### 🧭 Decision Making

The analysis can support:

* Financial news monitoring
* Headline prioritization
* Sentiment trend tracking
* Information triage
* Supporting analyst workflows

Sentiment should be treated as a **supporting signal**, rather than an automatic investment decision by itself.

---

# 🧰 Skills & Technologies

### Data Analysis

* Python
* Pandas
* NumPy
* Exploratory Data Analysis
* Statistical Analysis
* Data Cleaning
* Feature Engineering

### Machine Learning

* Scikit-learn
* Random Forest
* K-Means Clustering
* XGBoost
* Naive Bayes
* Model Evaluation

### Statistics

* Mann-Whitney U Test
* VIF
* Silhouette Score
* Residual Analysis

### NLP

* TF-IDF
* N-grams
* Text Classification
* Sentiment Analysis
* Complement Naive Bayes

### Visualization

* Matplotlib
* Seaborn
* Chart.js
* Interactive Charts
* Data Storytelling

### Portfolio Development

* HTML
* CSS
* JavaScript
* Tailwind CSS
* Responsive Design

---

# 📊 Analytical Approach

Every project follows a similar analytical framework:

```text
┌─────────────────────┐
│   Business Problem  │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│     Understand      │
│       the Data      │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│ Clean & Transform   │
│       Data          │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│   Statistical /     │
│  Machine Learning   │
│      Analysis       │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│    Visualization    │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│      Findings       │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│    Problem Solved   │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│   Decision Making   │
└─────────────────────┘
```

The purpose of this workflow is to ensure that analytical work connects back to the original business question.

---

# 📁 Project Structure

```text
data-analytics-portfolio/
│
├── index.html
│
├── README.md
│
├── projects/
│   ├── telco-churn/
│   ├── rfm-segmentation/
│   ├── housing-price/
│   └── sentiment-analysis/
│
├── datasets/
│
└── notebooks/
```

> The exact repository structure may differ depending on how the individual datasets, notebooks, and source files are organized.

---

# 📌 Portfolio Highlights

### 🔍 Four Different Analytics Problems

The portfolio demonstrates four different analytical directions:

**Customer Churn**
→ Predictive classification and customer retention

**Customer Segmentation**
→ Unsupervised learning and marketing strategy

**Housing Prediction**
→ Regression and predictive valuation

**Financial Sentiment**
→ NLP and automated text analysis

This demonstrates the ability to approach different business problems with different analytical techniques rather than applying one model everywhere.

---

# 💡 From Data to Decisions

The main goal of this portfolio is not simply:

> “I built a machine-learning model.”

It is:

> **“I used data to understand a problem, found meaningful patterns, and translated those patterns into information that can support a decision.”**

For every project, the portfolio therefore focuses on three questions:

### 01 — What happened?

The visualizations and statistical analysis reveal patterns in the data.

### 02 — What does it mean?

The findings explain why those patterns matter.

### 03 — What can we do with it?

The decision-making section translates analytical results into practical actions.

---

# 📈 Reported Model Results

| Project             | Metric           | Reported Result |
| ------------------- | ---------------- | --------------: |
| Telco Churn         | ROC-AUC          |        **0.84** |
| Telco Churn         | Mann-Whitney U   |  **p < 0.0001** |
| RFM Segmentation    | Silhouette Score |        **0.62** |
| Housing Forecasting | R²               |       **0.912** |
| Housing Forecasting | RMSE             |     **$14,200** |
| Financial Sentiment | Macro F1         |       **0.854** |

> These are the results displayed in the portfolio and are presented here as reported portfolio outputs.

---

# 🎯 What This Portfolio Demonstrates

This portfolio demonstrates an end-to-end approach to data analytics:

* Understanding business problems
* Working with real-world datasets
* Cleaning and transforming data
* Performing exploratory analysis
* Applying statistical tests
* Building machine-learning models
* Evaluating model performance
* Understanding model behavior
* Creating meaningful visualizations
* Communicating analytical findings
* Translating findings into business decisions

---

# 👤 Author

## Yash Singh

Data Analytics • Machine Learning • Data Visualization • Business Insights


