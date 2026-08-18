# Credit Card Fraud Detection

This repository contains a Streamlit-based fraud detection application for credit card transactions. The app uses a pre-trained LightGBM model to classify transactions as either legitimate or fraudulent.

## Project Files

- `app.py` - Streamlit application frontend for collecting transaction details and making fraud predictions.
- `Credit card dataset.csv` - Dataset used for model training and analysis (not required to run the app).
- `fraud_detection_model.jb` - Pre-trained LightGBM fraud detection model.
- `label_encoders.jb` - Saved label encoders used to transform categorical input fields.
- `requirements.txt` - Python dependencies required by the application.

## How It Works

The app collects transaction details from the user, including:

- Merchant name
- Category
- Transaction amount
- Customer latitude and longitude
- Merchant latitude and longitude
- Transaction hour, day, and month
- Gender
- Credit card number

It computes the geographic distance between the customer and merchant using `geopy`. Categorical data is encoded with saved label encoders, and the credit card number is hashed to derive a numeric feature.

The processed input is then passed to the pre-trained LightGBM model in `fraud_detection_model.jb`, which predicts whether the transaction is fraudulent.

## Installation

1. Create and activate a Python virtual environment.

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

2. Install dependencies.

```powershell
pip install -r requirements.txt
```

## Run the App

From the project root:

```powershell
streamlit run app.py
```

Then open the Streamlit URL shown in the terminal.

## Notes

- The app expects both `fraud_detection_model.jb` and `label_encoders.jb` to exist in the project folder.
- If you move the label encoder file, update the file path in `app.py`.
- The model is loaded with `joblib` and uses `LightGBM`.

## Dependencies

Key dependencies include:

- `streamlit`
- `pandas`

Here is the deployed link:
https://credit-card-fraud-detection-wgnrihytfbcoradgrgfldn.streamlit.app/
- `numpy`
- `joblib`
- `lightgbm`
- `geopy`

For the full dependency list, see `requirements.txt`.
