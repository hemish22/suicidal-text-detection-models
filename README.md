# Suicidal Text Detection using Machine Learning and Transformer Models

This project focuses on the detection of suicidal ideation in user-generated text. The primary objective is to classify text as either **Suicidal** or **Non-Suicidal** using both traditional Machine Learning models and a Transformer-based model (BERT). The project explores model performance, preprocessing steps, and key considerations when working with sensitive mental health data.

---

## 1. Motivation

With the increasing use of social media as an outlet for emotional expression, timely detection of suicidal intent can enable early intervention. Automated suicidal text detection systems can support mental health professionals, crisis helplines, and content moderation teams by identifying high-risk content efficiently.

---

## 2. Dataset

The dataset consists of posts collected from Reddit communities:

| Subreddit        | Label                             | Purpose                                  |
|------------------|-----------------------------------|------------------------------------------|
| r/SuicideWatch   | Suicidal                          | High-risk expressions and ideations      |
| r/depression     | Non-suicidal (emotional distress) | General mental health concerns           |
| r/teenagers      | Non-suicidal (neutral)            | Baseline non-mental health conversations |

Data was collected using the **Pushshift API** and cleaned for research usage. Standard preprocessing was applied (lowercasing, special character removal, stopword removal, and tokenization based on model requirements).

---

## 3. Models Implemented

| Model                                                              | Type              | Description                                                           |
|--------------------------------------------------------------------|-------------------|-----------------------------------------------------------------------|
| **Logistic Regression**                                            | Traditional ML    | Baseline linear classifier using TF-IDF vectorization                 |
| **Gaussian Naive Bayes (GNB)**                                     | Traditional ML    | Probabilistic classifier assuming feature independence                |
| **BERT (Bidirectional Encoder Representations from Transformers)** | Transformer Model | Contextual embedding-based model fine-tuned for binary classification |

---

## 4. Approach

### Preprocessing:
- Text normalization
- Tokenization (TF-IDF for ML models, WordPiece tokenizer for BERT)
- Train-Test split (commonly 80:20)

### Training:
- ML models trained on TF-IDF vectors
- BERT fine-tuned using HuggingFace transformers with GPU support where available

### Evaluation Metrics:
- Accuracy
- Precision
- Recall (emphasis)
- F1-Score

---

## 5. Performance Summary

| Model                   | Strengths                                       | Limitations                               |
|-------------------------|-------------------------------------------------|-------------------------------------------|
| **Logistic Regression** | Fast, interpretable                             |  Limited handling of contextual meaning   |
| **GNB**                 | Lightweight, simple                             |  Performs poorly with correlated features |
| **BERT**                | Best contextual understanding, highest accuracy | Requires more resources and training time |

*In most experiments, **BERT outperformed the traditional models**, particularly in minimizing false negatives (critical in suicidal text detection).*

---

## 6. Ethical Considerations
•	This project is intended for research and educational purposes only.
•	Automated predictions should not replace professional psychological evaluation.
•	If you or someone you know is in crisis, please seek immediate help from certified mental health professionals.

---

## 7.License
This project is released under the MIT License.
See the LICENSE file for details.
