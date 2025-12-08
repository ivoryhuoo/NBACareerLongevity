Using Random Forest Regression, Linear Models & Exploratory Data Analysis

This project analyzes the factors that influence NBA career longevity using player and season statistics from Kaggle. Through exploratory data analysis (EDA), feature engineering, and machine learning modeling, the project examines which rookie-year performance metrics best predict how long a player stays in the league.

📌 Project Overview

NBA players enter the league with immense performance variability—making career longevity difficult to predict with simple trends. This project builds an end-to-end pipeline to:

Explore trends in rookie stats and long-term career outcomes

Construct predictive models for career longevity

Identify the most influential performance metrics

Evaluate model performance using appropriate regression metrics

Ensure transparency and reproducibility across the entire process

📂 Dataset

Source: Kaggle — NBA Player & Season Stats Dataset
Contains player-level and season-level metrics including:

PTS, REB, AST, MP, WS, PER, etc.

Player demographics

Career start/end years

Target Variable: Number of seasons played (career longevity)

🔍 Exploratory Data Analysis (EDA)

The EDA phase examined:

Distribution of rookie-year stats

Correlations with career length

Outlier detection and variance analysis

Feature interactions (e.g., MP × WS, PTS × PER)

Visualizations using Matplotlib and Seaborn

Key insights:

Rookie Minutes Played (MP) and Win Shares (WS) showed strong nonlinear relationships with career length

Many performance variables interact, making linear assumptions ineffective

High variance in rookie data suggests the need for robust models

🤖 Modeling Approach
Models Used

Random Forest Regression (primary model)

Multilinear Regression (baseline comparison)

Why Random Forest?

Random Forest was selected due to:

Ability to model nonlinear patterns

Resilience to noise and variance in rookie stats

Strong performance with tabular data

Natural handling of feature interactions

Built-in feature importance ranking for interpretability

Hyperparameter Tuning

Tuned using GridSearchCV:

Hyperparameter	Final Value
n_estimators	200
max_depth	10
min_samples_leaf	4
Train/Test Strategy

80/20 split

Fixed random seed for reproducibility

All preprocessing steps stored in a reusable pipeline script

Reproducibility & Transparency

The entire workflow is:

✔ Scripted end-to-end (no manual steps)
✔ Deterministic with fixed random seeds
✔ Logged and documented for clarity
✔ Modularized so each step (EDA → preprocessing → modeling) is reproducible
✔ Version-controlled with Git

📊 Evaluation & Metrics

Metrics used:

R² Score — variance explained

MAE — average prediction error

Interpretation approach:

Compared model accuracy against baseline linear regression

Examined residuals to ensure stability

Evaluated feature importance rankings to understand key drivers of longevity

Results Summary

Random Forest outperformed multilinear regression on both R² and MAE, confirming:

Nonlinear interactions are essential

Rookie performance metrics differ in importance

Model generalization improved after tuning

⭐ Key Findings

Minutes Played (MP), Win Shares (WS), and PTS were top predictors of longevity

Rookie-year efficiency metrics contribute more than raw scoring

Nonlinear models capture complex player progression patterns significantly better

Predictive modeling can uncover overlooked drivers of sustainable NBA careers

🧱 Tech Stack

Python

Pandas, NumPy

Scikit-Learn

Matplotlib, Seaborn

Jupyter Notebook

Git/GitHub

🚀 How to Run the Project
git clone <repo-url>
cd nba-career-longevity
pip install -r requirements.txt
jupyter notebook


Run the notebooks in order:

01_eda.ipynb

02_preprocessing.ipynb

03_modeling.ipynb

04_evaluation.ipynb

📎 Future Improvements

Add XGBoost and LightGBM models

Introduce SHAP values for deeper interpretability

Expand features with advanced player tracking data

Deploy the model as an interactive web app
