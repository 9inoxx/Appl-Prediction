# Appl-Prediction
- Pre reqs sklearn, yfinance, pandas, matplotlib, tensorflow

  # Summary
- The historical stock price data for Apple (AAPL) is loaded from a CSV file.
The date column is set as the index for easier time series analysis.
Missing values are filled using a forward-fill method, which carries the last known value forward to fill in any gaps.
- Creating Lagged Features
Lagged features are created from the 'Close' price to include information about past prices. For example:
Lag1 refers to the closing price of the previous day.
Lag2 refers to the closing price from two days ago.
Lag3 refers to the closing price from three days ago.
These lagged features help the model learn patterns from recent price movements.
- Calculating a Moving Average
A simple moving average is calculated over a short window (just 1 day in this case).
- Defining the Target Variable
The target variable is set as the next day's closing price, which is achieved by shifting the 'Close' price forward by one day.
This way, today’s price and features are paired with tomorrow’s closing price as the target.
- Handling Missing Values
After shifting and calculating lagged features, some rows may contain NaN values.
These rows are dropped to ensure the dataset is complete and ready for training.
- Setting Up Features and Target Variables
A set of features is selected for training the model.
The target variable is the next day's closing price.
- Scaling the Data
The features are standardized using a scaler, which transforms them to have a mean of 0 and a standard deviation of 1.
- Splitting Data into Training and Testing Sets
The scaled data is split into training and testing sets, with 80% used for training and 20% for testing.
This allows the model to learn patterns from the training set and then be evaluated on how well it generalizes to unseen data in the testing set.
It minimizes the mean squared error (MSE), which measures how close the model's predictions are to the actual values.
- Generating Predictions
After training, the model makes predictions for the entire dataset.
These predictions are added as a new column in the dataset for comparison with actual closing prices.
- Forecasting the Next Day’s Price
The most recent data point is extracted and scaled to match the input format.
This scaled data is used as input to the model to forecast the next day’s closing price.
The prediction is then unscaled to reflect the actual price level.
![45e6970c-5a75-4895-b976-db75b0fd1769](https://github.com/user-attachments/assets/c0ef002b-e324-4f59-a4d6-909d01a0f14a)

