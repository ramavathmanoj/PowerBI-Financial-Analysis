# PowerBI-Financial-Analysis
A Power BI dashboard to analyze sales performance by region and time.
**Dataset**:  
- 1.125M units sold | $127.9M total sales  
- Key columns: Sales, Profit, Discount, Region, Product  

## 📸 Dashboard Preview  
![Dashboard Overview](<img width="960" height="464" alt="image 1" src="https://github.com/user-attachments/assets/205522b2-fae8-4bd4-a42a-0ff1075ae780" />)  

## 📌 Key Insights  
### 1. Sales by Country  
![Top Countries](<img width="960" height="465" alt="image 2" src="https://github.com/user-attachments/assets/65ba9e53-ca6b-4071-922b-31a4cd474ff8" />
)  
- **USA**: $51M sales (40% of total)  
- **Top 5**: USA, Canada, Germany, France, Mexico → 70% of revenue  

### 2. Discount Impact  
![Discount Analysis](<img width="960" height="472" alt="image3" src="https://github.com/user-attachments/assets/67b19d90-71f8-4793-b213-77f5366694e8" />
)  
- **Critical Threshold**: Discounts >25% reduce profits (r = -0.65)  
- **Velo**: Only product benefiting from discounts  

### **3. Product Trends** 
- **High-Profit Products**:  
  ```markdown
  | Product    | Revenue Share | Profit Margin |
  |------------|---------------|---------------|
  | Velo       | 22%           | 18%           |
  | Carretera  | 19%           | 15%           |
  
🛠️ Technical Implementation
Profit Margin = DIVIDE([Profit], [Sales], 0) * 100
Moving Avg (3mo) = 
    AVERAGEX(
        DATESINPERIOD('Date'[Date], LASTDATE('Date'[Date]), -90, DAY),
        [Sales]
    )


    Final Review observed from this solution:
Targeted Marketing: Focus on USA/Canada/Germany

Discount Strategy: Limit discounts to <20% for non-Velo products

Inventory Boost: Increase stock for Velo/Carretera in Q4
