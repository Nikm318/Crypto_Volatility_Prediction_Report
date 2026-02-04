# Crypto_Volatility_Prediction_Report

📈 Cryptocurrency Volatility Prediction System
📌 Project Overview

This project implements an end-to-end machine learning system to predict cryptocurrency price volatility using historical market data.
The system covers data preprocessing, feature engineering, exploratory data analysis (EDA), model training, evaluation, and deployment via a Flask API.

The objective is to analyze volatility patterns in cryptocurrency markets and build a predictive model that can assist in risk analysis and decision-making.

🧠 Problem Statement

Cryptocurrency markets are highly volatile and unpredictable.
The goal of this project is to predict short-term volatility using historical price movements and liquidity indicators.

📂 Dataset Description

Data Type: Daily time-series data

Features:

Open, High, Low, Close prices

Trading Volume

Market Capitalization

Date

Cryptocurrency name

Scope: Multiple cryptocurrencies over multiple time periods

⚙️ Project Workflow
Raw Data
 → Data Preprocessing
 → Feature Engineering
 → Exploratory Data Analysis (EDA)
 → Model Training
 → Model Evaluation
 → Flask API Deployment
🧹 Data Preprocessing

Removal of unnecessary columns

Handling missing values using forward-fill and median imputation

Ensuring chronological order per cryptocurrency

Filtering invalid values (negative volume or market cap)

Removing duplicate records

🛠️ Feature Engineering

The following features are engineered to capture market behavior:

Log Returns

High–Low Price Spread

14-day Rolling Volatility (Target Variable)

Liquidity Ratio (Volume / Market Cap)

7-day Volume Moving Average

Simple Moving Average (SMA – 14)

Exponential Moving Average (EMA – 14)

📊 Exploratory Data Analysis (EDA)

EDA is performed to understand:

Volatility distribution and clustering

Price trends over time

Relationship between volume and volatility

Correlation between engineered features

Visualizations include:

Volatility distribution plots

Price and volatility time-series plots

Volume vs volatility scatter plots

Correlation heatmaps

🤖 Machine Learning Model

Model Used: XGBoost Regressor

Reason: Handles non-linearity and volatility patterns effectively

Train/Test Split: Time-based split (80% train, 20% test)

📈 Evaluation Metrics

RMSE (Root Mean Squared Error)

MAE (Mean Absolute Error)

R² Score

These metrics are used to evaluate prediction accuracy and model reliability.

🚀 Deployment

The trained model is deployed using a Flask API, allowing predictions via HTTP requests.

API Endpoint

Endpoint: /predict

Method: POST

Input: JSON containing engineered features

Output: Predicted volatility value

Example request:

{
  "log_return": 0.01,
  "hl_spread": 0.03,
  "liquidity_ratio": 0.002,
  "volume_ma_7": 100000000,
  "sma_14": 30000,
  "ema_14": 29800
}
🧩 Project Structure
├── data/
│   └── crypto_data.csv
├── src/
│   └── crypto_volatility_pipeline.py
├── eda/
│   └── eda_report.pdf
├── docs/
│   ├── HLD.pdf
│   ├── LLD.pdf
│   ├── Pipeline_Architecture.pdf
│   └── Final_Report.pdf
├── models/
│   ├── xgb_volatility_model.pkl
│   └── scaler.pkl
├── README.md
🧪 How to Run (Google Colab / Local)

Upload the dataset

Run the training pipeline

Start the Flask server

Send POST requests to /predict

📌 Key Insights

Cryptocurrency volatility is right-skewed and clustered

Liquidity plays a major role in stabilizing volatility

High–Low price spread is a strong volatility indicator

Non-linear models outperform linear approaches

🏁 Conclusion

This project demonstrates a complete, modular, and scalable system for cryptocurrency volatility prediction.
By combining robust feature engineering, insightful EDA, and a powerful machine learning model, the system effectively captures volatility dynamics and supports real-world deployment.

🔮 Future Enhancements

Accept raw OHLC data directly in API

Incorporate deep learning models (LSTM/GRU)

Add real-time data ingestion

Improve explainability using SHAP values
