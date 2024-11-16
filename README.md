# Supply-Chain-Analysis



### **Data Cleaning**

The data cleaning process focused on preparing the dataset for analysis and modeling. Key steps included:

1. **Handling Missing Values**:
   - Missing values were identified in specific columns. Strategies to handle these included imputation with mean/median values for numerical columns and mode for categorical columns.
   - Dropped rows or columns with excessive missing values.

2. **Data Type Conversion**:
   - Converted columns like `TotalCharges` (which were strings due to data entry issues) to numerical data types.
   - Used `pd.to_datetime()` to convert date columns into a standard format.

3. **Outlier Detection and Removal**:
   - Outliers were detected using methods like the IQR method or visualizations (boxplots).
   - Removed or capped outliers in columns such as `Order Item Profit Ratio`.

4. **Column Standardization**:
   - Renamed columns to have consistent and readable names.
   - Removed any irrelevant or duplicate columns that didn't add value to the analysis.

---

### **Exploratory Data Analysis (EDA)**

The EDA was thorough and used a combination of visualizations and descriptive statistics:

1. **Univariate Analysis**:
   - Plots like histograms and boxplots were used to analyze the distribution of features such as `Sales`, `Profit`, and `Order Quantity`.
   - Found skewness in variables and applied transformations where necessary.

2. **Bivariate and Multivariate Analysis**:
   - **Correlation Heatmap**:
     - Identified strong positive/negative correlations between numerical variables.
     - For example, `Sales` was strongly correlated with `Order Item Quantity` and `Order Profit`.
   - **Pairplots**:
     - Explored relationships between multiple numerical variables.
     - Observed clusters indicating potential patterns in the data.

3. **Categorical Analysis**:
   - Bar charts were used to compare categories like `Shipping Mode` and `Order Status` with `Sales` and `Profit`.
   - Found that certain categories had higher instances of late delivery risk.

4. **Time Series Analysis**:
   - Aggregated data by `Order Date` to visualize trends in sales over time.
   - Detected seasonal patterns and anomalies in sales.

---

### **Modeling**

#### **Statsmodels**
1. **OLS Regression for Profit and Sales Prediction**:
   - Developed models to predict `Order Profit Per Order` and `Sales`.
   - Key Metrics:
     - R-squared values were evaluated to determine model fit.
     - P-values were used to assess feature significance.
   - Observed multicollinearity in some variables; VIF (Variance Inflation Factor) was calculated to address this.

2. **Interpretation**:
   - Coefficients of the model highlighted the impact of variables like `Order Item Discount` and `Product Price` on `Profit`.

---

#### **Scikit-learn**
1. **Logistic Regression for Late Delivery Risk**:
   - Target variable: `Late_delivery_risk`.
   - Steps:
     - Split data into train-test sets using `train_test_split`.
     - Scaled features with `StandardScaler`.
   - Metrics:
     - Confusion matrix, accuracy score, precision, recall, and F1-score were evaluated.
     - ROC curve was plotted to assess model performance.

2. **Random Forest for Sales Prediction**:
   - Performed feature importance analysis to identify critical predictors of sales.
   - Tuned hyperparameters using grid search.

3. **Comparative Analysis**:
   - Logistic Regression performed better in predicting late delivery risk compared to other models in terms of interpretability.
   - Random Forest outperformed OLS regression in predicting sales due to its ability to capture non-linear relationships.

---


