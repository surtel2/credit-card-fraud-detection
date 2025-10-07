# Credit Card Fraud Detection - Random Forest & XGradient boosting

**Goal**: To find and build best fraud detection model with highest score Private Score on the Kaggle competetion leaderboard.
**Data**: Open data set from competition with a highly imbalanced target class.
**Results**: Random Forest (0.701 Private Score Leaderboard, 27/71 Rank on LeaderBoard) and XGB (0.708 Private Score Leaderboard, 24/71 Rank on LeaderBoard)
**Date**: 2025-09-28

## How to run
1. **Set up environment** for your project.
2. **Download data**: from [Kaggle Competition](https://www.kaggle.com/competitions/credit-card-fraud-prediction/data) and place it in './data/' folder of your project/environment.
3. **Open notebooks** and run sequentially:
    01_data_exploring.ipynb
    02_random_forest_undersample.ipynb
    03_xgb_full.ipynb

## Data & licence
Dataset: [Kaggle Credit Card Prediction](https://www.kaggle.com/competitions/credit-card-fraud-prediction/overview) by Prayash Dash and VectorNd (2024).
Licence: Use governed by Kaggle competition rules (non-commercial / educational).
This repo is for **educational and portfolio purposes only**.

## Reproducibility
Notebooks has been already setuped to getting the same results with fixed SEED (random_state) parameter and fixed stratified split and undersampling.

## Method
1. Data validation: verivied no nulls, all features on comparable scales
2. Models:
    1. Random Forest (RF) — undersample 50%/50%
    2. XGBoost (XGB) — full data set
    Both models used all the features.
3. Preprocessing:
    Undersampling was made in raw code.
    Scaling and modeling combined in a pipeline.
4. Reproductibility:
    Fixed SEED=42 across samplers, splitters, and models.
    Stratified train/test split.

## Results
1. Random Forest
    ROC AUC: 0.745..
    PR AUC: 0.751.. (50%/50% balanced dataset)
    Kaggle Competition:
        Private score: 0.701..
        Position in LeaderBoard: 27/71
        Date: 2025-Sept-28
2. XG Boosting
    ROC AUC: 0.816..
    PR AUC: 0.031.. (full dataset with 0.00179 share of the target class, thus 0.031 / 0.00179 ≈ 17.3)
    Kaggle Competition:
        Private score: 0.708..
        Position in LeaderBoard: 24/71
        Date: 2025-Sept-28

## Repo map
change names

├─ data/                  # train.csv, test.csv, sample_submission.csv (not committed)
├─ notebooks/
│  ├─ 01_data_exploring.ipynb             # Exploring, checking: null values, target class balance, feature scale.
│  ├─ 02_random_forest_undersample.ipynb  # 50/50 undersample → RF → PR-curve threshold → submission
│  └─ 03_xgb_full.ipynb                   # full data (no undersample) → XGB (aucpr, scale_pos_weight) → submission
└─ README.md  ← you are here

## Model card-lite??

## Next steps

1. Make public demo with api, full MLops cycle.
    Using:
        Docker
        FastAPI
        Kafka
        


