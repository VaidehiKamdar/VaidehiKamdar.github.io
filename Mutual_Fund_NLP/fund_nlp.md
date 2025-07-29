---
layout: default
title: "Mutual Fund Categorization using NLP"
---

# Mutual Fund Categorization using Natural Language Processing

## Overview

This project explores how **Natural Language Processing (NLP)** can be applied to classify mutual funds based on their unstructured strategy summaries. By replacing traditional structured data-based categorization (like from Form N-1A), we apply machine learning and semantic modeling to textual fund descriptions to assign them into one of three styles:

- Balanced Fund (Low Risk)  
- Fixed Income Long Only  
- Equity Long Only

We experiment with TF-IDF, Word2Vec, custom embeddings, and multiple classifiers to build an intelligent tagging system.

## Tools & Techniques

- **Text Preprocessing**: Tokenization, stop word removal, lemmatization
- **Vectorization**:
  - TF-IDF
  - Word2Vec + sentence barycenters
- **Knowledge Base Construction**: Custom Skip-Gram model to extract semantically similar words by category
- **Sentence Scoring**: Cosine similarity between sentences and style-specific keywords
- **Machine Learning Classifiers**:
  - Logistic Regression
  - Multinomial Naive Bayes
  - SVM
  - Random Forest
  - XGBoost
  - Ensemble Voting Classifier

## Key Results

- **Best Performance**:  
  - TF-IDF + Random Forest achieved **94% accuracy** on test set  
  - Strong F1 scores across all fund styles:  
    - Equity Long: 0.95  
    - Fixed Income Long: 0.96  
    - Balanced: 0.80

- **Word2Vec models** performed lower, showing TF-IDF remains competitive for small datasets.

- **Ensemble models** added marginal improvements but increased complexity.

## Visuals

![Mutual Fund Classification Result](/indeximages/mutualfunds.png)

*Performance comparison across classifiers for TF-IDF and Word2Vec*

## Summary

This project demonstrates that machine learning + NLP can effectively automate mutual fund categorization from strategy descriptions. The methodology offers a scalable alternative to manual tagging or hardcoded rule-based systems — a major step forward for robo-advisors, fund screeners, and investor platforms.

---

📂 [Return to Portfolio Home](/)
