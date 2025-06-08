# 🧠 Task 2 – Sentiment and Thematic Analysis

This task focuses on quantifying user sentiment and uncovering key themes in reviews for Ethiopian banking apps: **CBE**, **BOA**, and **Dashen Bank**. The goal is to surface actionable insights about user satisfaction and pain points.

---

## 🎯 Objectives

- Quantify review sentiment using transformer-based and rule-based models.
- Identify recurring themes using keyword extraction and topic modeling.
- Group related issues to guide each bank in improving their mobile apps.

---

## 🛠️ Tools & Libraries Used

- `transformers` (Hugging Face) – for DistilBERT sentiment scoring  
- `nltk`, `spaCy` – for preprocessing (tokenization, stopword removal, lemmatization)
- `pandas`, `numpy` – data handling
- `sklearn` – TF-IDF vectorization and (optional) topic modeling
- `matplotlib`, `seaborn`, `wordcloud` – visualization

---

## 🔄 Workflow Overview

### 🔹 1. Sentiment Analysis

- Used **`distilbert-base-uncased-finetuned-sst-2-english`** from Hugging Face to classify each review as:
  - `positive`
  - `negative`
  - `neutral` (based on probability thresholds)

- Optional comparison with **TextBlob** and/or **VADER** for validation.

- **Aggregated sentiment by:**
  - Bank
  - Star rating
  - Date (for trend tracking)

### Output Format:
| review | bank | rating | sentiment_label | sentiment_score |
|--------|------|--------|-----------------|-----------------|

---

### 🔹 2. Thematic Analysis

#### Keyword & Phrase Extraction
- Used `spaCy` + `TF-IDF` to extract most informative keywords and n-grams (e.g., “login failed”, “slow loading”, “easy interface”).

#### Grouping & Manual Clustering
- Manually grouped related phrases and keywords into **3–5 overarching themes per bank**, such as:
  - **Account Access & Login Issues**
  - **Transaction Reliability & Performance**
  - **App Design & User Interface**
  - **Customer Support**
  - **Feature Requests & Suggestions**

#### Theme Assignment
- Used keyword matching and regular expressions to assign reviews to one or more themes.
- Some reviews may match multiple categories if relevant.

### Output Format:
| review | theme(s) | keywords | sentiment_label | bank |

---
