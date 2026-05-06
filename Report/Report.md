# 🏆 Data-Driven Business Intelligence for Vietnamese Fashion E-Commerce
### EDA & Revenue Forecasting — VinTelligent Datathon 2026 · Round 1

> **Team Blox Fruit Farmers** · [GitHub Repository](https://github.com/Faewon/Datathon2026-Blox-Fruit-Framers)

| Member | University |
|---|---|
| Hoang Gia Khai *(Team Leader)* | Western Sydney University |
| Le Nguyen Thu Ha | University of Information Technology |
| Nguyen Ngoc Thuy Duong | Monash University |
| Tran Ngoc Thien Kim | Nanyang Technological University |

---

## 📋 Project Overview

This project analyses a **ten-year simulation** of a Vietnamese fashion e-commerce business (July 2012 – December 2022) spanning 14 relational CSV files covering transactions, inventory, web traffic, geography, and customer behaviour.

The work is split into two parts:

- **Part 2 — EDA:** Five business-critical insights extracted via exploratory data analysis, spanning the full analytics hierarchy (Descriptive → Diagnostic → Predictive → Prescriptive).
- **Part 3 — Forecasting:** Daily revenue prediction for January 2023 – July 2024 using a Gradient Boosting Regressor with advanced feature engineering.

**Competition:** [Kaggle — Datathon 2026 Round 1](https://www.kaggle.com/competitions/datathon-2026-round-1)

---

## 📊 Part 2 — EDA Insights Summary

### Insight 1 · Promotion Profitability: Fixed-Amount Discounts Destroy Value
Fixed-amount promotions generate an average net loss of **-11,229 VND** per product line because the post-discount price (~4,000 VND) falls *below* COGS (~6,500 VND). Non-promoted lines are profitable at +5,007 VND.

**→ Recommendation:** Discontinue fixed-amount promotions where post-discount price < COGS. Replace with a capped percentage-off scheme (max 15%) or set a price floor at COGS + target margin.

---

### Insight 2 · Marketing–Supply Chain Disconnect
Stockout SKU counts and page views move in near lockstep in 2022 (r = 0.83), peaking together in April–May. Overstock SKUs are uncorrelated with traffic (r = 0.08).

**→ Recommendation:** Integrate web-traffic forecasts as a leading indicator into the inventory reorder model. Implement a shared marketing-supply calendar with 4-week advance replenishment triggers.

---

### Insight 3 · Post-Order Revenue Loss: COD Cancellations & Returns
COD orders cancel at **16.0%** — nearly double the 8.1% benchmark for other payment methods. Across 39,939 returns: Wrong Size (35%), Defective (20.1%), Not As Described (17.6%). GenZ products have the highest return rate (3.52%).

**→ Recommendation:** Add a small COD handling fee to reduce impulsive orders. Publish detailed size charts and a size-recommender tool, targeting a 5 pp reduction in wrong-size returns.

---

### Insight 4 · Geographic Revenue Concentration
Total revenue is 16.4B VND across 42 cities in 3 regions (East 46.5%, Central 30.1%, West 23.4%). Reaching 80% of revenue requires only **28/42 cities (67%)**, indicating a flat distribution with no extreme concentration.

**→ Recommendation:** Concentrate logistics investment on the top-28 cities. Pilot campaigns in 2 high-potential West-region cities to assess the largest addressable whitespace.

---

### Insight 5 · Customer Segmentation via RFM Model
RFM scoring partitions 90,246 customers into: **At Risk 40.0%** (n=36,097), Loyalists 26.3% (n=23,735), Others 23.6% (n=21,298), Champions 10.1% (n=9,116). Champions spend 600K VND on average — 10.5× the At-Risk spend of 57K VND.

**→ Recommendation:** Protect Champions with a VIP loyalty programme. Re-engage At-Risk customers with time-limited personalised offers — recovering just 10% of at-risk customers at Loyalist spend level adds ~700M VND in incremental revenue.

---

## 🤖 Part 3 — Sales Forecasting

### Model & Results

| Metric | Validation Score (2021–2022) |
|---|---|
| **MAE** | 502,341 VND |
| **RMSE** | 687,419 VND |
| **R²** | 0.826 |

**Algorithm:** Gradient Boosting Regressor (GBR)
- 500 estimators · learning_rate = 0.03 · fixed random seed for reproducibility

---

### Feature Engineering (60+ features)

| Group | Features |
|---|---|
| **Calendar & Cyclical** | Day, month, quarter, week-of-year; sine/cosine encodings |
| **Vietnamese Business Events** | `is_tet`, `is_bts`, `is_double_day` (11/11, 12/12), promotional periods |
| **Lag & Rolling/EMA** | Short-term lags (1–28d), long-term lags (1–3 years), SMA & EMA windows |
| **Seasonality Profiles** | `seasonal_rev` (monthly coefficients), `dow_monthly_factor` |

**Top predictors by importance:**
1. `rev_lag_1d`, `rev_lag_7d`, `rev_ema7` — Revenue momentum (r = 0.87, 0.74, 0.62)
2. `seasonal_rev`, `dow_monthly_factor` — Seasonality & day-of-week habits
3. `is_tet`, `is_double_day` — Event-driven revenue spikes

---

### Cross-Validation & Leakage Control

- **Time-Series Split** (not random K-Fold) to respect temporal ordering
- Train: 2015–2020 · Validate: 2021–2022
- All rolling/EMA features use `.shift(1)` — no look-ahead leakage
- Test-set unavailable lags imputed via `base_rev` × seasonal factor

---

## 🗂️ Repository Structure

```
Datathon2026-Blox-Fruit-Framers/
│
├── Part 1_MCQ/
│   ├── README_Part1_MCQ.md
│   └── vintelligent_datathon_2026_MCQ.ipynb
│
├── Part 2_EDA/
│   ├── Visualizations/
│   │   ├── insight1.png
│   │   ├── insight2.png
│   │   ├── insight3.png
│   │   ├── insight4.png
│   │   └── insight5.png
│   ├── README_Part2_EDA.md
│   └── vintelligent-datathon-2026-Part_2.ipynb
│
├── Part 3_Sales Forcasting/
│   ├── README_Part3_Forecasting.md
│   └── vintelligent-datathon-2026-Part_3.ipynb
│   └── submission.csv                 # Prediction Model result
│
├── .gitignore
├── Dataset.rar                        # Dataset used
├── README.md                          # Summary
└── requirements.txt                   # Library needed
```

---

## ▶️ How to Run

### On Kaggle (Recommended)
1. Upload `vintelligent-datathon-2026-Part_3.ipynb` to Kaggle.
2. Attach the `datathon-2026-round-1` dataset.
3. Click **Run All**.

### Locally (Jupyter / VS Code)
1. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib scikit-learn
   ```
2. Update `DATA_DIR` in **Section 1** of the notebook:
   ```python
   DATA_DIR = '/your/local/path/'
   ```
3. Ensure the directory contains `sales.csv` and `sample_submission.csv`.
4. Run cells sequentially from top to bottom.

---

## 📑 Notebook Sections

| Section | Description |
|---|---|
| 1. Import & Config | Libraries, `DATA_DIR`, random seed |
| 2. Load Data | Read `sales.csv` and `sample_submission.csv` |
| 3. EDA | Revenue trends by day/year/month; lag correlation analysis |
| 4. Feature Engineering | Build 60+ features: calendar, lag, rolling, EMA, seasonal profile |
| 5. Define Features | Declare `FEATURES` list and `TARGET` variable |
| 6. Validation | Time-series split — Train 2015–2020 / Validate 2021–2022 |
| 7. Training & Evaluation | Train GBR for Revenue & COGS; print MAE / RMSE / R² |
| 8. Final Training | Retrain on full dataset (2015–2022) |
| 9. Prediction | Forecast test set; export `submission.csv` |

---

## 📤 Outputs

| File | Description |
|---|---|
| `revenue_overview.png` | EDA revenue overview chart |
| `validation_plot.png` | Actual vs Predicted — 2021–2022 validation window |
| `submission.csv` | Final competition submission file |

---

## 📚 Reference

[1] VinTelligence & VinUni DS&AI Club, *Datathon 2026 — Round 1 Problem Statement*, VinUniversity, 2026.
