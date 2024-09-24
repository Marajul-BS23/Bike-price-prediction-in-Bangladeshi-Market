# Predicting Used Motorcycle Prices in Bangladesh: A Machine Learning Approach

# Predicting Used Motorcycle Prices in Bangladesh: A Machine Learning Approach

## Introduction

The used motorcycle market in Bangladesh is vibrant and dynamic, with a wide variety of bikes available at different price points. However, determining the fair price of a used bike can be challenging for both buyers and sellers. This research aims to address this challenge by developing a machine learning model to predict the prices of used motorcycles based on their attributes. The dataset for this analysis was collected by scraping listings from the popular online marketplace, bikroy.com.

## Data Collection Methodology

The data collection process involved web scraping techniques to extract relevant information from bike listings on bikroy.com. Custom Python functions were developed to navigate the website's structure, retrieve details like bike attributes and prices, and store them in a structured format.

### Data Collection Pipeline:

```scss
                   +-------------------+
                   |  Target Website   |     bikroy.com
                   +-------------------+
                              |
                              v
                   +-------------------+
                   | URL Extraction    |     store_url
                   +-------------------+
                              |
                              v
                   +-------------------+
                   | Data Extraction   |     (store_data)
                   +-------------------+
                              |
                              v
                   +-------------------+
                   | Data Storage      |     CSV file
                   +-------------------+
```

## Methodology

The research followed a systematic approach to predict used motorcycle prices, as outlined below:

```sql

                   +-------------------+
                   | Data Collection   |  (Web scraping from bikroy.com)
                   +-------------------+
                              |
                              v
                   +-------------------+
                   | Data Preprocessing|  (Handling missing values, encoding, scaling)
                   +-------------------+
                              |
                              v
                   +-------------------+
                   | Model Building    |  (KNN, Random Forest, XGBoost, Lasso)
                   +-------------------+
                              |
                              v
                   +-------------------+
                   | Model Evaluation  |  (Cross-validation, performance metrics)
                   +-------------------+
                              |
                              v
                   +-------------------+
                   | Feature Importance|  (Identifying key price predictors)
                   +-------------------+
```

### Data Preprocessing

1. **Handling Missing Values:** Missing values were addressed either through imputation or removing rows with missing data.
2. **One-Hot Encoding:** Categorical variables like `brand_model` were converted into numerical format using one-hot encoding.
3. **Feature Scaling:** Numerical features such as `Engine capacity`, `Kilometers run`, and `Year of Manufacture` were scaled using `MinMaxScaler`.

## Results and Analysis

### Model Performance Comparison

The following models were evaluated using cross-validation and performance metrics like Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and R-squared (R²) score:

| Model | Test R² | Train R² | MAE | RMSE |
| --- | --- | --- | --- | --- |
| **XGBoost Regressor** | 0.929 | 0.974 | 15287.87 | 21765.50 |
| **Random Forest** | 0.911 | 0.984 | 16050.83 | 24440.93 |
| **KNN Regressor** | 0.882 | 0.951 | 17808.09 | 28166.34 |
| **Lasso Regressor** | 0.809 | 0.804 | 23695.73 | 35828.95 |
| **Linear & Huber** | Negative | Negative | High | Very High |
- **XGBoost Regressor:** Best performance, with a test R² score of 0.929.
- **Random Forest Regressor:** Close second, with a test R² score of 0.911.
- **KNN Regressor:** Reasonable performance with a test R² of 0.882.
- **Lasso Regressor:** Lowest performing model with a test R² of 0.809.
- **Linear and Huber Regressors:** Performed poorly, showing negative R² scores.

### Feature Importance

The Random Forest model identified the following features as the most important:

1. **Kilometers run**
2. **Engine capacity**
3. **Year of Manufacture**

These results align with market intuition, where lower mileage, larger engines, and newer bikes are expected to command higher prices.

## Visualizations

### Actual vs. Predicted Prices

A scatter plot was created to compare actual bike prices with those predicted by the Random Forest model. The close alignment of the points to the diagonal line suggests a good fit.

## Conclusion

This research demonstrates the potential of machine learning, particularly tree-based models like XGBoost and Random Forest, in predicting used bike prices in Bangladesh. The models effectively captured key relationships in the data, with `Kilometers run`, `Engine capacity`, and `Year of Manufacture` being the top price predictors.

## Further Considerations

1. **Hyperparameter Tuning:** Fine-tuning hyperparameters could lead to further improvement.
2. **Additional Features:** Including features like bike condition, location, and seller reputation could enhance model performance.
3. **Larger Dataset:** A more diverse and larger dataset would improve the generalizability of the models.
