# Binance Trades Analysis
This project presents the analysis of historical trade data from Binance accounts over a 90- day period. The primary objective was to calculate financial metrics for each account, rank them, and provide a top 20 list based on their performance.
The dataset includes the following key features:

- Port_IDs: Unique identifiers for accounts.
- Trade_History: Historical trades containing details like timestamp, asset, trade side (BUY/SELL), price, realized profit, and more.

## **Methodology**

### **1. Data Exploration and Cleaning**

- The dataset was loaded using pandas for analysis.
- The Trade_History column contained JSON-like strings, which were parsed into structured data.
- Missing and invalid values in the Trade_History column were handled gracefully to ensure data integrity.

### **2. Feature Engineering**

- The Trade_History column was exploded to create individual rows for each trade, enabling detailed analysis.
- The parsed data was normalized to extract relevant columns such as symbol, side, price, realizedProfit, and quantity.
- Additional features like ROI, cumulative returns, and trade outcomes were derived.

### **3. Metrics Calculation**

Seven key metrics were calculated for each account:

1. **ROI (Return on Investment)**: Computed as the percentage return relative to the quantity invested.
2. **PnL (Profit and Loss)**: Aggregated realized profit for all trades.
3. **Sharpe Ratio**: Calculated as the mean return divided by the standard deviation of returns, representing risk-adjusted performance.
4. **MDD (Maximum Drawdown)**: The largest percentage drop from a cumulative return peak.
5. **Win Rate**: The percentage of trades that resulted in a profit.
6. **Total Positions**: Total number of trades executed by each account.
7. **Win Positions**: Number of profitable trades.

### **4. Ranking Algorithm**

- A scoring system was devised using weights for the calculated metrics:
    - PnL (40%)
    - Sharpe Ratio (30%)
    - Win Rate (20%)
    - Total Positions (10%)
- Each metric was normalized and combined to compute a final score for each account.
- Accounts were ranked based on their scores, with the top 20 accounts identified.

## **Findings**

1. **Top-Performing Accounts**:
    
    - The highest-ranked accounts exhibited a balance between high PnL, strong risk-adjusted returns (Sharpe Ratio), and consistent profitability (Win Rate).
2. **Statistical Summary**:
    
    - Average PnL across accounts was positive, indicating overall profitability.
    - Most accounts showed low drawdowns, suggesting disciplined risk management.
3. **Insights**:
    
    - Accounts with high total positions often had moderate win rates but consistent profits due to volume-based strategies.
    - Accounts with low maximum drawdowns were typically ranked higher due to their stability.

## **Conclusion**

The analysis successfully identified and ranked accounts based on financial performance metrics. The top 20 accounts demonstrated strong profitability, consistent returns, and effective risk management.

## **Limitations**:

- The analysis assumes accurate and complete trade history data.
- External factors influencing trade outcomes (e.g., market conditions) were not considered.

## **Recommendations**:

- Extend the analysis to include additional metrics like volatility or trade duration.
- Perform scenario-based testing to assess account performance under varying market conditions.
