# Credit Card Fraud Detection

## Project Overview

This project focuses on detecting fraudulent credit card transactions using machine learning techniques. It leverages data preprocessing, anomaly detection (Isolation Forest), supervised learning with XGBoost, and oversampling (SMOTE) to handle class imbalance. The model is wrapped in a user-friendly Streamlit web app that allows batch or manual entry transaction predictions.

## Dataset

- The dataset used is the [Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) from Kaggle.
- Contains anonymized transactions made by European cardholders over two days in 2013.
- Imbalanced dataset with a small fraction of fraud transactions.
- Features include 28 PCA principal components, `Time`, `Amount`, and target variable `Class` (0 = non-fraud, 1 = fraud).

## Key Features

- Data cleaning and feature scaling (StandardScaler).
- Class balancing using SMOTE oversampling.
- Unsupervised anomaly detection via Isolation Forest.
- Supervised classification with XGBoost.
- Performance evaluation using confusion matrix, classification report, ROC curve, and AUC.
- Deployment as an interactive Streamlit app enabling:
  - CSV upload for batch prediction.
  - Manual transaction input.

## Project Structure

├── app.py # Streamlit web app for prediction and UI
├── creditcard.csv # Kaggle dataset (not included due to size)
├── xgb_fraud_model.pkl # Serialized trained XGBoost model
├── amount_time_scaler.pkl # Serialized scaler for 'Time' and 'Amount'
├── notebook.ipynb # Jupyter notebook containing EDA, modeling, and evaluation
├── requirements.txt # Dependencies to install Python packages
└── README.md # This file

text

## Installation & Setup

1. Clone this repository:
git clone https://github.com/yourusername/credit-card-fraud-detection.git
cd credit-card-fraud-detection

text

2. Install dependencies:
pip install -r requirements.txt

text

3. Download the dataset from Kaggle and place `creditcard.csv` inside the project folder (optional if using pre-trained model only).

4. (Optional) Explore and retrain models through `notebook.ipynb`.

## Running the Streamlit App

Launch the web app locally with the following command:

streamlit run app.py

text

The app allows you to:

- Upload a CSV file with credit card transactions for batch fraud prediction.
- Manually input transaction features to get real-time fraud predictions.

Access the app in your browser at `http://localhost:8501`.

## Sample Input for Manual Prediction

| Feature | Example Value |
|---------|---------------|
| Time    | 50000         |
| V1      | -1.25         |
| V2      | 2.35          |
| ...     | ...           |
| Amount  | 150.75        |

(The app internally scales 'Time' and 'Amount' before prediction.)

For batch prediction, you can use the included `sample_transactions.csv` with the correct column format.

## Future Improvements

- Hyperparameter tuning for improved accuracy.
- Addition of alternative supervised and unsupervised algorithms.
- Enhanced interpretability and visualization features.
- Cloud deployment with continuous monitoring and alerts.
- Real-time integration with transactional systems.

## License

This project is for educational and demonstration purposes only. Dataset usage is subject to Kaggle's terms and conditions.

---

*Feel free to customize this README further with screenshots, badges, or contributor info.*  
If you need help generating a `requirements.txt` or other documentation files, let me know!