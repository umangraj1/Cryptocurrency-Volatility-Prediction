# Cryptocurrency-Volatility-Prediction

##  Project Overview
Cryptocurrency markets are known for their high volatility — rapid price changes that make trading risky yet profitable.  
This project develops a **Machine Learning pipeline** to predict **7-day cryptocurrency volatility** using  
historical OHLC (Open, High, Low, Close), Volume, and Market Cap data.  

It follows the complete **PwSkills Machine Learning Project Workflow**, including:
- Data Cleaning and Normalization  
- Exploratory Data Analysis (EDA)  
- Feature Engineering (Volatility, Liquidity, Moving Averages)  
- Model Training, Evaluation, and Saving  
- Project Documentation (HLD, LLD, Reports)

---

##  Dataset Information
**Dataset:** Historical cryptocurrency daily data (50+ coins)  
**Columns:**  
`date`, `open`, `high`, `low`, `close`, `volume`, `market_cap`, `crypto_name`

**Engineered Features:**  
- `daily_return = (close - open) / open`  
- `vol_7d = std(daily_return, 7-day rolling)`  
- `liquidity_ratio = volume / market_cap`  
- `ma7`, `ma30` (7-day & 30-day moving averages)

---

##  Pipeline Architecture
```text
data/dataset.csv
      ↓
src/data_preprocessing.py      → Cleaning, Missing Values, Normalization
      ↓
src/feature_engineering.py     → Rolling Volatility, Liquidity Ratio, Moving Averages
      ↓
src/model_training.py          → Train RandomForestRegressor, Evaluate, Save Model
      ↓
models/scaler.pkl              → Scaler file saved
app/streamlit_app.py           → Deployment interface (optional)
