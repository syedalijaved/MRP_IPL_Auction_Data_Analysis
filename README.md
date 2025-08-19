# MRP_IPL_Auction_Data_Analysis

Predicting IPL Auction Prices with Machine Learning

Data‑driven modeling of Indian Premier League (IPL) player auction prices using engineered season‑level performance features and supervised regression (Linear Regression, Random Forest, XGBoost). The project also explores feature selection via correlation analysis and outlines paths for future improvement. 

🎯 Project Goals

Predict a player’s final auction price from prior-season performance, role, and origin. 

Understand which features matter most via correlation/importance analysis. 

Provide a reproducible pipeline for data prep, modeling, and evaluation. 

🏏 Context

The IPL auction shapes team composition and value creation; historically, decisions have leaned on subjective assessments. With richer historical data, ML can bring objectivity to pricing and retention strategies. 

📦 Data

Ball‑by‑Ball Match Dataset (Kaggle): ~180k deliveries with batter, bowler, runs, wickets, over/ball, etc. Enables derivation of batting/bowling KPIs. 

Player Auction Dataset (Kaggle): ~900–970 records of auction outcomes with player role, style, team, year, origin, and INR amount. 

Years covered: 2013–2022 (auction data).
Example stats: mean auction amount ≈ ₹21,054,510; max ₹162,500,000; 543 unique players. 

🧪 Features (engineered per season)

Batting: matches, innings, runs, balls faced, not-outs, average, strike rate, 4s/6s, phase splits (PP/Middle/Death).
Bowling: overs, runs conceded, wickets, economy, strike rate, average, phase metrics (PP/Death).
Low‑participation players (e.g., <4 innings) filtered to reduce noise. 

Label alignment: features from seasons Y‑1 / Y‑2 predict auction price in Y. 

🧰 Methods

Models: Linear Regression, Decision Tree Regression, Random Forest Regression, XGBoost Regression. 

Split: 70% train / 30% test. 

Metrics: R², MAE, RMSE. 

🔍 Experiments & Results

Experiment 1: trained on all features → modest performance.

Linear Regression R² ≈ 0.356

Random Forest R² ≈ 0.206

XGBoost R² ≈ 0.156 

Experiment 2: feature selection via correlation (e.g., Batting_Average r≈0.844; Average_StrikeRate r≈0.844; Four r≈0.698, etc.) improved results.

Linear Regression R² ≈ 0.736

Random Forest R² ≈ 0.655

XGBoost R² ≈ 0.654
