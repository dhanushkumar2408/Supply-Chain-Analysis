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

### **2. Positive & Negative Order Profits by Department**
   
- All departments have a higher proportion of positive order profits (green) compared to negative order profits (red), with the split being roughly 80% positive to 20% negative across departments.

- The Health and Beauty Outdoors department appears to have the highest proportion of negative order profits, while departments like Apparel and Book Shop have slightly lower proportions of negative profits.

- The relatively consistent ratio across all departments suggests this might be a systemic pattern rather than being specific to any particular product category or department.


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

### **4. Distribution of Discount Rates**
  The histogram shows that most items in the dataset receive discount rates of 0%, 5%, and 15%, indicating these are the most commonly used discount levels. Higher discount rates like 20% and 25% are applied less frequently.

### **4. Average Profit by Discount Rate**
Higher discounts (above 15%) lead to reduced average profit, which indicates that larger discounts may negatively impact profitability. Careful consideration is needed when offering high discounts.

### **5. Heatmap of Correlation Matrix**
Discount rates have a negative correlation with profit, meaning higher discounts tend to reduce profitability. On the other hand, higher product prices and larger quantities positively affect sales and profit.

### **6. Largest Market by Order Count**
Latin America have biggest market ie number of orders are more

### **7.Average Sales & Profit by Departmment**
   The two barplot shows Technology Department recorded high number of average sales , whereas Footwear recorded high average Total profit.


### **8.Shipping Time Analysis**

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



--- 

Let me know if you'd like more details or additional sections written in Markdown!

  






---


