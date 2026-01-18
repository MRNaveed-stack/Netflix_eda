# 🎬 Netflix Movies & TV Shows  
## Exploratory Data Analysis (EDA) Report

---

## 📌 Introduction

The **Netflix Movies & TV Shows dataset** is a comprehensive collection of content metadata from the Netflix streaming platform. It contains information about thousands of movies and TV shows, including content type, production countries, release year, date added to Netflix, ratings, duration, and genres.

The goal of this project is to perform **Exploratory Data Analysis (EDA)** to understand Netflix’s content strategy, identify trends in content acquisition, and analyze how the platform’s library has evolved over time.

---

## 📂 Dataset Overview

- **Total Records:** ~8,800 titles  
- **Total Columns:** 12  
- **Each row represents:** One unique Netflix title  

### 🔑 Key Columns Used

- **type** – Indicates whether the content is a Movie or TV Show  
- **country** – Production country or countries  
- **release_year** – Original release year of the content  
- **date_added** – Date when the content was added to Netflix  
- **rating** – Content maturity rating (e.g., PG, R, TV-MA)  
- **duration** – Runtime or number of seasons  
- **listed_in** – Genres or categories  

These columns formed the foundation of the entire analysis.

---

## ⚠️ Data Issues & Challenges

Several real-world data quality issues were identified:

- **Missing Values**
  - Some titles were missing country information.
  - Several entries had missing content ratings.

- **Multi-Value Columns**
  - Columns like `country` and `listed_in` contained multiple values separated by commas.
  - These needed to be split and expanded to analyze individual countries and genres accurately.

- **Date Formatting Issues**
  - The `date_added` column contained inconsistent formats and missing values.
  - Proper datetime conversion was required for time-based analysis.

---

## 🧹 Data Cleaning & Preprocessing

To prepare the dataset for analysis, the following steps were performed:

- Filled missing values:
  - `country` → **"Unknown"**
  - `rating` → **"Not Rated"**
- Converted `date_added` to a datetime format with error handling.
- Created a new feature:
  - **year_added** – the year content was added to Netflix.
- **No rows were dropped**, ensuring full dataset integrity.

This approach preserved all available information while making the data analysis-ready.

---

## 🔍 Exploratory Data Analysis (EDA)

The exploratory analysis revealed several important patterns:

### 🎞️ Movies vs TV Shows
- Compared the distribution of Movies and TV Shows to understand Netflix’s content focus.

### 🌍 Country-wise Content Analysis
- Expanded multi-country entries to analyze each country’s contribution.
- Identified Netflix’s major content-producing regions.

### 📈 Content Growth Over Time
- Analyzed year-wise additions to identify growth phases and strategic shifts.

### 🎭 Ratings & Genres
- Examined the most common content ratings on the platform.
- Identified the most frequently occurring genres after expanding multi-genre values.

---

## 🧠 Feature Engineering & Advanced Analysis

To gain deeper insights, additional analysis techniques were applied:

### ⏳ Content Age
- **Content Age = Year Added − Release Year**
- Compared average content age between Movies and TV Shows to identify acquisition patterns.

### 🎨 Genre Diversity Over Time
- Measured the number of unique genres per year.
- Used this as an indicator of content diversity and portfolio expansion.

### 🌐 Country Dependency Analysis
- Calculated country contribution using **percentage share** instead of raw counts.
- Highlighted Netflix’s dependency on a small number of major content-producing countries.

### 🔞 Mature Content Trend
- Defined mature content as titles rated **TV-MA, R, or NC-17**.
- Analyzed trends separately for Movies and TV Shows to detect shifts in content maturity.

---

## 📊 Visualizations Used

To communicate insights effectively, the following visualizations were used:

- **Bar Charts**
  - Movies vs TV Shows
  - Top producing countries
  - Top ratings
  - Top genres

- **Line Charts**
  - Titles added per year
  - Genre diversity over time
  - Mature content trends

Each visualization type was chosen to clearly highlight comparisons and time-based trends.

---

## 📌 Key Insights & Results

- Netflix experienced significant content growth during certain periods, reflecting strategic expansion.
- Content production is geographically concentrated, with strong dominance from a few countries.
- Movies and TV Shows follow different acquisition strategies, particularly in terms of content age.
- Mature-rated content has increased over time, indicating changing audience preferences.
- Netflix maintains a broad range of genres to appeal to diverse audience segments.

---

## ✅ Conclusion

This Exploratory Data Analysis provides a clear and data-driven understanding of Netflix’s content strategy. By analyzing content types, geographic distribution, ratings, genres, and time trends, the project highlights how Netflix balances growth, diversity, and audience targeting.

The results show that Netflix operates as a global platform with strategic concentration in key regions, a strong focus on genre diversity, and a carefully managed maturity profile. This analysis demonstrates how data-driven insights can be used to evaluate real-world business strategies in the entertainment industry.

---

## 📁 Project Files

- **Netflix_EDA.ipynb** – Jupyter Notebook with full analysis  
- **README.md** – Project report  
- **netflix_titles.csv** – Original dataset (optional)  
