# Exascale_ai_assignment

README.md — Intelligent Power Demand Forecasting
Overview
This project presents a complete pipeline to forecast 24-hour power demand (in 15-minute intervals) for three feeders: F1, F2, and F3. The forecasts are informed by:

Weather data (temperature, humidity, wind speed, cloud cover) fetched from OpenWeatherMap API

Holiday data specific to Dhanbad, Jharkhand

Time-based features like hour, day-of-week, weekend flags

The pipeline includes:

Real-time weather data integration

Holiday recognition

Forecasting via pre-trained Random Forest models

CSV output of 24-hour predictions

Optional backend + dashboard for visualization

Files
Exascale_assignment (1).ipynb – Main Jupyter notebook that:

Loads trained models

Fetches real-time weather

Integrates holiday info

Generates predictions

F1_132KV_PowerConsumption_rf_model.pkl, etc. – Pickle files for trained models (not included here)

holidays_jharkand.xlsx – Excel file with regional holidays

forecast_next_24_hours.csv – Output file with predictions for next 24 hours

README.md – You’re reading this!

Setup Instructions
Clone this repository or upload the notebook to Colab

Install required libraries (in Colab or local Jupyter):

bash
Copy
Edit
!pip install requests openpyxl joblib pandas
Place required files in appropriate paths:

Place the model .pkl files in the notebook's directory.

Place holidays_jharkand.xlsx in your Google Drive and mount it in Colab.

Set your API key
Replace the placeholder in:

python
Copy
Edit
api_key
with your OpenWeatherMap API key (you can get one free from openweathermap.org).

Running the Forecast
Open the notebook and run all cells. The notebook will:

Fetch the current weather for Dhanbad (23.7957, 86.4304)

Build a 24-hour future time index (96 blocks of 15 minutes each)

Load and apply the trained models to predict F1, F2, F3 demand

Save output as forecast_next_24_hours.csv

Sample output columns:

Datetime, Temperature, Humidity, WindSpeed, CloudCover

is_weekend, is_holiday

F1, F2, F3 – predicted power demand
