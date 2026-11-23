# 📊 RE:search — Reddit Educational Trend Analyzer

An end-to-end data engineering and analytics application built to scrape, classify, and visualize student and educator discussions across Philippine educational subreddits (`r/CollegeAdmissionsPH`, `r/studentsph`, `r/Philippines`, and academic subject communities).

> **Note:** This repository serves as an architectural and visual case study showcasing the system workflow, NLP topic modeling, and analytics dashboard.

---

## 🎯 Problem Statement
Manual tracking of student pain points, reviewer requests, and academic trends across online communities is slow and unstructured. **RE:search** automates data ingestion across 30+ subreddits, applies unsupervised machine learning (Latent Dirichlet Allocation) to uncover latent discussion themes, and surfaces actionable insights through an interactive **Streamlit** dashboard.

---

## ⚙️ End-to-End Data Pipeline

1. **Configurable Data Ingestion (Extract):**
   - Sidebar controls allow filtering by custom date ranges (`Start Date` / `End Date`), additional subreddits, post limits per subreddit, and keyword search queries (`"textbook"`, `"reviewer"`, `"law codal"`, `"study guide"`).
   - Tracks real-time progress across target communities (`Processed 28/32 subreddits`).
2. **Data Cleaning & Structuring (Load):**
   - Extracts structured post metadata including timestamp, title, body text, upvote score, comment count, and permalink (`Scraped 151 educational posts`).
3. **NLP Topic Modeling & Classification (Transform):**
   - Applies **Latent Dirichlet Allocation (LDA)** to extract top discussion themes (*Study Tools & Anki*, *Book Requests*, *School Life & Exams*, *Math & Quant Questions*, *Test Prep / Chemistry*) and assigns a `topic_label` to every post.
4. **Interactive Analytics & Reporting (Visualize):**
   - Generates time-series trend charts (**Posts Over Time / Recent Activity Trend**), community activity rankings (**Top Subreddits**), and **Posts by Education Level** distributions.

---

## 🛠️ Tech Stack
- **Language:** Python
- **Frontend & Visualization:** Streamlit, Matplotlib / Seaborn
- **Data Processing & NLP:** Pandas, Scikit-Learn / Gensim (Latent Dirichlet Allocation)
- **Data Collection & Storage:** Reddit API (`PRAW`), Relational SQL Database

---

## 📸 System Walkthrough

### 1. Scraper Controls & Live Data Ingestion
Configurable sidebar parameters for date range, subreddit targeting, and post volume limits, paired with real-time scraping progress across 32 subreddits.
<img width="1280" height="692" alt="assets-01-scraper-overview" src="https://github.com/user-attachments/assets/72f18646-a31c-4cc6-bc14-30ecae38ffec" />

### 2. Raw Post Extraction & Structured Dataset
Automated extraction of post timestamps, titles, body text, engagement scores, comment counts, and URLs with completion summaries.
<img width="1280" height="643" alt="assets-02-raw-post-Extraction" src="https://github.com/user-attachments/assets/809cb072-e1eb-413b-84a0-bab0aebcdc4d" />

### 3. LDA Topic Modeling & Post Classification
Unsupervised topic extraction identifying 5 core academic discussion themes and tagging every post with its dominant `topic_label`.
<img width="1280" height="669" alt="assets-03-lda-topic-modeling" src="https://github.com/user-attachments/assets/c0946291-c596-45ea-b97f-974d5ce50d11" />

### 4. Subject & Education-Level Grouping
Categorizes scraped posts by academic subject and segments education-level discussions with post metadata and links.
<img width="1280" height="692" alt="assets-04-education-level-filtering" src="https://github.com/user-attachments/assets/c774a298-e704-4bb2-abe8-2a1b370ce3b5" />

### 5. Interactive Trend & Community Visualizations
Time-series activity tracking (**Recent Activity Trend**) alongside community volume rankings (**Most Active Subreddits**) to highlight where and when academic discussions peak.
<img width="1280" height="692" alt="assets-05-Interactive-trend-Analytics" src="https://github.com/user-attachments/assets/ad8959b3-5357-4f4e-902f-c8d45fd3f109" />
