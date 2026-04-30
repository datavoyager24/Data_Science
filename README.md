<div align="center">

# 👋 Hi, I'm Siva
### Data Scientist | Machine Learning Engineer | NLP Enthusiast

[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)](https://tensorflow.org)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org)

*Turning messy data into business decisions — from food delivery analytics to LLM-powered stock sentiment analysis.*

</div>

---

## 🗂️ Project Portfolio

> A collection of end-to-end Data Science & Machine Learning projects built during my DS/ML program. Each project tackles a real business problem using structured, industry-standard workflows.

---

### 🍔 Project 1 — FoodHub Demand Analysis
**`Exploratory Data Analysis` `Python` `Pandas` `Matplotlib` `Seaborn`**

<details>
<summary><b>📋 Problem, Approach & Key Findings</b></summary>

**Business Problem:**
FoodHub, a NYC food aggregator, needed to understand restaurant demand patterns to improve customer experience and operational efficiency.

**What I did:**
- Cleaned and analyzed 1,898 food orders across 14 cuisine types
- Investigated delivery time patterns across weekdays vs weekends
- Calculated revenue breakdown using tiered commission structure (25% on orders >$20, 15% on orders >$5)
- Identified restaurants with 50+ orders and ratings above 4.0

**Key Findings:**
- American cuisine dominates (~30% of orders); top 4 cuisines cover 80%+ of volume
- Weekend orders outnumber weekdays, yet delivery is ~6 min *faster* on weekends
- 39% of customers never left a rating — a significant blind spot for the business
- Orders over $20 generate disproportionately more revenue despite being a third of volume

**Business Recommendations:**
- Fix weekday delivery capacity (driver availability is the bottleneck)
- Revamp the rating system — break it into sub-ratings (food, delivery, driver) to boost participation
- Invest in premium restaurant partnerships for higher revenue per order

</details>

**Tech Stack:**

| Tool | Purpose |
|------|----------|
| `pandas` | Data loading, cleaning, groupby analysis |
| `matplotlib` / `seaborn` | Distribution plots, heatmaps, bar charts |
| `numpy` | Revenue calculations, time-based aggregations |

---

### 🏦 Project 2 — AllLife Bank Personal Loan Campaign
**`Decision Tree` `Classification` `Hyperparameter Tuning` `GridSearchCV`**

<details>
<summary><b>📋 Problem, Approach & Key Findings</b></summary>

**Business Problem:**
AllLife Bank wanted to convert liability customers (depositors) into personal loan customers. Their last campaign had a 9% conversion rate — they needed to do better.

**What I did:**
- Built a Decision Tree classifier to predict loan purchase probability
- Handled class imbalance through pre/post-pruning techniques
- Used GridSearchCV to tune depth and min-sample parameters
- Visualized the tree to extract human-readable decision rules

**Key Findings:**
- Income, CCAvg (credit card spend), and CD_Account ownership were the strongest predictors
- Post-pruned decision tree generalized better than unpruned (reduced overfitting)
- Feature importance analysis revealed actionable customer segments

**Business Recommendations:**
- Target high-income customers with active CD accounts first
- Track loan defaulters and incorporate that data to further filter prospects
- Build a risk-weighted campaign scoring model using this tree as baseline

</details>

**Tech Stack:**

| Tool | Purpose |
|------|----------|
| `sklearn.tree.DecisionTreeClassifier` | Core classification model |
| `GridSearchCV` | Hyperparameter tuning (depth, min samples) |
| `ConfusionMatrixDisplay` | Model evaluation visualization |
| `pandas` / `numpy` | Feature engineering, data prep |

---

### 💳 Project 3 — Thera Bank Credit Card Churn Prediction
**`Ensemble Methods` `XGBoost` `AdaBoost` `SMOTE` `Class Imbalance`**

<details>
<summary><b>📋 Problem, Approach & Key Findings</b></summary>

**Business Problem:**
Thera Bank was losing credit card customers. Credit cards are high-margin products — the bank needed to identify at-risk customers *before* they left.

**What I did:**
- Compared 5 models: Decision Tree, Random Forest, GBM, AdaBoost, XGBoost
- Handled class imbalance using three strategies: original data, SMOTE oversampling, and random undersampling
- Tuned models using RandomizedSearchCV
- Final model: **AdaBoost with undersampled data → 97.5% recall on test set**

**Key Findings:**
- Top predictors: `Total_Trans_Amt`, `Total_Trans_Ct`, `Total_Revolving_Bal`
- Customers with fewer transactions and lower revolving balance churn at much higher rates
- Elite customers (post-grads, $120K+ income) churn more — indicating a premium product gap
- ~53% of customers are women, yet they show higher attrition → product-fit issue

**Business Recommendations:**
- Introduce split payment / lower interest options to retain low-balance customers
- Create premium card offerings for high-income / high-education segments
- Set up an inactivity alert system for customers inactive 3+ months

</details>

**Tech Stack:**

| Tool | Purpose |
|------|----------|
| `XGBClassifier` | Gradient boosted tree ensemble |
| `AdaBoostClassifier` | Final selected model (best recall) |
| `imblearn` SMOTE / RandomUnderSampler | Class imbalance handling |
| `RandomizedSearchCV` | Efficient hyperparameter search |
| `StandardScaler` | Feature normalization |

---

### 🧠 Project 4 — Bank Customer Churn Neural Network
**`Deep Learning` `TensorFlow/Keras` `SMOTE` `Dropout` `Binary Classification`**

<details>
<summary><b>📋 Problem, Approach & Key Findings</b></summary>

**Business Problem:**
Predict whether a bank customer will leave within the next 6 months using a neural network — enabling proactive retention efforts.

**What I did:**
- Built and compared multiple Neural Network architectures using Keras Sequential API
- Tested Adam and SGD optimizers, with and without Dropout regularization
- Handled class imbalance with both class-weight balancing and SMOTE
- Final model: **NN with Adam optimizer + Dropout** — best recall on validation set

**Key Findings:**
- Model explains ~74% of variance in churn behavior
- 49% of customers are inactive — likely due to limited product offerings (only 4 products available)
- Customers aged 45–55 are most likely to churn (retirement planning gap)
- Female customers show higher churn — possible lack of women-centric products
- Customers from France make up 50% of base — geographic diversification needed

**Business Recommendations:**
- Expand product portfolio to retain 45–55 age group approaching retirement
- Develop women-focused financial products
- Collect more demographic data (job, education) to build segmented models

</details>

**Tech Stack:**

| Tool | Purpose |
|------|----------|
| `TensorFlow` / `Keras` | Neural network architecture (Sequential API) |
| `Dense`, `Dropout` layers | Model building and regularization |
| `SMOTE` (`imblearn`) | Oversampling minority class |
| `StandardScaler` | Feature normalization before NN input |
| `tf.config.experimental.enable_op_determinism()` | Reproducibility for GPU ops |

---

### 📈 Project 5 — Stock Sentiment Analysis with NLP & LLM Summarization
**`NLP` `Transformers` `Sentence-BERT` `Word2Vec` `GloVe` `LLaMA` `Sentiment Analysis`**

<details>
<summary><b>📋 Problem, Approach & Key Findings</b></summary>

**Business Problem:**
An investment startup needed to process high-volume financial news to gauge market sentiment and surface actionable insights for stock analysts — faster than any human team could.

**What I did:**
- Built a full NLP pipeline: text cleaning → embeddings → sentiment classification
- Compared three embedding strategies: Word2Vec, GloVe, and Sentence-BERT (transformer-based)
- Trained classifiers (Random Forest, GBM, AdaBoost, Decision Tree) on top of each embedding
- Used **LLaMA (open-source LLM)** to generate 100–200 word weekly news summaries and extract top 3 positive/negative market-moving events
- Structured LLM output as JSON for downstream analyst consumption

**Key Findings:**
- Sentence-BERT embeddings outperformed Word2Vec and GloVe on sentiment classification
- LLM-generated summaries successfully condensed weeks of news into actionable bullet points
- Weekly positive/negative event extraction gave analysts a structured signal without reading full articles

**Recommendations:**
- Tune LLM prompt templates for domain-specific financial vocabulary
- Experiment with `temperature` and `top_p` for better summary diversity
- Fine-tune a domain-specific sentiment model on financial corpora (e.g., FinBERT)

</details>

**Tech Stack:**

| Tool | Purpose |
|------|----------|
| `sentence-transformers` (SBERT) | State-of-the-art sentence embeddings |
| `gensim` Word2Vec / GloVe | Traditional word embedding baselines |
| `LLaMA` (via HuggingFace) | News summarization & event extraction |
| `NLTK` | Tokenization, stopword removal, stemming |
| `GradientBoostingClassifier` | Best performing traditional classifier |
| `tqdm` | Progress tracking for large batch inference |

---

## 🛠️ Core Skills

```
Machine Learning        → Classification, Regression, Ensemble Methods, Neural Networks
NLP & Text Analytics    → Embeddings, Sentiment Analysis, LLM Prompting, Summarization
Data Wrangling          → Pandas, NumPy, feature engineering, missing value treatment
Class Imbalance         → SMOTE, undersampling, class-weight tuning
Model Evaluation        → F1, Recall, AUC-ROC, Confusion Matrix, cross-validation
Visualization           → Matplotlib, Seaborn, feature importance plots
```

---

## 📊 Stats at a Glance

| Project | Domain | Best Model | Key Metric |
|---------|--------|-----------|------------|
| FoodHub Analysis | Food-Tech | EDA | Revenue $6,166 identified |
| Loan Campaign | Banking | Decision Tree (pruned) | Precision-focused |
| Credit Card Churn | Banking | AdaBoost + Undersample | 97.5% Recall |
| Neural Net Churn | Banking | Keras NN + Dropout | ~74% accuracy |
| Stock Sentiment NLP | FinTech | SBERT + GBM + LLaMA | LLM-structured output |

---

<div align="center">

*Built with 🐍 Python · Trained on real business problems · Focused on actionable insights*

</div>
