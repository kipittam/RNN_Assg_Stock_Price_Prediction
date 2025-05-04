# Stock-Price-Prediction-Using-RNN-s

## Objective
The objective of this assignment is to try and predict the stock prices using historical data from four companies IBM (IBM), Google (GOOGL), Amazon (AMZN), and Microsoft (MSFT).

We use four different companies because they belong to the same sector: Technology. Using data from all four companies may improve the performance of the model. This way, we can capture the broader market sentiment.

The problem statement for this assignment can be summarised as follows:

> Given the stock prices of Amazon, Google, IBM, and Microsoft for a set number of days, predict the stock price of these companies after that window.

## Business Value
Data related to stock markets lends itself well to modeling using RNNs due to its sequential nature. We can keep track of opening prices, closing prices, highest prices, and so on for a long period of time as these values are generated every working day. The patterns observed in this data can then be used to predict the future direction in which stock prices are expected to move. Analyzing this data can be interesting in itself, but it also has a financial incentive as accurate predictions can lead to massive profits.

### **Data Description**
You have been provided with four CSV files corresponding to four stocks: AMZN, GOOGL, IBM, and MSFT. The files contain historical data that were gathered from the websites of the stock markets where these companies are listed: NYSE and NASDAQ. The columns in all four files are identical. Let's take a look at them:

- `Date`: The values in this column specify the date on which the values were recorded. In all four files, the dates range from Jaunary 1, 2006 to January 1, 2018.

- `Open`: The values in this column specify the stock price on a given date when the stock market opens.

- `High`: The values in this column specify the highest stock price achieved by a stock on a given date.

- `Low`: The values in this column specify the lowest stock price achieved by a stock on a given date.

- `Close`: The values in this column specify the stock price on a given date when the stock market closes.

- `Volume`: The values in this column specify the total number of shares traded on a given date.

- `Name`: This column gives the official name of the stock as used in the stock market.

There are 3019 records in each data set. The file names are of the format `\<company_name>_stock_data.csv`.
#### Assignment is Completed by Kiran Pittampally and Keval R Menon

#### Model Development
- In this project, we successfully developed, trained, and evaluated both SimpleRNN and LSTM models to forecast stock prices for four major companies: Amazon (AMZN), Google (GOOGL), IBM, and Microsoft (MSFT).
- Constructed SimpleRNN and LSTM architectures using windowed time series data.
- Applied Keras Tuner for hyperparameter optimization of the LSTM model, fine-tuning:
    - Number of layers
    - Units per layer
    - Dropout rates
    - Learning rates
- Evaluated model performance using:
    - Mean Absolute Error (MAE)
    - Mean Squared Error (MSE)
    - Root Mean Squared Error (RMSE)
    - R² Score

#### Quantitative Performance Summary
| Stock | Best Model | MAE (↓) | RMSE (↓) | R² Score (↑) |
|:-----:|:----------:|:-------:|:--------:|:------------:|
| AMZN  | LSTM       | 6.1 dollars | 13.2 dollars | 0.9971 |
| GOOGL | LSTM       | 5.9 dollars | 8.1 dollars | 0.9989 |
| IBM   | LSTM       | 1.7 dollars | 2.3 dollars | 0.9955 |
| MSFT  | LSTM       | 5.9 dollars | 7.4 dollars | 0.7308 |


#### Key Insights
- LSTM Superiority: Across all stocks, the LSTM model consistently outperformed SimpleRNN, achieving lower error rates and higher R² scores.
- Stock-Specific Predictability:
    - High Predictive Accuracy for AMZN, GOOGL, and IBM:
        - All three stocks have very high R² scores (above 0.99), indicating that the model explains nearly all the variance in the stock prices.
        GOOGL has the lowest RMSE among the high-performing stocks, suggesting the most precise predictions.
    - IBM Shows the Best Overall Error Metrics:
       - Lowest MAE, MSE, and RMSE, making it the most accurately predicted stock in absolute terms.
        Slightly lower R² than GOOGL and AMZN, but still excellent.
    - MSFT Performance is Noticeably Weaker:
        - Although the error metrics are moderate, the R² Score is significantly lower (0.7308).
        This suggests that the model struggles to capture the underlying patterns in MSFT’s stock price, possibly due to higher volatility or external influencing factors.

 - Summary
    - The model performs exceptionally well for AMZN, GOOGL, and IBM, with GOOGL showing the best balance of low error and high R².
      MSFT stands out as an outlier with lower predictability, indicating the need for either more complex modeling or additional features.