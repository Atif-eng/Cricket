# 🏏 Cricket 2026: The "Moneyball" Analysis

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python)
![Library](https://img.shields.io/badge/Library-Plotly_Interactive-green?style=for-the-badge&logo=plotly)
![Algorithm](https://img.shields.io/badge/Algorithm-K--Means_Clustering-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

## 📌 Project Overview
**"Rankings tell you who is good. Math tells you who is valuable."**

This project moves beyond standard ICC rankings to calculate the true **Impact Score** of modern cricketers. Using the "Moneyball" philosophy, we analyze data from the 2026 season to identify **MVPs (Most Valuable Players)** across ODI and T20I formats.

By applying **Weighted Metrics** and **Unsupervised Learning (K-Means)**, we separate the "Stat-Padders" from the "Match-Winners."

**Author:** Muhammad Atif

## 📂 Dataset
The analysis is based on the `Cricket_Player_Stats_2026.csv` dataset.
- **Key Features:** `Rating`, `Average`, `Matches_Played`.
- **Targets:**
  - **MVP Calculation:** A derived metric combining consistency (Average) and dominance (Rating).
  - **Player Segments:** Elite Icons vs. Standard Top Order.

## 🛠 Tech Stack
- **Language:** Python
- **Data Manipulation:** `pandas`, `numpy`
- **Visualization:** - `plotly.express` (Interactive Charts)
  - `seaborn` (Static Statistical Plots)
- **Machine Learning:** `scikit-learn` (K-Means Clustering, MinMaxScaler)

## 📊 Methodology: The "Impact Score"
We engineered a custom feature called **`Impact_Score`** to rank players holistically.

$$\text{Impact Score} = (0.4 \times \text{Normalized Rating}) + (0.4 \times \text{Normalized Average}) + (0.2 \times \text{Normalized Matches})$$

* **Rating (40%):** Represents current form and dominance.
* **Average (40%):** Represents consistency and reliability.
* **Matches (20%):** Represents experience and availability.

## 🔍 Key Insights & Visuals

### 1. The MVP Leaderboard 🏆
Our algorithm identified the following players as the highest-impact assets for 2026:
* **ODI MVP:** **Shubman Gill (IND)** — *High Average + Consistency.*
* **T20I MVP:** **Suryakumar Yadav (IND)** — *Unmatched Strike Rate/Rating.*

### 2. Player Clustering (K-Means) 
We used K-Means to group players into distinct tiers:
* **Cluster 0 (The Icons):** Rank 1-2 players who are statistically outliers (e.g., Babar Azam, Virat Kohli).
* **Cluster 1 (The Backbone):** Solid performers who stabilize the team but lack the "X-Factor" of icons.

### 3. Format Dominance
* **ODI vs. T20I:** The analysis shows that ODI players maintain significantly higher averages (50+), while T20I players are optimized for high-intensity, lower-average burst performance.

## 🚀 How to Run

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/cricket-moneyball-2026.git](https://github.com/your-username/cricket-moneyball-2026.git)
    ```
2.  **Install dependencies:**
    ```bash
    pip install pandas numpy scikit-learn seaborn plotly
    ```
3.  **Run the Analysis:**
    Open `cricket-2026-moneyball-analysis-player-ranking.ipynb` to explore the interactive Plotly charts.

## 💻 Code Teaser
Here is how we normalized the data to calculate the Impact Score:

```python
from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()
cols_to_scale = ['Rating', 'Average_2025', 'Matches_Played_2025']

# Normalize stats to 0-1 range
df[cols_to_scale] = scaler.fit_transform(df[cols_to_scale])

# Calculate Weighted Impact Score
df['Impact_Score'] = (df['Rating'] * 0.4) + (df['Average_2025'] * 0.4) + (df['Matches_Played_2025'] * 0.2)
