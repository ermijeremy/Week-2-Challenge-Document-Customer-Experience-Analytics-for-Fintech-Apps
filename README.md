# 📥 Task 1 – Data Collection and Preprocessing

This task involves collecting user reviews for three major Ethiopian banking apps from the Google Play Store, cleaning the data, and preparing it for sentiment and thematic analysis. All work is version-controlled via Git and GitHub.

---

## 🎯 Objectives

- Scrape a minimum of **400 reviews per bank** using `google-play-scraper`.
- Normalize, clean, and prepare the dataset for downstream NLP tasks.
- Set up a Git-based workflow for managing all scraping and preprocessing scripts.

---

## 🛠️ Tools & Technologies

- `google-play-scraper` – to collect reviews from Google Play Store
- `pandas` – data handling and cleaning
- `datetime` – standardizing date formats
- `Git & GitHub` – version control and task management

---

## 🔄 Workflow Overview

### 🔹 1. Git Setup

- Repository initialized with:
  - `.gitignore` to exclude large files and virtual environments
  - `requirements.txt` for reproducibility
- Used a dedicated branch: `task-1`
- Committed progress in meaningful, logical chunks

### 🔹 2. Web Scraping

Used the `google-play-scraper` library to extract:
- **Review content**
- **Rating** (1–5 stars)
- **Date** of review
- **Bank/app name** for traceability

Apps scraped:
- CBE Birr
- BOA Mobile Banking
- Dashen Bank Wallet

Target: 400+ reviews per bank  
Achieved: 1,200+ total reviews

### Output Columns:
| review | rating | date | bank | source |
|--------|--------|------|------|--------|

---

## 🧼 3. Data Preprocessing

**Cleaning steps included:**
- Removed **duplicate reviews** based on text
- Dropped reviews missing essential fields (e.g., rating or text)
- Normalized dates using `pd.to_datetime` to format: `YYYY-MM-DD`
- Trimmed extra whitespace and lowercased all text
- Added static metadata fields:
  - `bank`: one of "CBE", "BOA", or "Dashen"
  - `source`: always "Google Play"

---

## 🗂️ File Outputs

- `data/` – initial scraped data
- `data/cleaned/` – cleaned and combined dataset:
  - `abyssiniaBank_cleaned.csv`
  - `dashenBank_cleaned.csv`
  - `commercialBank_cleaned.csv`

---

## 📄 Scripts

| File | Description |
|------|-------------|
| `abbisiniaBank_scrapping_script.ipynb`, `commercialBank_scrapping_script.ipynb`, `dashenBank_scrapping_script.ipynb` | Script to collect reviews per app |
| `abbysinia_cleaning_script.ipynb`, `commercial_cleaning_script.ipynb`, `dashen_cleaning_script.ipynb`  | Script to preprocess and clean raw data |
