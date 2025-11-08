# Sensor Drift Prediction

## Overview
This project aims to forecast calibration drift in low-cost metal oxide CO sensors deployed in an urban air quality monitoring network. The sensors measure pollutants such as CO, benzene, and nitrogen oxides (NOx). Calibration drift can lead to inaccurate readings, causing incorrect health advisories and regulatory issues. This project provides a predictive solution to detect sensor drift for CO in advance, enabling timely recalibration.

## Features
- Preprocessing of sensor data, including handling missing values and outliers.
- Feature engineering: temporal features (hour, day, month), lag features, and rolling window statistics.
- Target creation: `Recalibrate_Indicator`, a binary flag indicating when recalibration is needed.
- Machine learning models:
  - **Random Forest Classifier**
  - **XGBoost Classifier**
- Evaluation metrics include precision, recall, F1-score, accuracy, and confusion matrices.
- Designed for 6-hour ahead drift prediction to support predictive maintenance.

## Data
The dataset contains hourly measurements of pollutants from sensors and reference instruments, with environmental variables:

| Column | Description |
|--------|-------------|
| Date | Date of measurement (DD/MM/YYYY) |
| Time | Time of measurement (HH.MM.SS) |
| CO(GT) | True CO concentration (mg/m³) |
| PT08.S1(CO) | CO sensor reading |
| NMHC(GT) | True NMHC concentration (µg/m³) |
| C6H6(GT) | True benzene concentration (µg/m³) |
| PT08.S2(NMHC) | NMHC sensor reading |
| NOx(GT) | True NOx concentration (ppb) |
| PT08.S3(NOx) | NOx sensor reading |
| NO2(GT) | True NO2 concentration (µg/m³) |
| PT08.S4(NO2) | NO2 sensor reading |
| PT08.S5(O3) | O3 sensor reading |
| T | Temperature (°C) |
| RH | Relative humidity (%) |
| AH | Absolute humidity (g/m³) |

Dataset link: [UCI Air Quality Dataset](https://archive.ics.uci.edu/dataset/360/air+quality)

## Usage
1. Open the notebook in Google Colab.
2. Ensure the dataset is available in your Google Drive, and update the `path` variable in the notebook to point to the correct directory where the dataset is stored in your drive.
3. Run all cells to preprocess data, train models, and evaluate performance.
4. The models predict the `Recalibrate_Indicator` for each sensor reading, enabling proactive maintenance.

## Results
- Random Forest and XGBoost models provide predictions for sensor recalibration.
- Evaluation metrics such as accuracy, precision, recall, and F1-score indicate model performance on unseen test data.
