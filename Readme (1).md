# 🇮🇳 India Lok Sabha 2024 — Election Data Analysis

A complete end-to-end **Exploratory Data Analysis (EDA)** project on the 2024 Indian General Election results, built in Python using Pandas, Matplotlib, Seaborn, and Scikit-learn.

---

## 📌 Project Overview

This notebook analyzes all **543 Lok Sabha constituencies** from the 2024 Indian General Election. It covers data loading, cleaning, visual exploration, party-level comparisons, and a linear trend-based prediction for the 2029 election.

---

## 📂 Repository Structure

```

📁 EDA
  ┣ 📓 INDIAN_ELECTION.ipynb     ← Main analysis notebook
  ┗ 📄 clean_election_2024.csv   ← Cleaned output dataset (generated on run)
  ┗ 📄 README.md
```

---


## 🔧 Steps in the Notebook

### 1. Import Libraries
`pandas`, `numpy`, `matplotlib`, `seaborn`, `sklearn`, `requests`

### 2. Load Data
- Fetches CSV directly from GitHub via URL
- Runs `.shape`, `.info()`, and `.describe()` for structural diagnosis

### 3. Data Cleaning
- Renames columns to clean, consistent names
- Converts `Margin` from string (with commas) to numeric
- **Missing value imputation** with written justification:
  - `Runner_Up` / `Runner_Party` → `fillna('Unknown')` (structural missingness, not random)
- **Duplicate removal** — verified final count is exactly zero

### 4. EDA Insights
Key metrics printed:
- Total constituencies & parties
- BJP and INC seat counts
- Highest, lowest, and average winning margins
- Party-level margin comparisons

### 5. Visualizations — EDA Dashboard (6 charts)

| Chart | Type | Insight |
|---|---|---|
| ① Top 10 Parties by Seats | Horizontal bar | BJP dominates, but below majority |
| ② Seat Share | Pie chart | BJP + NDA vs opposition split |
| ③ Winning Margin Distribution | Histogram + KDE | Right-skewed; most wins by small margins |
| ④ BJP vs INC — Seats & Avg Margin | Twin-axis bar + line | BJP wins fewer but by larger margins |
| ⑤ Top 30 Highest Margin Winners | Horizontal bar | Dominant regional wins visible |
| ⑥ Margin Spread by Party | Violin plot | Full distribution shape per party |

**Additional charts:**
- Scatter plot — margin by constituency rank, colored by party
- Seaborn correlation heatmap

### 6. 2029 Election Prediction
Uses `LinearRegression` on historical seat data (2009–2024) to estimate BJP and INC seat counts for 2029.

> 🎓 **Practice Purpose Only** — This prediction is built as a beginner exercise to demonstrate how Linear Regression works on time-series data. It is **not** a professional or political forecast. Real election outcomes depend on coalition dynamics, regional factors, economic conditions, and many variables a simple linear model cannot capture. Do not interpret these numbers as actual predictions.

### 7. Final Summary + Export
- Prints summary statistics
- Saves cleaned data to `clean_election_2024.csv`

### 8. Insights for ML Modeling
Addresses two key architectural questions:
- How to handle outliers in `Margin` before model training
- Collinearity risks when encoding categorical features

---

## 📈 Key Findings

- **BJP won 240 seats** — below the 272 majority mark, requiring coalition partners
- **INC recovered to 99 seats** — up significantly from 52 in 2019
- **Winning margins are right-skewed** — median margin is far lower than the mean
- **BJP wins more dominantly** (higher average margin per seat than INC)
- **No single party achieved an outright majority** — coalition politics will define 2029

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning, aggregation |
| `numpy` | Numerical operations |
| `matplotlib` | Base plotting |
| `seaborn` | Statistical visualizations |
| `scikit-learn` | Linear regression for 2029 prediction |
| `requests` | Fetching CSV from URL |

---

## ▶️ How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/indian-election-2024-eda.git
   cd indian-election-2024-eda
   ```

2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn requests
   ```

3. Open the notebook:
   ```bash
   jupyter notebook EDA/INDIAN_ELECTION.ipynb
   ```

4. Run all cells: **Kernel → Restart & Run All**

> No local CSV file is needed — the dataset is fetched automatically from GitHub.

---

## 📁 Output Files

| File | Description |
|---|---|
| `EDA/clean_election_2024.csv` | Cleaned dataset generated after running the notebook |

---


