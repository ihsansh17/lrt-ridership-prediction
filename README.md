# LRT Kelana Jaya Line Daily Ridership Prediction using XGBoost

This project uses machine learning to predict daily ridership for LRT Kelana Jaya line. It combines historical ridership data with time-related and lag features to forecast daily ridership for November and December 2024. By forecasting ridership with greater accuracy, transportation management can better allocate resources, improve customer service, and make informed decisions about transit operations.

## Project Overview

- **Objective**: Predict daily ridership for November and December 2024 to help with operational decision-making, staffing, and customer experience improvements.
- **Approach**: Built and tuned an XGBoost regression model using time-related features (day of the week, month, etc.) and lag features. The model was evaluated using cross-validation (TimeSeriesSplit) and compared to a baseline model based on day-of-week averages.
- **Key Result**: The XGBoost model achieved lower RMSE than the baseline, indicating improved predictive performance.

## Table of Contents
1. [Motivation](#motivation)
2. [Methodology](#methodology)
3. [Results](#results)
4. [Business Impact](#business-impact)
5. [Future Work](#future-work)
6. [Usage](#usage)
7. [Requirements](#requirements)

## Motivation
Predicting daily ridership accurately is essential for:
- **Optimizing Operations**: Ensuring the right number of vehicles and staff are available to meet demand.
- **Improving Customer Experience**: Reducing crowding and managing traffic flows.
- **Strategic Planning**: Helping planners decide on potential expansions, service adjustments, and budget allocations.

## Methodology

1. **Data Preparation**: Created features capturing time-related information (e.g., day of the week, month) and lagged ridership values to capture recent trends.
2. **Hyperparameter Tuning**: Used Optuna to find optimal hyperparameters for the XGBoost model.
3. **Evaluation**:
   - **Baseline Model**: Calculated day-of-week average ridership from the training set for each day of the week.
   - **Cross-Validation**: Used TimeSeriesSplit to evaluate model performance in a time series context.
   - **Performance Metric**: Root Mean Squared Error (RMSE) to evaluate the prediction accuracy.

## Results

- **Model Performance**: The XGBoost model outperformed the baseline day-of-week average, achieving a lower RMSE on the test set. This indicates a more precise prediction of daily ridership patterns.

## Business Impact

This model can benefit multiple teams within a transit organization:

- **Operations**: Helps with staffing, vehicle allocation, and scheduling by accurately forecasting peak and off-peak ridership days.
- **Customer Service**: Enhances passenger experience through better crowd management and timely communication.
- **Strategic Planning**: Provides insights into long-term ridership trends, guiding infrastructure investment and expansion planning.
- **Finance**: Assists with budgeting and cost forecasting, ensuring efficient allocation of resources.

## Future Work

- **Incorporate Additional Features**: Include weather data, public holidays and special events data to capture additional factors influencing ridership.
- **Forecasting Methods**: Explore time-series techinques such as Exponential Smoothing and ARIMA.
- **Broader Deployment**: Expand this model to other metro lines and integrate it into live operational systems.
- **Model Interpretability**: Use feature importance or SHAP values to better understand which factors most impact ridership.

## Usage

To train and evaluate the model, follow these steps:

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/yourusername/metro-ridership-prediction.git
    cd metro-ridership-prediction
    ```

2. **Run the Training Script**:
    ```bash
    python train_model.py
    ```

3. **Generate Predictions**:
    Use the trained model to generate predictions on a new dataset:
    ```python
    python predict_ridership.py --input data/new_data.csv --output results/predictions.csv
    ```

## Requirements

- Python 3.8+
- Libraries:
  - xgboost
  - scikit-learn
  - pandas
  - numpy
  - optuna

Install requirements using:
```bash
pip install -r requirements.txt
