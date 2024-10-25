# Supply-Chain-Analysis


### 1. **Data Cleaning**
   - The notebook performs data cleaning by renaming certain columns and converting relevant columns (e.g., shipping date, order date) into the correct formats.
   - **Analysis**: This step ensures that the dataset is prepped for analysis. It's essential to ensure that categorical data is properly encoded and dates are treated as datetime objects.

### 2. **Exploratory Data Analysis (EDA)**
   - **EDA with Visualizations**: From the next few cells, you perform EDA using `matplotlib` and `seaborn`. These libraries are used to plot distributions, correlations, and patterns within the data.
   - **Analysis**: Make sure to visualize the relationship between different features, like sales, profit, and delivery time. This helps in understanding key business insights such as profit drivers and delivery efficiency.

### 3. **OLS Model for Total Profit per Order**
   - The OLS (Ordinary Least Squares) regression model was developed to predict **Total Profit per Order**.
   - **Analysis**: Check the statistical significance of variables in this model. You may have considered factors such as order size, customer location, and category. This helps in identifying which factors most affect profit margins.

### 4. **OLS and Random Forest Regression for Sales Prediction**
   - For predicting **Sales**, you compared the performance of OLS regression against a Random Forest model.
     - The Random Forest model was identified as more significant and accurate.
   - **Analysis**: Random Forest typically performs better on complex, non-linear datasets. Consider analyzing feature importance within this model to see what factors most contribute to predicting sales.

### 5. **Multiple Regression for Sales Prediction**
   - You also developed a multiple regression model for sales prediction, which could indicate how individual predictors interact in a linear fashion to affect sales.
   - **Analysis**: The interpretation of coefficients here can provide direct business insights on how specific variables influence sales in a linear relationship.

### 6. **Logistic Regression and Random Forest for Late Delivery Risk**
   - **Logistic Regression** was significant for predicting the risk of late deliveries, while a **Random Forest** model was also developed.
   - **Analysis**: Logistic regression can provide probabilities for whether a delivery will be late or not, based on key features like distance, customer location, or shipping mode. The Random Forest model might capture more complex interactions that are useful for identifying patterns of late delivery.

### Conclusion:
Your project covers a comprehensive set of analyses for the supply chain dataset, including data cleaning, EDA, and building predictive models for profit, sales, and delivery risks. Here are some suggestions to enhance your report:
- **Model Performance**: Include metrics like R-squared, RMSE (Root Mean Square Error) for regression models, and accuracy, precision, or AUC for classification models like logistic regression.
- **Feature Importance**: Especially for Random Forest models, analyzing feature importance can give further insights into which variables are most critical for predictions.
- **Residual Analysis**: Perform residual analysis for your OLS models to ensure the assumptions of linear regression hold (e.g., homoscedasticity, normality of residuals).

