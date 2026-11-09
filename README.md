# Taxi Price Predictor

A machine learning app that predicts the price of a taxi trip from distance, time of day, weather, traffic and other factors. The model is served through a FastAPI backend and used from a Streamlit frontend.

<img width="1481" height="787" alt="Taxi Price Predictor" src="https://github.com/user-attachments/assets/4f8dd3a8-c513-4c00-89e4-98a9c2cf12a9" />

## How it works

1. **Data preparation:** cleaned and explored the taxi trip dataset (`model_development/eda.ipynb`)
2. **Model training:** compared regression models and picked a Random Forest, evaluated with MAE and RMSE (`model_development/model_dev.ipynb`)
3. **API:** FastAPI serves predictions from the saved model and scaler, with input validation through Pydantic
4. **Frontend:** Streamlit app where you fill in trip details and get a price back

## Tech stack

Python · scikit-learn · Pandas · FastAPI · Pydantic · Streamlit · joblib

## Run it

```bash
pip install -r requirements.txt

# Start the API (http://localhost:8000)
python -m uvicorn taxipred.backend.api:app --reload --app-dir src

# Start the frontend (http://localhost:8501)
streamlit run src/taxipred/frontend/app.py
```

## Project structure

```text
src/taxipred/
├── backend/            # FastAPI app and data processing
├── frontend/           # Streamlit app
├── model_development/  # EDA and model training notebooks
├── data/               # Dataset, trained model and scaler
└── utils/              # Paths and constants
```
