📈 AAPL Stock Price Prediction using Linear Regression
🔍 Overview
This project predicts the next day's closing price of Apple Inc. (AAPL) using historical stock data from Yahoo Finance. The workflow includes downloading data, engineering features like lag values, moving averages, and momentum, and then training a Linear Regression model to forecast future prices. The final result is visualized by comparing predicted vs. actual closing prices.

🧰 Libraries Used
yfinance: to fetch stock data

pandas: for data manipulation

matplotlib: for plotting

scikit-learn: for modeling and evaluation

🗂️ Dataset Details
Source: Yahoo Finance

Ticker: AAPL

Date Range: January 1, 2022 – December 31, 2024

Frequency: Daily

Features:

Open, High, Low, Close, Volume

Lagged closing prices: Close_t-1 to Close_t-5

Moving averages: MA_3 and MA_7

Momentum: Close(t-1) - Close(t-4)

Target: Next day’s Close price

⚙️ Workflow
Data Loading:
Used yfinance to download AAPL stock data from Jan 2022 to Dec 2024.

Feature Engineering:

Created lagged close prices for the past 5 days.

Calculated moving averages for the past 3 and 7 days.

Added a momentum feature based on the difference between close(t-1) and close(t-4).

Set the target as the next day's closing price.

Data Cleaning:

Dropped all rows with NaN values after creating shifted features.

Train/Test Split:

Split the dataset into 80% training and 20% testing without shuffling to preserve time sequence.

Model Training:

Trained a Linear Regression model using scikit-learn.

Prediction & Evaluation:

Predicted prices on the test set.

Evaluated the model using Mean Squared Error (MSE).

MSE was effectively 0 due to the short-term nature of stock prediction and model simplicity.

Visualization:

Plotted actual vs predicted closing prices over time using matplotlib.

📊 Results Summary
The model achieved very low error due to high correlation between recent prices and the next day's price.

Distribution of Target - Close_t-1 difference showed a mean of around 0.21, with typical fluctuations within ±4 USD.

🚀 How to Run
Install required libraries:
pip install yfinance pandas matplotlib scikit-learn

Run the Python script or Jupyter Notebook containing the logic above.
