# Trader Behavior Insights: Market Sentiment Analysis

## 📌 Project Overview
This project analyzes the relationship between **Bitcoin market sentiment** (Fear & Greed Index) and **trader behavior/performance** using historical trading data from Hyperliquid.

The objective is to uncover how different market sentiment regimes influence:
- Trader profitability (PnL)
- Win rates
- Risk-taking behavior (trade size)
- Directional bias (Buy/Sell, Long/Short)

These insights can help design smarter, sentiment-aware trading strategies.

---

## 📂 Datasets Used

### 1️⃣ Historical Trader Data (Hyperliquid)
Contains detailed trade-level information such as:
- Account
- Coin
- Execution price
- Trade size (USD & tokens)
- Trade direction and side
- Timestamp (IST)
- Closed PnL
- Fees

### 2️⃣ Bitcoin Fear & Greed Index
Daily sentiment data with:
- Timestamp
- Sentiment value
- Classification (Fear, Extreme Fear, Neutral, Greed, Extreme Greed)
- Date

---

## 🛠️ Tools & Libraries
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn

---

## 🧹 Data Cleaning & Preparation

### Trader Data
- Converted column names to `snake_case`
- Converted `timestamp_ist` to datetime
- Removed rows with missing timestamps
- Dropped non-analytical columns (transaction hash, order ID, trade ID)
- Renamed key columns for clarity (e.g., `closed_pnl → pnl`)

### Sentiment Data
- Removed duplicate columns
- Converted date column to datetime
- Standardized sentiment labels:
  - Extreme Fear → Fear
  - Extreme Greed → Greed
- Retained Neutral as a separate category

### Data Merge
- Created a common `date` column in both datasets
- Merged trader data with sentiment data using an **inner join on date**

Final merged dataset contained **~35,800 trades** with sentiment labels.

---

## 📊 Exploratory Data Analysis

### 🔹 Average PnL by Sentiment
- Fear markets showed slightly higher average PnL than Greed.
- Neutral sentiment showed lower average PnL.

### 🔹 Win Rate Analysis
- Win rate was highest during **Greed** sentiment.
- Fear sentiment showed lower win probability but higher average PnL, indicating fewer but larger winning trades.

### 🔹 Risk Appetite (Trade Size)
- Average trade size (USD) was highest during **Fear**.
- Traders appear to deploy more capital cautiously during fearful markets.

### 🔹 Directional Behavior
- Greed periods showed increased Sell and Short activity.
- Fear periods had more conservative and hedged positions.

### 🔹 Visualization
- Boxplots of PnL vs sentiment revealed higher volatility during Fear and Greed phases compared to Neutral.

---

## 🧠 Key Insights

- Market sentiment has a **clear behavioral impact** on traders.
- Fear markets tend to reward disciplined, higher-conviction trades.
- Greed markets increase participation and win rate but also volatility.
- Neutral markets show reduced conviction and lower profitability.

---

## 🚀 Conclusion

Incorporating market sentiment into trading strategies can improve decision-making by:
- Adjusting risk exposure based on sentiment
- Modifying trade frequency during Greed phases
- Capitalizing on high-conviction opportunities during Fear

This analysis demonstrates how sentiment-aware analytics can enhance trading intelligence in crypto markets.

---

## 📎 How to Run the Project

1. Clone the repository
2. Place both CSV files in the project directory
3. Open `analysis.ipynb`
4. Run all cells top to bottom

---

## 👤 Author
Snehal Badakh  
Junior Data Scientist Candidate
