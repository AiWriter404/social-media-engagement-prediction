# social-media-engagement-prediction
Predicting social media post engagement (likes) using Python, Pandas, and Linear Regression.
# 📱 Instagram User Engagement Prediction

A complete data science project that explores user lifestyle, demographic, and app-usage data to predict Instagram engagement scores using Python and Linear Regression.

## 📌 Project Overview

This project analyzes a large-scale dataset (1.5M+ users) combining demographic information, lifestyle habits, and Instagram usage behavior to predict a user's engagement score. The project covers data inspection, feature selection, encoding, model training, evaluation, and visualization.

## 📂 Dataset

- **Size:** 1,547,896 rows × 58 columns (original)
- **Description:** Contains user demographics (age, gender, country, income), lifestyle data (sleep, exercise, stress), and Instagram usage metrics (sessions per day, posts created, followers, time on feed/reels/explore), along with a target variable: `user_engagement_score`.

## 🛠️ Tools & Libraries

- **Python**
- **Pandas** — data manipulation
- **NumPy** — numerical operations
- **Matplotlib & Seaborn** — visualization
- **Scikit-learn** — model training and evaluation

## 🧹 Data Preparation Steps

1. Inspected dataset structure, data types, missing values, and duplicates (dataset was found to be clean — 0 missing values, 0 duplicates)
2. Identified and removed irrelevant columns:
   - `user_id` — unique identifier, no predictive value
   - `app_name` — constant column (all values = "Instagram")
   - `last_login_date` — raw date string, not used in this version
3. Applied one-hot encoding to 18 categorical columns (gender, country, employment status, etc.), expanding the dataset from 55 to 99 columns
4. Split data into 80% training and 20% testing sets

## 🤖 Model

- **Algorithm:** Linear Regression
- **Target Variable:** `user_engagement_score`
- **Features:** 98 columns (demographic, lifestyle, and usage-based features)

## 📊 Model Evaluation

| Metric | Value |
|---|---|
| MAE | 0.83 |
| MSE | 1.46 |
| RMSE | 1.21 |
| R² Score | 0.557 |

## 💡 Key Insights

1. **Engagement Score Distribution:** The target variable is heavily right-skewed — most users score between 1.0–2.0, while a small number of users have unusually high scores (up to 18.67). This skewness limits how well a linear model can fit the data.

2. **Sessions vs Engagement (Counter-Intuitive Finding):** Users with fewer daily sessions show higher and more variable engagement scores, while users with many daily sessions show consistently low, flat scores. This suggests that raw usage frequency alone does not strongly predict engagement in this dataset — quality of interaction may matter more than quantity of app opens.

3. **Model Performance:** With an R² of 0.557, the model explains about 56% of the variance in engagement scores — a moderate result. The skewed nature of the target variable suggests that non-linear models (e.g., Random Forest) or a log-transformed target could improve performance in future iterations.

## 📁 Repository Structure

```
social-media-engagement-prediction/
│
├── README.md
├── social_media_engagement_analysis.ipynb
└── requirements.txt
```

## ▶️ How to Run

```bash
git clone https://github.com/your-username/social-media-engagement-prediction.git
cd social-media-engagement-prediction
pip install -r requirements.txt
jupyter notebook social_media_engagement_analysis.ipynb
```

## 📬 Connect

Feel free to connect or reach out if you have feedback or questions about this project.
