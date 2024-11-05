# Customer-Data-Analysis
### Overview
The Customer Data Analysis aims to understand customer behavior, track subscription types, and identify patterns in cancellations and renewals. This analysis combines demographic segmentation with an examination of subscription trends.

---
*STEPS*
1. Excel Analysis
Objective: Performed an initial data exploration of customer demographics and subscription data.

Key Metrics Calculated:
- Customer Count by Region: Pivot table summarizing the total number of customers in each region.
- Subscription Types: Count of customers by subscription type to find the most popular subscription.
- Cancellation Trends: Identified recent cancellations by filtering customers who canceled within six months and some other insight
  
![CPivot 1](https://github.com/user-attachments/assets/682c8148-ea62-4b6b-9db1-bc39b4d56f29)

![CPivot 2](https://github.com/user-attachments/assets/bb229472-61ec-4381-906c-a9a0aa9414aa)

---

2. SQL Analysis
Objective: I used SQL to extract subscription insights and validate the Excel analysis results.

Key SQL Queries:
- Total Number of Customers per Region:
```sql
SELECT Region, COUNT(CustomerID) AS CustomerCount
FROM Customers
GROUP BY Region;
Most Popular Subscription Type by Customer Count:
```

```sql
SELECT SubscriptionType, COUNT(CustomerID) AS CustomerCount
FROM Subscriptions
GROUP BY SubscriptionType
ORDER BY CustomerCount DESC;
Subscription Cancellations within 6 Months:
```

```
sql
SELECT CustomerID, SubscriptionType
FROM Subscriptions
WHERE DATEDIFF(MONTH, SubscriptionStartDate, SubscriptionEndDate) <= 6;
Average Subscription Duration:
```

```
sql
SELECT AVG(DATEDIFF(MONTH, SubscriptionStartDate, SubscriptionEndDate)) AS AvgDurationMonths
FROM Subscriptions;
```
![CQuery1](https://github.com/user-attachments/assets/81b23370-2ec7-474a-a3f3-20bbbc6118a6)
![CQuery2](https://github.com/user-attachments/assets/7165f2a0-a4c7-4e7a-9982-948a2b7b23a0)
![CQuery3](https://github.com/user-attachments/assets/79bb0b4d-25bf-4cb4-816d-a87437dd13aa)
![CQuery4](https://github.com/user-attachments/assets/a75b82ad-c268-4f79-bcd5-a0e92f30da9a)
![CQuery5](https://github.com/user-attachments/assets/5752e1d7-d2d7-4c00-adac-03c0071bda1f)
![CQuery6](https://github.com/user-attachments/assets/c9bf676e-507d-4faa-9bf7-74806f81d71d)
![CQuery7](https://github.com/user-attachments/assets/722d7cec-6432-434c-83b9-16d9035d82db)
![CQuery8a](https://github.com/user-attachments/assets/1899e84a-b971-43f2-a110-a3f4edc9c26d)
![CQuery8b](https://github.com/user-attachments/assets/8f7c80fd-270c-4238-8337-1bd1cb7cf9fd)

---
3. PowerBI Dashboard
Objective: Visualize customer insights, including subscription trends, cancellations, and segments.

Dashboard Elements:
- Customer Demographics (Pie Chart for region and subscription type).
- Subscription Duration Distribution (Histogram).
- Cancellation Trends (Line Chart of cancellations over time).
- Active vs. Canceled Subscriptions (Donut Chart).
- 
<img width="580" alt="Screenshot 2024-11-05 203913" src="https://github.com/user-attachments/assets/21d34824-dbcf-4d95-9605-ab9c2dbbe38e">

---

The Customer Data Analysis uncovers significant insights, such as popular subscription types, demographic segmentation, and subscription trends. This information will therefore help to optimize marketing efforts, reduce cancellations, and enhance customer retention strategies.

#### The Final Power BI Dashboard
This consolidates both sales and customer insights into a comprehensive and interactive format. Users can analyze sales trends, product performance, and regional data for the retail store while exploring customer demographics, subscription patterns, and cancellation trends for the subscription service.

- Key Metrics and Visuals:
  - Monthly and regional sales performance.
  - Top products and customers.
  - Subscription and cancellation trends.

---
### In Conclusion
This project provides a robust analysis of both sales and customer data for a retail business. By leveraging Excel, SQL, and Power BI, we gained actionable insights into product performance, customer segmentation, and subscription behaviors. The final Power BI dashboard serves as a powerful tool for stakeholders to explore data, allowing them to make informed decisions to enhance sales strategies and improve customer engagement.
