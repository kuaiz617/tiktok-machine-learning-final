 
# TikTok (Douyin) User Behavior Analysis Based on Data Mining

## Overview
This project presents a large-scale data-driven analysis of user browsing behavior on Douyin (TikTok China) using data mining and machine learning techniques.  
By examining user-, creator-, and content-level features, the study aims to uncover structural patterns in user engagement, content popularity, and platform dynamics, with implications for recommendation systems, content strategy, and advertising targeting.

This repository supports a research-oriented thesis project and focuses on analytical insight and interpretation rather than production deployment.

---

## Dataset
- Source: Public dataset from HeyWhale
- Platform: Douyin (TikTok China)
- Time period: 2019
- Full dataset size: 1,737,312 user interaction records

Due to GitHub file size limitations, this repository includes a randomly sampled subset
(10,000 rows) of the original dataset for demonstration and reproducibility purposes.
All analyses in the thesis were conducted on the full dataset.


### Key Fields
- User: `uid`, `user_city`
- Content: `item_id`, `item_city`, `duration_time`
- Creator: `author_id`
- Interaction: `like`, `finish`
- Time: `real_time`, `date`


---

## Key Findings & Results

### 1. Strong Long-Tail User Behavior
User activity exhibits a pronounced long-tail distribution:
- A small fraction of highly active users accounts for a large proportion of total views and likes.
- The majority of users interact with only a limited number of videos, indicating asymmetric engagement patterns typical of attention-driven platforms.

This suggests that user experience on Douyin is shaped disproportionately by a minority of highly engaged users.

---

### 2. Extreme Concentration Among Creators
Creator-level analysis reveals significant inequality in content impact:
- A very small number of creators account for the majority of views and likes.
- Over 50% of creators receive minimal exposure, while top creators dominate platform attention.

This concentration highlights structural visibility imbalance and has implications for creator recommendation, platform fairness, and monetization strategies.

---

### 3. Interpretable User and Creator Segmentation
K-Means clustering (validated via Silhouette Score and SSE) was applied to both users and creators:
- Users were segmented by engagement intensity, viewing breadth, and completion behavior.
- Creators were grouped by content output, audience reach, and engagement effectiveness.

These clusters provide interpretable behavioral archetypes rather than opaque model outputs, supporting exploratory analysis and strategic segmentation.

---

### 4. Behavioral Associations Across Features
Association rule mining (Apriori) uncovered consistent relationships between:
- High viewing activity and higher likelihood of likes and completions
- Creator output frequency and cumulative engagement metrics

These associations reflect systematic behavioral regularities rather than random interactions.

---

### 5. Like Prediction: Limited but Informative Performance
Binary classification models were used to predict whether a user would like a video:
- Random Forest outperformed Logistic Regression, Naive Bayes, and Decision Tree models.
- ROC-AUC improved through hyperparameter tuning, though overall predictive performance remained moderate.

This indicates that while behavioral features contain signal, user “like” behavior is influenced by complex and potentially unobserved factors (e.g., content semantics, social context).

---

## Methods Summary
- Feature construction at user, creator, and content levels
- Exploratory Data Analysis (EDA)
- K-Means clustering with model selection
- Association rule mining (Apriori)
- Binary classification with ROC-AUC evaluation

---

## Data Preprocessing
- Removed irrelevant fields (e.g. `Unnamed: 0`)
- Checked and confirmed no missing or duplicate records
- Converted time fields into numerical representations
- Constructed feature tables for:
  - Users
  - Creators
  - Content (videos)

All feature tables were exported as CSV files for further analysis.

## Exploratory Data Analysis (EDA)
EDA was conducted at three levels:

### User-Level Analysis
- Distribution of views, likes, and completed views
- User activity concentration and long-tail effects
- Average watch duration and city diversity

### Creator-Level Analysis
- View and like concentration among creators
- Identification of high-impact creators
- Geographic diversity of content production

### Content-Level Analysis
- Daily content publishing trends
- View and like distribution across videos
- Detection of temporal spikes indicating trending events

Visualizations were created using line charts, pie charts, and funnel charts.

## Data Mining and Modeling

### Clustering (K-Means)
- Applied K-Means clustering to both users and creators
- Evaluated clustering performance using:
  - Silhouette Score
  - Sum of Squared Errors (SSE)
- Clustering results were used to segment:
  - Users by engagement level
  - Creators by content impact and activity

### Association Rule Mining (Apriori)
- Applied Apriori algorithm to user, creator, and content feature sets
- Extracted frequent itemsets and association rules
- Evaluated rules using support and confidence metrics
- Used to explore relationships between behavioral features

### Like Prediction (Binary Classification)
- Goal: predict whether a user will like a video
- Models evaluated:
  - Logistic Regression
  - Naive Bayes
  - Decision Tree
  - Random Forest
- Evaluation metric: ROC-AUC
- Hyperparameter tuning performed using GridSearchCV
- Random Forest achieved the best overall performance among tested models


## Tools & Technologies
- Python
- pandas, numpy
- scikit-learn
- mlxtend

- matplotlib, pyecharts

---

## Applications
- User interest modeling and behavioral segmentation
- Content performance evaluation
- Creator stratification for platform strategy
- Data-informed advertising and recommendation research

---

- pyecharts
- matplotlib

## Applications
- User interest modeling and personalized recommendation
- Content performance evaluation
- Creator segmentation for platform strategy
- Advertising targeting and business decision support

## Outputs
- User, creator, and content feature tables (CSV)
- Trained clustering models
- Association rule results
- Classification models and evaluation plots

## Notes
This project focuses on demonstrating data mining and modeling techniques rather than building a production-level recommendation system.  
All analyses are conducted on historical data for research and educational purposes.

