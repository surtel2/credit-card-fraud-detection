# Credit Card Fraud Detection - Random Forest & XGradient boosting

Goal: To find and build best fraud detection model with highest score Private Score on the Kaggle competetion leaderboard.
Data: Open data set from competition with a highly imbalanced target class.
Key Results: Random Forest (0.701 Private Score Leaderboard, 27/71 Rank on LeaderBoard) and XGB (0.708 Private Score Leaderboard, 24/71 Rank on LeaderBoard)
Date???

## How to run
??

## Data & licence
Open data set from competition 
@misc{credit-card-fraud-prediction,
    author = {Prayash Dash and VectorNd},
    title = {Credit Card Fraud Detection},
    year = {2024},
    howpublished = {\url{https://kaggle.com/competitions/credit-card-fraud-prediction}},
    note = {Kaggle}
}

## Reproducibility
Notebooks has been already setuped to getting the same results with fixed SEED (random_state) parameter and fixed stratified split and undersampling.

## Method
1. Data completeness research: making sure that there is no Null values, all variables are scaled in same magnitude
2. Modeling (2 Branches):
    1. Random Forest (undersample 50%/50%)
    2. XG Boosting (full data set)

Both branches used all the features.
Preprocessing:
    Undersampling was made in raw code.
    Colummn scaling and modeling was made in a pipeline.

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
        


