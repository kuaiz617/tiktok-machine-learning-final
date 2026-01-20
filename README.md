# TikTok User Behavior Analysis Based on Data Mining

## Overview
This project analyzes large-scale user browsing behavior data from Douyin (TikTok China) using data mining and machine learning techniques.  
By examining user, creator, and content-level features, the project aims to uncover behavioral patterns, user interests, and content performance, and to explore data-driven approaches for recommendation, content optimization, and advertising targeting.

## Dataset
- Source: Public dataset from HeyWhale
- Time period: 2019
- Size: 1,737,312 user interaction records
- Platform: Douyin (TikTok China)

### Key Fields
- User: `uid`, `user_city`
- Content: `item_id`, `item_city`, `duration_time`
- Creator: `author_id`
- Interaction: `like`, `finish`
- Time: `real_time`, `date`

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
