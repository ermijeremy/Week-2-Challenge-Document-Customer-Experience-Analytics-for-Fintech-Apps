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