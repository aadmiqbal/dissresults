# 📰 Article-Level Political Bias Classification (AllSides) — Results

This repository contains the **results** from my dissertation on detecting and classifying political bias in news articles (**Left / Center / Right**). I compare **traditional ML** (Naïve Bayes, Logistic Regression, SVM, Random Forest, XGBoost) against **transformer models** (e.g., BERT family) on the AllSides corpus (~37k articles).

**In short:** classical models with TF-IDF plus features like topics, sentiment, and lexical cues are competitive, but **BERT/RoBERTa** achieve the strongest **in-domain** (random-split) macro-F1. Performance **drops on cross-publisher** (media-split) tests unless **brand mentions are removed** and/or additional linguistic cues are leveraged. The results highlight the importance of **data quality**, **feature design**, and **domain-shift evaluation** for any real-world deployment.

---

# 📁 What’s inside 

Each folder groups JSON run artifacts (configs, metrics, confusion matrices) for a theme or ablation:

* [`countVsTfidf/`](./countVsTfidf) – Count vs TF-IDF baselines
* [`TfidfKbest/`](./TfidfKbest) – TF-IDF + SelectKBest
* [`smote/`](./smote) – Class-balancing (SMOTE)
* [`scaler/`](./scaler) – Feature scaling variants
* [`lda/`](./lda) – Topic features (LDA)
* [`vader/`](./vader) – Sentiment features (VADER)
* [`lexical/`](./lexical) – Lexical / empirical cues (e.g., POS ratios, hedges)
* [`biasfeatures/`](./biasfeatures) – Bias-lexicon variants
* [`brandremoval/`](./brandremoval) – Removing publisher/brand mentions
* [`combinationexperiments/`](./combinationexperiments), [`combinationexperiments2/`](./combinationexperiments2) – Combined feature settings & ablations.
