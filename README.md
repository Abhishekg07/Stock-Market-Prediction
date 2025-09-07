# Stock-Market-Prediction
Stock Market Prediction

# Stock Price Prediction using Data Mining in Financial Data

##  Overview
This project predicts **daily stock price movement (Up/Down)** for a selected set of U.S. equities using **historical OHLCV data** and machine learning.  
We analyze five stocks — **AAPL, MSFT, NKE, SBUX, BA** — over the period **2020-01-01 to 2025-01-01**.  
The notebook explores return behavior, performs EDA, and benchmarks eight classification models.

---

##  Problem Statement
### Predicting Stock Price Movement
The task is to forecast whether the **next day’s closing price** will be **higher (Up)** or **lower (Down)** than today’s close.

### Importance
- **Investment Decision Making:** Even small predictive improvements can help traders manage risk and improve returns.  
- **Market Efficiency:** Tests the limits of short-term predictability in equity markets.  
- **Economic Measures:** Stock movements reflect sentiment and broader economic expectations.  
- **Risk Management:** Anticipating movement aids in hedging and portfolio adjustment.

### Why Data Science?
- **Complex patterns** in financial markets require ML to uncover weak, non-linear signals.  
- **Data availability**: Historical OHLCV data is easily accessible via `yfinance`.  
- **Continuous learning**: Models can be retrained as new data arrives.

---

##  Data Collection and Processing
- **Source:** Yahoo Finance (`yfinance`)  
- **Stocks:** AAPL, MSFT, NKE, SBUX, BA  
- **Period:** 2020-01-01 → 2025-01-01  
- **Features:** Open, High, Low, Close, Volume  
- **Target:** `Price_Up = 1` if `Close[t+1] > Close[t]`, else `0`  

Data reshaping includes stacking multi-index download, renaming columns, handling datatypes, and adding engineered target variables.

---

##  Exploratory Data Analysis (EDA)
- **Summary statistics** of the dataset.  
- **Daily Returns**: Close-to-Close returns to capture day-to-day direction.  
- **Weekly Returns**: Resampled (`W-FRI`), % change.  
- **Monthly Returns**: Resampled (`ME`), % change.  
- **Other visualizations**:
  - Time series plots of closing prices.  
  - Boxplots of trading volumes.  
  - Scatter plots (Closing Price vs. Volume).  

---

##  Machine Learning Models

**Formulation:** Binary classification (Up/Down).  
**Train/Test split:** 80/20 (stratified).  

### Models Used
- Logistic Regression  
- Support Vector Machine  
- K-Nearest Neighbors  
- Decision Tree  
- Random Forest  
- Naive Bayes  
- AdaBoost  
- Gradient Boosting  

### Evaluation Metrics
- Accuracy  
- Precision, Recall, F1-Score  
- Confusion Matrix  
- ROC Curve & AUC  

---

##  Results

- **Accuracy range:** ~0.51 – 0.54  
- **ROC-AUC range:** ~0.49 – 0.53  
- **Best Model:** *AdaBoost*  
  - Accuracy ≈ 0.535  
  - ROC-AUC ≈ 0.535  

 **Key Takeaways**  
- Predicting short-term (daily) direction with raw OHLCV data is **very difficult**; models are only slightly above random.  
- Ensemble methods (AdaBoost, Random Forest, Gradient Boosting) performed better than linear models.  
- Confusion matrices showed mild bias toward “Up,” reflecting upward market drift.  

---


