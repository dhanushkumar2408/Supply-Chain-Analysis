# Supply-Chain-Analysis

 

## **Data Cleaning Process**

The data cleaning process was an essential step in preparing the dataset for analysis and modeling. Below are the steps performed during data cleaning:

### **1. Dropping Unwanted / Unnecessary Columns**
   - Removed columns that were irrelevant to the analysis or redundant. This reduced noise and improved computational efficiency.
   - Example: Columns like `Customer Password` or `Product Image` were dropped as they didn’t contribute to the analysis objectives.


### **2. Renaming Columns**
   - Standardized column names for better readability and uniformity.
   - Example:
     - Changed `Shipping date(DateOrders)` to `Shipping Date`.
     - Renamed `Order date (DateOrders)` to `Order Date`.

### **3. Changing Column Types**
   - **Date Conversion**:
     - Used `pd.to_datetime` to convert `Shipping Date`, `Order Date`, and other date-related columns into a standard datetime format.
     - Ensured consistency in date-time operations for further analysis.
   - **Integer to Object Conversion**:
     - Changed specific columns like `Order ID` or `Product Category ID` from `Integer` to `Object` type as they represented categorical data.

### **4. Merging with USA Holiday List**
   - Merged the primary dataset (Supply Chain dataset) with a USA holiday list to identify orders occurring on or near public holidays.
   - New columns derived:
     - `Is_Holiday`: Boolean column indicating if the order date coincided with a holiday.
     - Extracted date-related components:
       - `Month`, `Year`, `Day`, `Weekday`.
   - Filled null values in the holiday column with a placeholder string `'Non-Holiday'`.

![Screenshot 2024-11-16 121720](https://github.com/user-attachments/assets/291c05b4-4404-478d-8644-f1c9fa7c2b83)



---

## **Explratory Data Analysis**

### **1. Count of Positive & Negative Order Profits**
   Chart shows that the number of orders with positive profits is significantly higher than the 
   number of orders with negative profits. This suggests that the majority of orders are 
   generating profits for the business, while a smaller portion is resulting in losses.

   ![Screenshot 2024-11-16 125638](https://github.com/user-attachments/assets/d7f17bc8-51cc-4615-be51-27de71bab343)

  
![Screenshot 2024-11-16 140639](https://github.com/user-attachments/assets/dce10b16-e9d1-4a95-9a0c-cc535f7c0db3)


### **2. Positive & Negative Order Profits by Department**
   
- All departments have a higher proportion of positive order profits (green) compared to negative order profits (red), with the split being roughly 80% positive to 20% negative across departments.

- The Health and Beauty Outdoors department appears to have the highest proportion of negative order profits, while departments like Apparel and Book Shop have slightly lower proportions of negative profits.

- The relatively consistent ratio across all departments suggests this might be a systemic pattern rather than being specific to any particular product category or department.
![Screenshot 2024-11-16 125750](https://github.com/user-attachments/assets/aeca1a28-ef10-4213-b8fa-73e51d39d06d)

![Screenshot 2024-11-16 140722](https://github.com/user-attachments/assets/5ecaf1df-bf0e-468d-8663-54ae85766336)



### **3. Statistical Summary of "Order Profit Per Order"**

- **Total Data Points**: 180,519  
- **Mean (Average)**: $21.97  
- **Standard Deviation**: $104.43 (indicating significant variability in profit per order)  
- **Minimum Value**: -$4,274.98 (a substantial loss)  
- **Maximum Value**: $911.80 (highest profit recorded)  
- **Median (50th Percentile)**: $31.52 (half of the orders have profits below this amount)  
- **Interquartile Range (IQR)**:
  - **25th Percentile (Q1)**: $7.00
  - **75th Percentile (Q3)**: $64.80
  ![Screenshot 2024-11-16 125826](https://github.com/user-attachments/assets/063902e5-712c-4aa0-9d46-3bdd5e1ca640)


### **4. Distribution of Discount Rates**
  The histogram shows that most items in the dataset receive discount rates of 0%, 5%, and 15%, indicating these are the most commonly used discount levels. Higher discount rates like 20% and 25% are applied less frequently.
  
![Screenshot 2024-11-16 130203](https://github.com/user-attachments/assets/adb496f9-7400-483d-aceb-9ac5f90e8237)

![Screenshot 2024-11-16 140756](https://github.com/user-attachments/assets/88fd26fa-cd18-4084-b40b-add3e326f850)

### **5. Average Profit by Discount Rate**
Higher discounts (above 15%) lead to reduced average profit, which indicates that larger discounts may negatively impact profitability. Careful consideration is needed when offering high discounts.

![Screenshot 2024-11-16 130240](https://github.com/user-attachments/assets/f27352bc-04bf-45ed-bfcd-9a631e89d3dd)
![Screenshot 2024-11-16 140847](https://github.com/user-attachments/assets/48750177-9348-4421-962d-65543208cd45)

### **6. Heatmap of Correlation Matrix**
Discount rates have a negative correlation with profit, meaning higher discounts tend to reduce profitability. On the other hand, higher product prices and larger quantities positively affect sales and profit.


![Screenshot 2024-11-16 130306](https://github.com/user-attachments/assets/ac4a0f2a-7344-4e0d-8a4d-173b9955e6f6)

![Screenshot 2024-11-16 140931](https://github.com/user-attachments/assets/582f2d94-5a77-430b-b3a4-c7411fd933a2)


### **7. Largest Market by Order Count**
Latin America have biggest market ie number of orders are more
![Screenshot 2024-11-16 130334](https://github.com/user-attachments/assets/94b6ce10-a24b-4bd7-9e53-3426b3f68327)


### **8.Average Sales & Profit by Departmment**
   The two barplot shows Technology Department recorded high number of average sales , whereas Footwear recorded high average Total profit.

![Screenshot 2024-11-16 130409](https://github.com/user-attachments/assets/f60ce64c-58b4-4794-8371-86ebab1ab404)

![Screenshot 2024-11-16 141013](https://github.com/user-attachments/assets/b7e8144e-7ac1-4cba-aaf7-01a11e131905)
![Screenshot 2024-11-16 141023](https://github.com/user-attachments/assets/f1c6dc8e-ccde-4b8e-a6b4-e8e1b631cfc5)



### **9.Shipping Time Analysis**

### **Days for Shipping (Real) (Blue Box)**

- **Median**:  
  The median real shipping time is approximately **3 days**, represented by the line inside the blue box.  

- **Interquartile Range (IQR)**:  
  The blue box spans from **2 days** (25th percentile) to **5 days** (75th percentile), indicating that 50% of the shipments took between 2 and 5 days.  

- **Whiskers**:  
  The whiskers extend from **0 to 6 days**, meaning the total range of real shipping times varies from 0 to 6 days.  


### **Days for Shipment (Scheduled) (Orange Box)**

- **Median**:  
  The median scheduled shipping time is approximately **2 days**, represented by the line inside the orange box.  

- **Interquartile Range (IQR)**:  
  The orange box spans from **2 days** (25th percentile) to **4 days** (75th percentile), suggesting that the majority of scheduled shipments are expected to take between 2 and 4 days.  

- **Whiskers**:  
  The whiskers extend from **0 to 4 days**, indicating that scheduled shipments have a more condensed range compared to real shipping times.  


### **Findings**:

1. **Real vs. Scheduled Shipping**:  
   - Real shipping times generally take **longer on average** than scheduled shipping times.
   - The **median real shipping time (3 days)** exceeds the **median scheduled shipping time (2 days)**.  

2. **Variability**:  
   - There is **greater variability** in real shipping times compared to scheduled shipping times, as indicated by a wider IQR and whisker range for real shipping.  
   - This variability suggests potential **delays** in meeting scheduled shipping expectations.  


![Screenshot 2024-11-16 130458](https://github.com/user-attachments/assets/fb38b47d-94bd-4ae2-8f88-6c70dae68af4)

### **10.Customer Segment Distribution**
The Customer Segment Distribution shows that the "Consumer" segment has the highest number of customers, followed by "Corporate" and then "Home Office". This suggests that the majority of the customer base is individuals, while businesses and home offices make up smaller portions.

![Screenshot 2024-11-16 134611](https://github.com/user-attachments/assets/cc3d2622-1635-4f3c-8c7f-3eb2b378084e)

### **11.Monthly Sales Trend Over the Years**
The line plot shows the monthly sales trend from 2015 to 2018. Sales remained relatively stable across the first 9 months for all years, peaking around August. However, in 2018, there was a significant drop in sales in the last quarter (October to December), suggesting a potential issue or change in market dynamics during that period.

![Screenshot 2024-11-16 134742](https://github.com/user-attachments/assets/d5a03596-4681-45ee-ba06-f9b9d97f68c9)

### **12.Product Popularity by Category**
The Product Popularity by Category chart reveals that "Cleats" is the top-selling category, followed by "Women's Apparel" and "Indoor/Outdoor Games". This suggests that sports equipment, particularly footwear, is driving sales, while other categories, such as "Electronics" and "Camping & Hiking", have lower demand

![Screenshot 2024-11-16 134924](https://github.com/user-attachments/assets/26f5ce94-7f12-4ca2-8b3e-4013243fa7b6)

![Screenshot 2024-11-16 141231](https://github.com/user-attachments/assets/5cc8c150-7440-48ae-b148-6e104bbe8577)


### **13.Product vs Sales**
Plot shows a general trend of increasing sales with higher product prices. However, there are also some outliers with high prices and low sales, suggesting that price alone may not be the sole determinant of sales performance.
![Screenshot 2024-11-16 135107](https://github.com/user-attachments/assets/c0fde63c-a8e2-47be-9d9c-ff520deadd0e)


### **14.Total Sales & Profit by Market**
- Europe and LATAM have the highest sales values, followed by Pacific Asia.
- Africa and USCA have the lowest total sales and profits, indicating smaller market size or 
  demand.
- Total Profit Per Order is consistently lower than total sales in all regions, with Europe and LATAM showing the largest profit per order gaps.
![Screenshot 2024-11-16 135238](https://github.com/user-attachments/assets/ca27c310-10d5-4ebf-a044-760b29ff615d)

### **15.Pair Plot of Shipping Days, Sales, and Profit**
- There is no clear correlation between "Days for shipping (real)" and "Sales" or "Profit."

- A noticeable cluster shows most data points have low shipping days and low sales.
    
- High negative profit seems to be associated with low sales.


![Screenshot 2024-11-16 135638](https://github.com/user-attachments/assets/1296887a-78c2-485b-a541-47309fe27a95)

### **16.Average Profit by Discount Rate**

- Discounts between 4-6% lead to the highest average profits during holidays.

- Extremely low discount rates (0% or near 0%) result in negative profit, indicating discounts 
  are necessary for profitability.

- Discounts above 15% yield diminishing returns, with profits decreasing.

![Screenshot 2024-11-16 140418](https://github.com/user-attachments/assets/47dfe172-82a7-46e2-991c-ee3219ae3ee1)


![Screenshot 2024-11-16 141359](https://github.com/user-attachments/assets/3fb93e17-dfe5-448b-a108-df6dc244eddb)





# Random Forest Regressor Findings for Predicting Sales

### Model Overview
We used a **Random Forest Regressor** to identify the importance of various features in predicting sales. The model was trained with the following features:
- `Order Item Discount Rate`
- `Product Price`
- `Order Item Quantity`
- `Total Profit Per Order`

The target variable (`y`) was `Sales`.
![Screenshot 2024-11-16 191822](https://github.com/user-attachments/assets/ac6af898-9d25-464c-8cf4-c8e364ebb5af)



### **Feature Importance Analysis**

Using the trained Random Forest model, the importance of each feature was calculated, and the results are summarized below:

#### **1. Product Price**
- **Importance Score**: Close to **0.8**.
- **Insights**: This feature is the most critical factor for predicting sales. It highlights that the price of a product has a substantial impact on the sales volume or revenue.

#### **2. Order Item Quantity**
- **Importance Score**: Around **0.2**.
- **Insights**: The quantity of items ordered is the second most significant feature. While it contributes to sales predictions, its influence is notably less than that of the product price.

#### **3. Order Item Discount Rate**
- **Importance Score**: Relatively low.
- **Insights**: Discounts on items have a limited impact on predicting sales in this dataset. Although discounts may affect consumer behavior in some contexts, their predictive power here is minimal.

#### **4. Total Profit Per Order**
- **Importance Score**: Almost negligible.
- **Insights**: Profit margins seem to have little to no influence on predicting sales. This suggests that the sales volume is not directly tied to profitability for individual orders in this dataset.



### **Visual Representation**

Below is a bar plot showcasing the feature importance:


![Screenshot 2024-11-16 183740](https://github.com/user-attachments/assets/e6d85416-358c-4f2e-9201-22bd655bd24b)


### **Key Takeaways**
- **Product Price** is the dominant driver of sales predictions.
- **Order Item Quantity** also plays a role, but to a lesser extent.
- **Order Item Discount Rate** and **Total Profit Per Order** have minimal influence on the model, indicating they may not be critical factors for predicting sales in this context.

### **Recommendations**
- Focus on optimizing product pricing strategies, as they have the most significant impact on sales.
- Consider analyzing the role of discounts and profits further, especially in cases where these features might affect specific customer segments or categories.

---
# Multiple Linear Regression Findings for Predicting Sales

### **Model Overview**
We developed a **Multiple Linear Regression** model to predict `Sales` using the following features:
- `Days for shipping (real)`
- `Days for shipment (scheduled)`
- `Product Price`
- `Order Item Quantity`
![Screenshot 2024-11-16 192413](https://github.com/user-attachments/assets/c02eac9b-81e5-4169-aaf8-00779ad5269c)


The model's performance was evaluated on a test dataset using **Mean Squared Error (MSE)** and **R-squared (R²)** metrics.


### **Performance Metrics**

#### **1. Mean Squared Error (MSE): 1312.08**
- **Definition**: MSE measures the average squared difference between actual values and predicted values.
- **Interpretation**:  
  - An MSE of **1312.08** indicates the average squared deviation between the predicted sales and the actual sales is 1312.08 units.  
  - While this value suggests how far off predictions are on average, its scale depends on the target variable, so it is often challenging to interpret MSE in isolation.  
  - A lower MSE is desirable, as it signifies better prediction accuracy.

#### **2. R-squared (R²): 0.924**
- **Definition**: R² represents the proportion of variance in the dependent variable (`Sales`) explained by the independent variables.
- **Interpretation**:  
  - An R² of **0.924** means that **92.4%** of the variance in `Sales` is explained by the predictors (`Days for shipping (real)`, `Days for shipment (scheduled)`, `Product Price`, and `Order Item Quantity`).  
  - This is an excellent fit, as it indicates the model explains most of the variability in the sales data.  
  - The closer R² is to 1, the better the model explains the variability in the target variable.
 
 
### **Insights**
- **High R²** suggests the linear model captures a significant portion of the relationship between the features and `Sales`. 
- However, the **MSE** indicates there is still room to improve the model's predictive accuracy, especially when dealing with large variations in sales values.


### **Key Recommendations**
- **Feature Engineering**: Explore additional predictors (e.g., seasonality, region, or customer-specific factors) that might further improve predictions.
- **Residual Analysis**: Analyze residuals to check for patterns, outliers, or assumptions violations, such as non-linearity or heteroscedasticity.
- **Model Comparison**: Compare this linear regression model with other algorithms (e.g., Random Forest, Gradient Boosting) to assess if non-linear models perform better on this dataset.

### **Conclusion**
The high R² value demonstrates that the model fits the data well, while the MSE suggests prediction errors could be optimized further. This linear regression provides a strong baseline for sales prediction.

---

# Logistic Regression Findings for Predicting Late Delivery Risk

### **MODEL 1 - lOGISTIC REGRESSION**

### **Model Overview**
We developed a **Logistic Regression** model to predict whether a delivery would be late (`Late_delivery_risk`) using the following features:
- `Days for shipping (real)`
- `Days for shipment (scheduled)`
- `Sales per customer`


The model's performance was evaluated on a test dataset using accuracy, confusion matrix, and classification metrics.
![Screenshot 2024-11-16 192006](https://github.com/user-attachments/assets/a770cd99-edac-426b-9de5-e8a68674ce64)


### **Performance Metrics**

#### **1. Accuracy: 97.5%**
- **Definition**: Accuracy measures the proportion of correctly classified instances among the total instances.
- **Interpretation**:  
  - An accuracy of **97.5%** indicates the model correctly predicted the delivery status (on-time or late) for 97.5% of the test data.  
  - This high accuracy suggests the model performs well in predicting late delivery risk.

#### **2. Confusion Matrix**:
|                  | **Predicted: No Late** | **Predicted: Late** |
|------------------|-------------------------|----------------------|
| **Actual: No Late** | 15,399 (True Negatives) | 908 (False Positives)  |
| **Actual: Late**    | 0 (False Negatives)      | 19,797 (True Positives) |

- **True Negatives (15,399)**: Correctly predicted on-time deliveries.  
- **False Positives (908)**: On-time deliveries incorrectly predicted as late.  
- **True Positives (19,797)**: Correctly predicted late deliveries.  
- **False Negatives (0)**: No late deliveries were missed.  


### **Classification Metrics**

| Metric        | On-Time Delivery | Late Delivery |
|---------------|------------------|---------------|
| **Precision** | 96%              | 98%           |
| **Recall**    | 100%             | 96%           |
| **F1-Score**  | 97%              | 97%           |

#### **Key Insights**:
- **Precision**: Out of all predicted late deliveries, **96%** were correct. This reflects how often the model is accurate when predicting a late delivery.  
- **Recall**: The model identified **100%** of actual late deliveries, meaning it detected all instances of late deliveries (no false negatives).  
- **F1-Score**: The F1-score for both classes is high (97%), indicating a balance between precision and recall for both on-time and late deliveries.


### **Heatmap of Confusion Matrix**
A heatmap visualization of the confusion matrix shows the distribution of predictions and actual values:
- **True Negatives (15,399)** and **True Positives (19,797)** dominate the matrix, highlighting the model's accuracy.
- The small number of **False Positives (908)** indicates occasional overestimation of late deliveries.
  
![Screenshot 2024-11-16 184531](https://github.com/user-attachments/assets/0705a232-ab33-4ceb-8042-ba3cc5038a8f)

### **Imbalance Handling**
Despite a potential class imbalance (more late deliveries than on-time), the model performs exceptionally well:
- It maintains high precision and recall for both classes.
- The model's ability to handle imbalance is evidenced by its high F1-scores (97% for both classes).


### **Recommendations**
- **Feature Expansion**: Consider including additional predictors (e.g., region, shipping mode, or seasonality) to improve performance further.
- **Threshold Tuning**: Experiment with adjusting the logistic regression decision threshold to balance precision and recall better if priorities shift (e.g., fewer false positives or higher sensitivity to late deliveries).
- **Comparison**: Evaluate other classification models (e.g., Random Forest, Gradient Boosting) for potentially better performance.

### **Conclusion**
The logistic regression model demonstrates excellent predictive performance, with high accuracy, precision, recall, and F1-scores. It effectively identifies late deliveries with no false negatives, making it reliable for risk assessment.


---
# Random Forest Findings for Predicting Late Delivery Risk

### **MODEL-2 RANDOM FOREST**

### **Model Overview**
We employed a **Random Forest Classifier** to predict whether a delivery would be late (`Late_delivery_risk`) using the following features:
- `Days for shipping (real)`
- `Days for shipment (scheduled)`
- `Sales per customer`

![Screenshot 2024-11-16 192050](https://github.com/user-attachments/assets/45db6f9b-39f5-4209-b0a4-b864ab34e8e3)


The model's performance was evaluated on a test dataset using accuracy, confusion matrix, and classification metrics.


### **Performance Metrics**

#### **1. Accuracy: 97.3%**
- **Definition**: Accuracy measures the proportion of correctly classified instances among the total instances.
- **Interpretation**:  
  - An accuracy of **97.3%** indicates the model correctly predicted the delivery status (on-time or late) for 97.3% of the test data.  
  - This high accuracy demonstrates the model's ability to handle this classification task effectively.


#### **2. Confusion Matrix**
|                  | **Predicted: No Late** | **Predicted: Late** |
|------------------|-------------------------|----------------------|
| **Actual: No Late** | 15,405 (True Negatives) | 902 (False Positives)  |
| **Actual: Late**    | 73 (False Negatives)      | 19,724 (True Positives) |

- **True Negatives (15,405)**: Correctly predicted on-time deliveries.  
- **False Positives (902)**: On-time deliveries incorrectly predicted as late.  
- **True Positives (19,724)**: Correctly predicted late deliveries.  
- **False Negatives (73)**: Late deliveries missed by the model.  


### **Classification Metrics**

| Metric        | On-Time Delivery | Late Delivery |
|---------------|------------------|---------------|
| **Precision** | 96%              | 98%           |
| **Recall**    | 99%              | 96%           |
| **F1-Score**  | 97%              | 97%           |

#### **Key Insights**:
- **Precision**: Out of all predicted late deliveries, **96%** were correct, indicating the model has good precision in identifying late deliveries.  
- **Recall**: The model successfully identified **96%** of actual late deliveries, missing only 73 instances.  
- **F1-Score**: Balanced F1-scores (97% for both classes) reflect the model's robustness in managing class imbalance.


### **Confusion Matrix Heatmap**
A heatmap visualization of the confusion matrix shows:
- High counts of **True Negatives (15,405)** and **True Positives (19,724)** dominate the matrix.
- **False Positives (902)** and **False Negatives (73)** are minimal, highlighting the model's effectiveness.

![Screenshot 2024-11-16 190734](https://github.com/user-attachments/assets/b5b33875-2e82-419f-9f89-91262f78e278)


### **Imbalance Handling**
- The Random Forest model handles class imbalance well, maintaining high precision, recall, and F1-scores for both classes.  
- It effectively predicts both late and on-time deliveries with minimal errors.


### **Comparison to Logistic Regression**
- Both Logistic Regression and Random Forest achieved similar high accuracy, but **Random Forest offers slightly better robustness** in feature importance and adaptability.
- Random Forest's performance can be further optimized with hyperparameter tuning (e.g., adjusting the number of trees, depth, or sampling strategy).


### **Recommendations**
- **Feature Exploration**: Incorporate additional features (e.g., customer location, shipping mode, or order region) to enhance predictive power.
- **Hyperparameter Tuning**: Experiment with `n_estimators`, `max_depth`, and `min_samples_split` to potentially improve the model's performance.
- **Comparison with Other Models**: Evaluate Gradient Boosting or XGBoost for further insights into model efficiency.

### **Conclusion**
The Random Forest model demonstrates excellent predictive performance, achieving an accuracy of **97.3%**. Its high precision, recall, and F1-scores indicate it is highly reliable for predicting late delivery risks.

 ---
 # Model Comparison: Logistic Regression vs. Random Forest for Late Delivery Risk Prediction


### **Overview**

We evaluated two models for predicting late delivery risks:
1. **Model 1**: Logistic Regression
2. **Model 2**: Random Forest Classifier


### **Performance Metrics Comparison**

| Metric            | **Model 1 (Logistic Regression)** | **Model 2 (Random Forest)** |
|-------------------|-----------------------------------|----------------------------|
| **Accuracy**      | **97.5%**                        | 97.3%                     |
| **Precision**     | 96%                              | 96%                       |
| **Recall**        | **100%**                         | 96%                       |
| **F1-Score**      | 0.98                             | 0.98                      |
| **True Positives**| **19,797**                       | 19,724                    |
| **False Negatives**| **0**                           | 73                        |


### **Key Observations**

1. **Accuracy**:  
   - Model 1 has a slightly higher accuracy (**97.5%**) than Model 2 (**97.3%**).

2. **Recall**:  
   - **Model 1 (Logistic Regression)** achieved a perfect recall (100%) for late deliveries, meaning it identified all true late deliveries without any false negatives.  
   - **Model 2 (Random Forest)** missed **73 late deliveries**.

3. **Precision and F1-Score**:  
   - Both models have the same **precision (96%)** and **F1-score (0.98)**, indicating similar performance in handling class imbalance.

4. **Overall Performance**:  
   - While both models are strong performers, **Model 1's flawless recall makes it more suitable for critical applications where missing late deliveries has severe consequences**.


### **Conclusion**

**Model 1 (Logistic Regression)** is the better choice for predicting late delivery risks:
- It has a higher accuracy.
- Achieves perfect recall, ensuring no late deliveries are missed.
- Provides similar precision and F1-scores compared to Model 2.

**Recommendation**: Use Model 1 if identifying all late deliveries is crucial. Consider Model 2 if interpretability or robustness to new features is needed.

---

# Analysis of Total Profit Per Order using OLS Regression



### **Findings**

#### **Model Summary**
The Ordinary Least Squares (OLS) regression model evaluates the relationship between **Total Profit Per Order** and three independent variables:
1. **Order Item Discount Rate**
2. **Product Price**
3. **Order Item Quantity**
![Screenshot 2024-11-16 192135](https://github.com/user-attachments/assets/47338995-396e-492e-922c-bb1259cd220f)


### **Key Metrics**
- **R-squared**: **26%**
  - This indicates that 26% of the variation in 'Total Profit Per Order' is explained by the independent variables in the model. While this is relatively low, it suggests that other factors not included in the model also influence total profit.


### **Independent Variables and Coefficients**

1. **Order Item Discount Rate**:
   - **Coefficient**: **-65.2753**
   - **Interpretation**: For every unit increase in the discount rate (e.g., 100% increase), the **Total Profit Per Order decreases by 65.2753 units** on average, holding other variables constant.
   - **Statistical Significance**: The coefficient is statistically significant (**p-value < 0.05**), meaning the relationship is unlikely due to chance.

2. **Product Price**:
   - **Coefficient**: **0.1393**
   - **Interpretation**: For every 1-unit increase in product price, the **Total Profit Per Order increases by 0.1393 units** on average, holding other variables constant.
   - **Statistical Significance**: The coefficient is statistically significant (**p-value < 0.05**), suggesting a strong positive correlation.

3. **Order Item Quantity**:
   - **Coefficient**: **34.7414**
   - **Interpretation**: For every additional item sold, the **Total Profit Per Order increases by 34.7414 units** on average, holding other variables constant.
   - **Statistical Significance**: The coefficient is statistically significant (**p-value < 0.05**), demonstrating a strong positive correlation.


### **Conclusion**

- **Order Item Discount Rate** has a significant **negative impact** on Total Profit Per Order. Strategies to minimize excessive discounts could help improve profitability.
- **Product Price** and **Order Item Quantity** both have a significant **positive impact** on Total Profit Per Order. This highlights the importance of pricing strategy and increasing sales volume to drive profitability.
- The relatively low **R-squared (26%)** suggests that other factors not included in this model play a significant role in determining total profit.


### **Recommendations**
1. **Review discounting policies** to balance competitive pricing with profitability.
2. **Optimize product pricing** to maximize profit margins while maintaining sales volume.
3. Focus on **increasing order quantities** through promotional bundles or volume discounts.

---









