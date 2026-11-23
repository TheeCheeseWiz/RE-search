# 📊 RE:search — Reddit Educational Trend Analyzer

An end-to-end data engineering and analytics application built to scrape, classify, and visualize student and educator discussions across Philippine educational subreddits (`r/StudentsPH`, `r/DepEdTeachersPH`, `r/PanganaySupportGroup`, etc.).

> **Note:** This repository serves as an architectural and visual case study showcasing the system workflow, NLP topic modeling, and analytics dashboard.

---

## 🎯 Problem Statement
Manual tracking of student pain points, curriculum feedback, and educational trends across online communities is slow and unstructured. **RE:search** automates data ingestion from Reddit, applies unsupervised machine learning (Latent Dirichlet Allocation) to uncover latent discussion themes, and surfaces actionable insights through an interactive **Streamlit** dashboard.

---

## ⚙️ End-to-End Data Pipeline

1. **Configurable Data Ingestion (Extract):**
   - Sidebar controls allow filtering by target subreddits, post limits, time windows (`year`), and custom search keywords (`"senior high"`, `"college"`, `"module"`, `"deped"`, etc.).
   - Fetches post metadata including timestamp, title, body text, upvote score, comment count, and permalink.
2. **Database Persistence (Load):**
   - Cleaned and structured records are automatically stored in a relational database with deduplication (`Saved 100 new posts to the database!`) for historical tracking.
3. **NLP Topic Modeling & Classification (Transform):**
   - Applies **Latent Dirichlet Allocation (LDA)** to extract top discussion topics and tag each post with its dominant theme (e.g., *Student Life*, *Academic Performance*, *Teaching & Curriculum*, *Student Support*).
   - Automatically classifies posts by **Education Level** (`College`, `Senior High`, `Elementary`, `Junior High`, etc.) for targeted filtering.
4. **Interactive Analytics & Reporting (Visualize):**
   - Generates time-series trend charts (**Post Activity Over Time**), keyword frequency breakdowns (**Top Keywords**), and **Posts by Education Level** distributions.
   - Supports direct export of processed datasets to CSV (`Download CSV`).

---

## 🛠️ Tech Stack
- **Language:** Python
- **Frontend & Visualization:** Streamlit, Matplotlib / Seaborn
- **Data Processing & NLP:** Pandas, Scikit-Learn / Gensim (Latent Dirichlet Allocation)
- **Data Collection & Storage:** Reddit API (`PRAW`), Relational SQL Database

---

## 📸 System Walkthrough

### 1. Scraper Controls & Live Data Ingestion
Configurable sidebar parameters for subreddit targeting, post limits, and keyword filtering, paired with real-time scraping progress.
<img width="1280" height="692" alt="assets-01-scraper-overview" src="https://github.com/user-attachments/assets/d2211311-4079-42cf-9517-471775866052" />

### 2. Raw Post Extraction & Database Persistence
Automated extraction of structured post metadata (timestamps, titles, body text, scores, comment counts, and URLs) with database storage confirmation.
<img width="1280" height="643" alt="assets-02-raw-post-Extraction" src="https://github.com/user-attachments/assets/00d6ba0d-f390-4d27-a60a-02c4c6a56b9d" />

### 3. LDA Topic Modeling & Post Classification
Unsupervised topic extraction identifying 5 core discussion themes across scraped threads and assigning a dominant topic label to every post.
<img width="1280" height="669" alt="assets-03-lda-topic-modeling" src="https://github.com/user-attachments/assets/c201852d-222f-4d5e-b818-785d307cab64" />

### 4. Education-Level Segmentation
Automated filtering separating general educational discussions from specific academic tiers (e.g., Senior High School trends).
<img width="1280" height="669" alt="assets-04-education-level-filtering" src="https://github.com/user-attachments/assets/b989ddc3-6dd1-40bc-af13-3c3af1edab08" />

### 5. Interactive Trend & Keyword Visualizations
Time-series activity tracking alongside top keyword rankings (`grade`, `school`, `college`, `student`, `exam`, `teacher`) to highlight recurring community concerns.
<img width="1280" height="692" alt="assets-05-Interactive-trend-Analytics" src="https://github.com/user-attachments/assets/1e9184af-6d79-4021-b754-393a5a78ef0f" />
