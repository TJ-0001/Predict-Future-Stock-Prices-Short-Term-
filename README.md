# Stock Price Prediction (Short-Term)

## Objective
The goal of this project is to **predict the next day’s closing stock price** using historical market data from **Yahoo Finance**.  
This is a **regression problem**, where a **Random Forest Regressor** is trained to learn patterns from past stock prices and trading volume.

---

## Dataset
- **Source:** Yahoo Finance  
- **Accessed Using:** `yfinance` Python library  
- **Stock Used:** Apple Inc. (`AAPL`)   
- **Time Period:** 2023 – 2025  

### Features Used
- `Open` – Opening price of the stock  
- `High` – Highest price of the day  
- `Low` – Lowest price of the day  
- `Volume` – Number of shares traded  

### Target Variable
- `Next Close` – Closing price of the **next trading day**

---

## Data Preprocessing
1. Historical stock data downloaded using `yfinance`
2. Created a new target column by shifting the `Close` price by one day
3. Removed rows with missing values
4. Split the data into:
   - **Training set:** 80%
   - **Testing set:** 20% (time-ordered, no shuffling)

---

## Model Applied
### Random Forest Regressor
- Ensemble learning method using multiple decision trees
- Captures **non-linear relationships** between stock features
- Robust to noise and overfitting compared to single models

**Key Parameters:**
- `n_estimators = 100`
- `random_state = 42`

---

## Model Evaluation

### Metrics Used
- **Mean Absolute Error (MAE)**  
- **Root Mean Squared Error (RMSE)**  

These metrics measure how close the predicted prices are to the actual closing prices.

---

## Visualization
- Line plots comparing:
  - **Actual Closing Prices**
  - **Predicted Closing Prices**
- Helps visually assess how well the model follows real market movements

---

## Results & Insights
1. The Random Forest model is able to **closely track short-term price trends**
2. Predictions generally follow the direction of actual prices, though exact values may differ
3. Volume and price ranges (`High–Low`) play an important role in prediction
4. The model performs reasonably well for **short-term forecasting**, but:
   - It does not account for news, events, or market sentiment
   - Stock prices remain inherently unpredictable

---

## Files Included
- **stock_price_prediction.ipynb** — Jupyter Notebook containing all code, visualizations, and outputs.
---

## Libraries Used
- `pandas`
- `numpy`
- `matplotlib`
- `scikit-learn`
- `yfinance`

---

## References
- Yahoo Finance Data: https://finance.yahoo.com  
- yfinance Documentation: https://pypi.org/project/yfinance/
