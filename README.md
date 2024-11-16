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


  







---


