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
Configurable sidebar parameters for subreddit targeting, post limits, and keyword filtering, paired with real-time database storage confirmation and raw post preview.
![Scraper Overview](assets/01-scraper-overview.png)

### 2. LDA Topic Modeling & Post Classification
Unsupervised topic extraction identifying 5 core discussion themes across scraped threads and assigning a dominant topic label to every post.
![LDA Topic Modeling](assets/03-lda-topic-modeling.png)

### 3. Education-Level Segmentation
Automated filtering separating general educational discussions from specific academic tiers (e.g., Senior High School trends).
![Education Level Filtering](assets/04-education-level-filtering.png)

### 4. Trend & Keyword Visualizations
Time-series activity tracking alongside top keyword rankings (`grade`, `school`, `college`, `student`, `exam`, `teacher`) to highlight recurring community concerns.
![Trend Visualizations](assets/05-trend-visualizations.png)
