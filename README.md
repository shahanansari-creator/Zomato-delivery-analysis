# Zomato-delivery-analysis

# 🍔 Zomato Delivery Operations Analysis

Analysis and predictive modeling of 45,000+ Zomato delivery orders — covering delivery performance, route optimization, customer experience, operational patterns, and an ML model to forecast delivery time.

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![pandas](https://img.shields.io/badge/pandas-data%20analysis-150458)
![scikit--learn](https://img.shields.io/badge/scikit--learn-ML-F7931E)
![License](https://img.shields.io/badge/license-MIT-green)

## 📌 Overview

This project explores the Zomato delivery dataset to answer five business questions:

| # | Objective | What it covers |
|---|-----------|-----------------|
| 1 | **Delivery Performance Analysis** | Delivery-person ratings, delivery times, vehicle condition |
| 2 | **Route Optimization** | Trip distance, traffic density, city type |
| 3 | **Customer Experience Enhancement** | Weather conditions, festival-season impact |
| 4 | **Operational Insights** | Order volumes, order types, multiple/bundled deliveries |
| 5 | **Predictive Analytics** | ML models to forecast delivery time |

## 📊 Dataset

- **Rows:** 45,584 orders | **Columns:** 20
- **Date range:** 11 Feb 2022 – 6 Apr 2022
- **Delivery partners:** 1,320 unique riders
- **Fields:** delivery-person age/rating, restaurant & delivery coordinates, order/pickup timestamps, weather, road traffic density, vehicle type/condition, order type, multiple deliveries, festival flag, city type, and `Time_taken (min)` as the target.

> Dataset file: `Zomato_Dataset.csv` (not included in this repo if large/licensed — see [Setup](#-setup--usage)).

## 🔑 Key Findings

- **Ratings vs. speed:** Higher-rated delivery partners deliver faster (r = −0.34).
- **Vehicle condition matters:** Poor-condition vehicles average **30.1 min** vs. **24–26 min** for better-maintained ones.
- **Traffic > distance:** Delivery time rises from **21.3 min (Low traffic)** to **31.2 min (Jam)** — a bigger swing than distance alone explains (r = 0.32 with distance).
- **Semi-Urban lag:** Semi-Urban deliveries average **49.7 min**, nearly double Urban (**23.0 min**).
- **Weather effect:** Sunny days average **21.9 min** vs. **28.9 min** in Fog/Cloudy conditions.
- **Festival spike:** Average delivery time jumps **75%** on festival days (45.5 min vs. 26.0 min).
- **Bundled orders:** Trips with 4 stacked deliveries take **47.8 min** on average vs. **22.9 min** for single-order trips.
- **Peak hours:** Order volume peaks between **5 PM–10 PM**.

## 🤖 Predictive Model

Three regression models were trained to forecast `Time_taken (min)` from distance, traffic density, weather, rider profile, vehicle condition, multiple-deliveries count, order hour, prep time, festival flag, and city type (41,213 rows, 80/20 split):

| Model | MAE (min) | RMSE (min) | R² |
|---|---|---|---|
| Linear Regression | 4.75 | 5.98 | 0.585 |
| Gradient Boosting | 3.49 | 4.36 | 0.780 |
| **Random Forest** ⭐ | **3.01** | **3.75** | **0.837** |

The Random Forest model explains ~84% of the variance in delivery time with an average error of ~3 minutes, making it viable for real-time ETA estimation.

## 🛠️ Tech Stack

- **Language:** Python 3
- **Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`
- **Environment:** Google Colab / Jupyter Notebook

## 📁 Repository Structure

```
.
├── Zomato_Dataset.csv                  # Raw dataset
├── Zomato_Delivery_Analysis.ipynb      # Full analysis + ML notebook
├── Zomato_Project_Report.docx          # Written project report
└── README.md                           # This file
```

## 🚀 Setup & Usage

1. Clone the repo:
   ```bash
   git clone https://github.com/shahanansari-creator/zomato-delivery-analysis.git
   cd zomato-delivery-analysis
   ```
2. Open `Zomato_Delivery_Analysis.ipynb` in [Google Colab](https://colab.research.google.com/) or Jupyter.
3. Run all cells — upload `Zomato_Dataset.csv` when prompted (Colab) or place it in the repo root (local Jupyter).
4. Install dependencies locally if needed:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```

## 📄 Report

See [`Zomato_Project_Report.docx`](./Zomato_Project_Report.docx) for the full written report, including methodology, findings, and recommendations.

## 👤 Author

**Mohd Shahan Ansari**
Data Analyst | BBA (Supply Chain & Finance), MBA (Marketing & IT), PG Certification in Data Science & AI (IIT Roorkee)

- GitHub: [@shahanansari-creator](https://github.com/shahanansari-creator)
- LinkedIn: [Mohd Shahan Ansari](https://www.linkedin.com/in/mohd-shahan-ansari-100479259/)

## 📜 License

This project is licensed under the MIT License.
