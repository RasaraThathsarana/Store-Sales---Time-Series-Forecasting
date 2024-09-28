# Store Sales - Time Series Forecasting

This project is part of the **Store Sales - Time Series Forecasting** competition hosted on Kaggle. The goal is to build a machine learning model that accurately predicts the daily unit sales of thousands of products at multiple stores of **Corporación Favorita**, a large Ecuadorian grocery retailer.

## Project Overview

Time series forecasting plays a vital role in retail by helping businesses manage inventory, minimize wastage, and maximize customer satisfaction. This project leverages historical sales data, promotions, and other relevant features to predict future sales more effectively.

## Dataset

The dataset includes:

- **Train Data**: Contains historical sales data, item, store information, promotions, and other variables.
- **Test Data**: Sales data without target variables for prediction.
- **Oil Prices**: Historical daily prices of oil which can impact product costs and sales.
- **Holidays and Events**: List of national holidays and regional events.

For more details, check out the data description on the [Kaggle competition page](https://www.kaggle.com/competitions/store-sales-time-series-forecasting/data).

## Evaluation Metric

The evaluation metric for the competition is **Root Mean Squared Logarithmic Error (RMSLE)**, calculated as:

![image](https://github.com/user-attachments/assets/e69cca0d-219e-441e-865e-ca3661f0e2a2)


Where:

- `n` is the number of data points,
- `ŷᵢ` is the predicted value,
- `yᵢ` is the actual value,
- `log` represents the natural logarithm.

## Approach

### Data Preprocessing:

- Convert date columns to proper datetime format.
- Handle missing data and outliers.
- Feature engineering:
  - Moving averages of oil prices.
  - Decomposing date into year, month, day, and weekday.
  - One-hot encoding for categorical variables such as promotions.

### Modeling:

- We utilized **CatBoostRegressor** for its capability to handle categorical variables and time series data efficiently.
- We leveraged moving averages for oil prices to capture macroeconomic trends.
- Cross-validation techniques were used to prevent overfitting.

### Hyperparameter Tuning:

- Fine-tuned the model using various metrics like **Mean Absolute Error (MAE)**, **Mean Squared Error (MSE)**, and **RMSLE**.
- Performed grid search to optimize parameters like depth, learning rate, and iterations.

### Evaluation:

- Submitted predictions for the test data and evaluated the performance using **RMSLE**.
