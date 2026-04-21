#link for dataset: 
https://www.kaggle.com/datasets/chaitu20/ipl-dataset2008-2025

# IPL Big Data Analytics & Match Prediction System

A complete Big Data mini-project using IPL cricket data (2008–2024).

## Folder Structure
```
ipl-big-data-project/
├── data/
│   └── ipl.csv              ← Place your CSV here
├── notebooks/
│   ├── 01_data_ingestion.ipynb
│   ├── 02_eda_and_visualization.ipynb
│   ├── 03_mongodb_storage.ipynb
│   ├── 04_prediction_models.ipynb
│   └── 05_summary_report.ipynb
├── requirements.txt
└── README.md
```

## Setup

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Place ipl.csv in the data/ folder

# 3. Start MongoDB (optional — only for Notebook 03)
docker run -d -p 27017:27017 --name mongodb mongo

# 4. Launch Jupyter
jupyter notebook
```

## Run Order
Execute notebooks in order: 01 → 02 → 03 → 04 → 05

## Notebooks

| # | Notebook | Unit | What it does |
|---|----------|------|--------------|
| 01 | Data Ingestion | Unit I | Load CSV, handle nulls, save ipl_clean.csv |
| 02 | EDA & Graphs | Unit V | Win %, toss impact, top scorers, venues, trends |
| 03 | MongoDB Storage | Unit III | Store in MongoDB, aggregation pipeline |
| 04 | Prediction Models | Unit V | Random Forest + Linear Regression |
| 05 | Summary Report | Unit VI | Predicted vs actual, Spark comparison |

## Tech Stack
- **Python** — Pandas, NumPy
- **Visualization** — Matplotlib, Seaborn
- **ML** — Scikit-learn (Random Forest, Linear Regression)
- **NoSQL** — MongoDB + pymongo
- **Big Data** — Apache Spark (discussed in NB 05)

## Notes on column names
The code auto-detects whether your CSV uses:
- `batter` vs `batsman`
- `batter_runs` vs `batsman_runs`
- `is_wicket` vs `player_dismissed`

If anything breaks, run `df.columns.tolist()` in NB 01 to check exact names.
