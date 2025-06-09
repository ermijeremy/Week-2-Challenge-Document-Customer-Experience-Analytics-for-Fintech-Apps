# 📱 Fintech App Review Analysis – Week 2

This project is part of the **10 Academy AI Mastery Week 2 Challenge**, where the goal is to analyze Google Play Store reviews for three major Ethiopian banking apps — **CBE**, **BOA**, and **Dashen Bank** — to extract insights that can improve customer experience.

---

## 🎯 Project Objective

- Scrape user reviews from the Play Store
- Clean and preprocess the review text
- Perform sentiment analysis and thematic grouping
- Store the processed data in a structured Oracle database
- Visualize insights and provide recommendations to each bank

---

## 🛠️ Tools & Libraries

- `google-play-scraper` – for scraping app reviews
- `pandas`, `numpy` – data processing
- `matplotlib`, `seaborn`, `wordcloud` – data visualization
- `TextBlob`, `NLTK`, `VADER`, `TextBlob`, `TF-IDF`, `SpaCy` – sentiment & theme extraction
- `cx_Oracle` – connecting to Oracle XE database

---
## 🧪 Methodology

### 🔹 Data Scraping

We used the `google-play-scraper` Python library to extract user reviews for three Ethiopian banking apps: **CBE**, **BOA**, and **Dashen Bank**. For each app, over 400 reviews were collected to ensure diversity and volume.

Key fields extracted:
- `review`: User-written review content
- `rating`: Integer rating (1 to 5)
- `date`: Date the review was posted
- `source`: Set to "Google Play"
- `bank`: One of "CBE", "BOA", or "Dashen"

The scraping was done in batches and saved as raw `.csv` files per app in the `data/raw_reviews/` folder.

---

### 🔹 Data Cleaning & Preprocessing

After scraping, each dataset underwent preprocessing to ensure quality and consistency.

Steps included:
- **Removing Duplicates**: Eliminated repeated reviews based on text content.
- **Standardizing Text**: Converted reviews to lowercase, removed URLs, non-ASCII characters, and excess whitespace.
- **Filtering Noise**: Removed reviews with fewer than 3 words or missing key fields (e.g., no rating or date).
- **Parsing Dates**: Standardized review dates using `pandas.to_datetime()`.
- **Labeling**: Appended `bank` and `source` columns to each row to ensure traceability.

The cleaned data was saved in `data/cleaned/` and combined into a single master file:  
`all_clean_reviews.csv`

This cleaned dataset is the basis for sentiment analysis, thematic grouping, and database storage.
---

## 📂 Folder Structure

project/  
├── data/  
│ ├── raw_reviews/  
│ ├── cleaned/  
│ └── sentiment/  
├── notebooks/  
│ ├── task1_scraping_eda.ipynb  
│ ├── task2_sentiment_theme.ipynb  
│ ├── task3_oracle_storage.ipynb  
│ └── task4_insights_report.ipynb  
├── scripts/  
│ ├── scrape_reviews.py  
│ ├── clean_reviews.py  
│ ├── sentiment_analysis.py  
│ └── upload_to_oracle.py  
├── reports/  
│ └── final_report.pdf  
├── requirements.txt  
└── README.md  