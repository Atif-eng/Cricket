# 🏏 Cricket Player Stats 2026: The Leaderboard

![Dataset Status](https://img.shields.io/badge/Dataset-Updated-success?style=for-the-badge&logo=kaggle)
![Domain](https://img.shields.io/badge/Domain-Sports_Analytics-orange?style=for-the-badge&logo=python)
![Format](https://img.shields.io/badge/Format-ODI_%7C_T20I-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-CC0_Public_Domain-green?style=for-the-badge)

## 🏆 Overview
Welcome to the **Cricket Player Stats 2026** dataset! 

This dataset provides a snapshot of the world's top-performing cricketers leading into the 2026 season. It captures critical performance metrics from the 2025 calendar year, including **ICC Rankings, Match Averages, and Format-specific Ratings**.

Whether you are building a **Fantasy Cricket Predictor**, analyzing **Team Dominance**, or just checking who is currently the "King of Cricket," this dataset serves as a clean, structured baseline.

> **Note:** This dataset focuses on the elite tier of players across **ODI (One Day International)** and **T20I (Twenty20 International)** formats.

---

## 📂 Dataset Structure

The dataset consists of a single CSV file: `Cricket_Player_Stats_2026.csv`.

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| **`Rank`** | `Integer` | The player's official ranking (1-5) in their respective format. |
| **`Player`** | `String` | Name of the cricketer (e.g., *Babar Azam, Virat Kohli*). |
| **`Team`** | `String` | The national team they represent (e.g., *IND, PAK, AUS*). |
| **`Rating`** | `Integer` | Official performance points/rating. |
| **`Format`** | `String` | The game format: `ODI` or `T20I`. |
| **`Matches_Played_2025`** | `Integer` | Number of international matches played in the previous year. |
| **`Average_2025`** | `Float` | The batting average maintained during the 2025 season. |

---

## 📊 Quick Insights (EDA)
Here is a breakdown of the elite talent pool included in this dataset:

### 🌍 Team Representation (Top 10 Players)
| Team | Players Count |
| :--- | :--- |
| **India (IND)** | 4 |
| **Pakistan (PAK)** | 3 |
| **Australia (AUS)** | 1 |
| **England (ENG)** | 1 |
| **South Africa (SA)** | 1 |

### 🏏 Top Performers by Format
- **ODI King:** **Babar Azam (PAK)** - *Rating: 824*
- **T20I King:** **Suryakumar Yadav (IND)** - *Rating: 861*
- **Highest Average (2025):** **Shubman Gill (IND)** with an impressive **60.1** in ODIs.

---

## 💡 Potential Use Cases

This dataset is perfect for:

1.  **Sports Analytics & Visualization**
    * *Comparison:* Bar charts comparing Batting Averages vs. ICC Ratings.
    * *Team Strength:* Analyze which country dominates the top 5 rankings.

2.  **Fantasy Cricket Algorithms**
    * Predict potential fantasy points based on `Average_2025` and `Matches_Played`.

3.  **Player Form Analysis**
    * Identify players who are "Over-performing" relative to their ranking based on their 2025 average.

---

## 💻 Getting Started

### Python Example
```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load the dataset
df = pd.read_csv('Cricket_Player_Stats_2026.csv')

# Visualizing the Top Ratings
plt.figure(figsize=(10, 6))
sns.barplot(data=df, x='Player', y='Rating', hue='Format', palette='viridis')
plt.title('Top Player Ratings: ODI vs T20I (2026)')
plt.xticks(rotation=45)
plt.show()
