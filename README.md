🚲 Bike Rental Demand Prediction

📌 Project Overview

This project aims to predict the daily number of bike rentals based on weather, calendar, and historical usage data. The data comes from a bike-sharing system and includes features like temperature, humidity, wind, and day-of-week information. The project goal is to build a regression model that can explain and forecast rental demand accurately.

🛠️ Technologies & Tools

Python 3

Jupyter Notebook

Pandas, NumPy

scikit-learn

Matplotlib, Seaborn

📊 Dataset

Input file: cleaned_day_data_v2.csv

Observations: Daily data for the year 2011

Target variable: cnt (total number of bike rentals per day)

Key Features Used: temp, hum, windspeed, weathersit_encoded, weekdayt, holiday, workingday, One-hot encoded mnth (month)

Rolling averages of cnt (3-day and 7-day)

Interaction features like temp × weekdayt, humidity × workingday

🧪 Modeling Approach

Preprocessing:

Removed duplicate columns (e.g. season_fall.1, .2)

Converted holiday and season_* columns to integers

Applied get_dummies() to encode the month (mnth) without dropping any category



Feature Engineering:

cnt_rolling_3: 3-day rolling average of bike rentals

cnt_rolling_7: 7-day rolling average

temp_x_weekdayt: interaction of temperature and weekday

humidity_x_workingday: interaction of humidity and workingday



Models Trained:

Linear Regression

Random Forest Regressor

Gradient Boosting Regressor (with and without tuning)

Final: Gradient Boosting with feature engineering

🎯 Final Model Performance

Gradient Boosting + rolling averages + interactions

📈 R² Score: 0.895

📉 RMSE: ~648

✅ MSE: ~419,993

💡 Key Learnings

Feature engineering (rolling averages and interaction terms) dramatically improved model performance.

Raw models without temporal context underperformed (R² ≈ 0.56).

Model generalizes well without overfitting after careful tuning.


🚀 Next Steps

Add external weather data (e.g., precipitation, cloudiness)

Tune hyperparameters further using GridSearchCV

Deploy model as an API or Streamlit app



Project built iteratively with the help of a virtual assistant (Chat GPT)
