# House Price Prediction Using Machine Learning

## 1. Introduction

House prices depend on different factors, such as location, median income, house age, and the number of rooms. Predicting house prices manually can be difficult because many factors affect the final price.

In this project, I used Machine Learning to predict house prices using the California Housing dataset. I trained different models and compared their performance to find a suitable model for prediction.

## 2. Objectives

The main objectives of this project are:

- To predict house prices using Machine Learning.
- To understand and prepare the dataset.
- To train and compare different Machine Learning models.
- To evaluate model performance using suitable metrics.
- To identify the features that have the greatest influence on predictions.

## 3. Dataset Description

For this project, I used the California Housing dataset. It contains information about houses and their surrounding areas.

Some important features are:

- **Median Income:** Median income of people in the area.
- **Longitude and Latitude:** Geographical location.
- **Housing Median Age:** Median age of houses.
- **Total Rooms:** Total number of rooms.
- **Total Bedrooms:** Total number of bedrooms.
- **Population:** Population of the area.
- **Households:** Number of households.
- **Ocean Proximity:** Distance or location in relation to the ocean.

The target variable is `median_house_value`, which represents the median house value that the model predicts.

## 4. Tools and Technologies Used

The following tools and technologies were used:

- **Python:** Main programming language.
- **Pandas:** For data handling and preprocessing.
- **NumPy:** For numerical operations.
- **Matplotlib and Seaborn:** For data visualization.
- **Scikit-learn:** For training and evaluating Machine Learning models.
- **Jupyter Notebook:** For writing and executing the code.

## 5. Data Preprocessing

Before training the models, I prepared the dataset for analysis and prediction.

First, I checked the dataset and its features to understand the available information. I also checked for missing values and handled them where necessary.

The `ocean_proximity` column contains categorical values, so I converted it into numerical columns using one-hot encoding. This made the categorical information suitable for the Machine Learning models.

After preprocessing, I separated the input features (`X`) from the target variable (`y`).

### Train-Test Split

I divided the dataset into two parts using the `train_test_split()` function from Scikit-learn.

- **Training data: 80%** — used to train the model.
- **Testing data: 20%** — used to evaluate the model on data it had not seen during training.

I used `random_state=42` to make the split reproducible, assuming these values match the code used in my notebook.

## 6. Model Training and Hyperparameter Tuning

I used two Machine Learning algorithms for this project.

**Linear Regression:** This model is used to predict numerical values by learning the relationship between the input features and the target variable.

**Random Forest Regressor:** This model uses multiple decision trees and combines their predictions to produce a final result. It can learn more complex relationships in the data.

I compared the models and used `GridSearchCV` to tune the Random Forest model's hyperparameters.

The best parameters obtained were:

- `n_estimators = 200`
- `max_depth = None`
- `min_samples_split = 2`

These settings were selected through the hyperparameter-tuning process.

## 7. Model Evaluation

I evaluated the final model using three metrics: Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R² Score.

| Evaluation Metric | Result |
|---|---:|
| MAE | 31,629.47 |
| RMSE | 49,058.54 |
| R² Score | 0.816 |

**Mean Absolute Error (MAE):** It measures the average absolute difference between actual and predicted house prices.

**Root Mean Squared Error (RMSE):** It measures prediction errors while giving more weight to larger errors.

**R² Score:** It indicates how much of the variation in the target variable is explained by the model. The score of 0.816 means the model explains approximately 81.6% of the variation in house values in the test dataset.

These results indicate that the tuned Random Forest model performed reasonably well on the test data.

## 8. Actual vs. Predicted Price Visualization

I created a scatter plot to compare actual house prices with the prices predicted by the model.

The graph includes a red dashed line representing ideal predictions, where actual and predicted prices are equal. Points closer to this line indicate more accurate predictions, while points farther away represent larger prediction errors.

The graph helps me understand how closely the model's predictions match the actual house prices.

## 9. Feature Importance Analysis

I used feature importance to identify which input features contributed most to the Random Forest model's predictions.

The most important features were:

| Feature | Importance |
|---|---:|
| Median Income | 47.71% |
| Inland | 14.56% |
| Longitude | 9.86% |
| Latitude | 9.29% |
| Housing Median Age | 4.80% |

The results show that median income was the most important feature, followed by the inland indicator and geographical location.

This analysis helped me understand which features the model relied on most when predicting house prices. Feature importance shows the model's predictive reliance on features; it does not prove that a feature directly causes house prices to change.

## 10. Practical Applications

This type of house price prediction model can be useful in different situations.

- **Buyers:** It can help buyers estimate house prices before purchasing a property.
- **Sellers:** It can provide an approximate price for comparing properties before selling.
- **Real Estate Agents:** It can help agents analyse property information and guide clients.
- **Investors:** It can help investors study housing trends and compare properties.

The predictions are estimates and should not be treated as official property valuations.

## 11. Conclusion

In this project, I developed a House Price Prediction model using Machine Learning and the California Housing dataset. I learned how to preprocess data, convert categorical features into numerical form, split data into training and testing sets, train models, and evaluate their performance.

I compared Linear Regression and Random Forest Regressor and used GridSearchCV to tune the Random Forest model. The final model achieved an R² score of 0.816 on the test data.

I also used visualizations and feature importance analysis to understand the model's predictions and identify the most important features. Overall, this project helped me gain practical experience with data preprocessing, model training, evaluation, and visualization.

## 12. Future Improvements

In the future, I can improve this project by:

- Testing additional Machine Learning algorithms.
- Trying different hyperparameter combinations.
- Including more relevant housing features.
- Building a simple web application where users can enter house details and receive a predicted price.
- Improving the model's performance through further experimentation.
