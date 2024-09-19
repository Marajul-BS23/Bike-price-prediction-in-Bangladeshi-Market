# Old Bike Price Prediction using Machine Learning

This project focuses on predicting the prices of second-hand bikes listed on *bikroy.com* using machine learning models. The dataset is scraped from the website and analyzed using various regression algorithms to build an accurate prediction model.

## Introduction
The resale value of used motorcycles can vary based on multiple factors such as brand, year of manufacture, engine capacity, and kilometers run. This project aims to predict the price of old motorcycles using machine learning, identifying the key features that influence the price. By leveraging different models, we aim to improve the accuracy of price prediction.

## Data Collection
The dataset was collected by scraping *bikroy.com*, a popular classifieds platform. Using Python’s `BeautifulSoup`, the following features were extracted for each motorcycle:
- **Brand**
- **Model**
- **Year of Manufacture**
- **Engine Capacity**
- **Kilometers Run**
- **Price**

The data was compiled into a CSV file for further processing.

## Methodology
We employed various machine learning algorithms to predict the bike prices:
1. **Linear Regression**: A basic regression technique that fits a line through the data points.
2. **Random Forest Regressor**: A tree-based ensemble method that averages multiple decision trees.
3. **XGBoost**: A boosting technique that improves accuracy by combining multiple weak learners.
4. **Support Vector Machine (SVM)**: A method that maximizes the margin between predicted and actual values.

The performance of each model was evaluated using the following metrics:
- **Root Mean Squared Error (RMSE)**
- **R-squared (R²)**

## Data Preprocessing
The following steps were taken to preprocess the data:
1. **Handling Missing Values**: Missing data points were filled or removed as appropriate.
2. **Normalization**: Numerical features such as engine capacity and kilometers run were normalized using Min-Max Scaling.
3. **Train-Test Split**: The dataset was split into training (80%) and testing (20%) sets for model evaluation.

## Feature Importance
Using the Random Forest model, the most important features affecting bike prices were identified as:
- **Engine Capacity**
- **Year of Manufacture**
- **Kilometers Run**
- **Brand**

Here’s a graphical representation of feature importance:

![Alt text](../image/bike.png)
