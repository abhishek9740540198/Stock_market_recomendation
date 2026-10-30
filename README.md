# 📈 Stock Market Recommendation System

A machine learning-based stock recommendation system that predicts **BUY**, **HOLD**, or **SELL** signals by combining technical analysis with real-time news sentiment analysis.

The project trains individual machine learning models for multiple stocks, generates technical indicators from historical market data, analyzes recent news sentiment, and combines both scores to produce a final investment recommendation.

---

## 🚀 Features

- Predicts **BUY**, **HOLD**, and **SELL** signals
- Machine learning model trained for each stock
- Technical indicators for feature engineering
- News sentiment analysis using NLP
- REST API built with Flask
- Supports multiple stocks
- Top 5 stock recommendation endpoint
- Scalable architecture with separate models and scalers

---

## 🛠️ Tech Stack

- Python
- Flask
- Flask-CORS
- Scikit-learn
- XGBoost
- Pandas
- NumPy
- Joblib
- BeautifulSoup
- NLTK

---

## 📂 Project Structure

```
Stock-Market-Recommendation-System/
│
├── app.py                  # Flask backend
├── main.py                 # Model training script
├── requirements.txt
│
├── models/
│   ├── *_model.pkl
│   └── *_scaler.pkl
│
├── stock_data/
│   └── *.csv
│
├── news_sentiment.py
│
└── README.md
```

---

## ⚙️ Installation

### Clone the repository

```bash
git clone https://github.com/chandanreddy76/Stock-market-recommendation-system.git
cd Stock-market-recomendation-system
```

### Create virtual environment

```bash
python -m venv venv
```

Activate it

Linux / macOS

```bash
source venv/bin/activate
```

Windows

```bash
venv\Scripts\activate
```

### Install dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Train Models

Train models for all available stocks.

```bash
python main.py
```

This will:

- Load stock datasets
- Generate technical indicators
- Train XGBoost models
- Save trained models
- Save feature scalers

---

## ▶️ Run Backend

```bash
python app.py
```

Server starts on

```
http://127.0.0.1:5000
```

---

## 📌 API Endpoints

### Predict Recommendation

**POST**

```
/predict
```

Example Request

```json
{
    "symbol": "RELIANCE",
    "sentiment_method": "vader"
}
```

Example Response

```json
{
    "symbol":"RELIANCE",
    "prediction":"BUY",
    "model_prediction":"BUY",
    "final_score":0.73
}
```

---

### Top 5 Recommendations

**GET**

```
/top5
```

Returns the top five stocks ranked using the combined machine learning and sentiment score.

---

## 📊 Technical Indicators Used

The model uses several indicators generated from historical stock prices:

- Daily Returns
- 5-Day Returns
- 10-Day Moving Average
- 20-Day Moving Average
- Price vs Moving Average
- Volatility
- RSI (Relative Strength Index)
- Volume Moving Average
- Volume Ratio

---

## 📰 News Sentiment Analysis

The recommendation system also analyzes recent news related to a company.

Sentiment score is combined with the machine learning prediction to improve the final recommendation.

Final Score:

```
Final Score =
0.6 × ML Prediction
+
0.4 × News Sentiment
```

---

## 🤖 Machine Learning

The project uses:

- XGBoost Classifier
- StandardScaler
- Feature Engineering
- Multi-class Classification

Output Classes

- BUY
- HOLD
- SELL

---

## 📦 Requirements

Install all required packages using

```bash
pip install -r requirements.txt
```

---

## 🎯 Future Improvements

- Live stock price integration
- Interactive dashboard
- Portfolio management
- Risk analysis
- Deep learning models
- Real-time market updates
- User authentication

---

## 👨‍💻 Author

**Chandan M**

If you found this project useful, consider giving it a ⭐ on GitHub.
