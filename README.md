# Blinkit Sales Analysis

This project explores the sales performance of 'Blinkit', an online grocery shopping store. The goal is to gain insights into various sales aspects, including product category performance, outlet behavior, and revenue generation patterns. By analyzing key metrics and trends, the project provides recommendations to optimize operations and sales strategies.

This analysis was performed using **Power BI**, leveraging its powerful visualization capabilities and DAX (Data Analysis Expressions) for KPI creation.

---

## TABLE OF CONTENT

- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Data Cleaning](#data-cleaning)
- [Analysis](#analysis)
- [Insights](#insights)
- [Recommendations](#recommendations)
- [Conclusion](#conclusion)

---

## PROJECT OVERVIEW

The primary objective of this project is to address the following questions:

- What is the total sales generated across different outlets?
- Which product categories and outlet types contribute the most to revenue?
- How does outlet size, location, and establishment year affect sales?
- What trends in sales performance can be observed, and what strategies can be recommended to improve revenue?

This analysis will assist in decision-making processes related to product offerings, store management, and marketing strategies to enhance sales performance.

---

## DATA SOURCE

The data was sourced from Kaggle.com, which offers a range of fictitious datasets for data projects. The dataset used for this analysis is in **CSV format** and consists of **12 columns** and **8523 rows**. It contains detailed records of grocery sales, including:

- **Product Information**: Item type, fat content, visibility, and weight.
- **Outlet Information**: Size, type, location, and establishment year.
- **Sales Metrics**: Individual sales records and customer ratings.

---

## DATA CLEANING

After importing the data into Power BI, I checked for discrepancies, starting with verifying that all **data types** were correct. I then used the column distribution and column quality features to look for any **duplicates** or **empty values**, and found none. However, I noticed an issue in the **'Item Fat Content'** column, where values were inconsistently entered as "Low Fat," "LF," "Regular," and "reg." Since "LF" and "reg" were meant to represent "Low Fat" and "Regular," respectively, I used the **Power Query Editor** to standardize the values by replacing "LF" with "Low Fat" and "reg" with "Regular."


---

## ANALYSIS

To address the key objectives of this project, I created KPI cards and visualization charts. These visuals offer a focused view of sales patterns, regional strengths, and customer preferences.

### KPI CARDS

I used **DAX measures** in Power BI to create these KPI cards, offering quick insights into key metrics like total sales, average transaction value, items sold, and customer ratings.

1. **Total Sales**: ($1M)
   
   The overall revenue generated from all items sold. I calculated the 'Total Sales' measure by **summing** all the values in the Sales column. It adds up the revenue generated from each transaction, providing the overall sales figure across all products and outlets. This measure is used in Power BI to display the total sales KPI card on the dashboard which gives a quick view of the company’s total income.

   ```dax
   Total Sales = SUM('BlinkIT Grocery Data'[Sales])
   ```

2. **Average Sales**: ($141)
  
   The average revenue per sale. I calculated the 'Average Sales' measure by taking the **mean** of all values in the Sales column. It provides insight into the typical revenue generated per transaction, helping to evaluate the average spending pattern of customers. This measure is used in Power BI to display the average sales KPI card on the dashboard.

   ```dax
   Avg Sales = AVERAGE('BlinkIT Grocery Data'[Sales])
   ```

3. **Number of Items**: (8523)

    The total count of different items sold. I calculated the 'No of Items' measure by **counting** the number of rows in the 'BlinkIT Grocery Data' table, it represents the total number of items or transactions recorded in the dataset. Each row corresponds to a specific product sold, helping to quantify the overall volume of transactions. This measure is used in Power BI to display the no of items KPI card on the dashboard.

   ```dax
   No of Items = COUNTROWS('BlinkIT Grocery Data')
   ```

4. **Average Rating**: (3.9)
  
   The average customer rating for items sold. I calculated the 'Average Rating' measure by taking the **mean** of all values in the Rating column. It provides insight into the overall customer satisfaction with the products sold. This measure is used in Power BI to display the average rating KPI card on the dashboard, helping monitor customer feedback and product performance.

   ```dax
   Avg Rating = AVERAGE('BlinkIT Grocery Data'[Rating])
   ```
<br>

### CHARTS

I created a **field metrics** group using the **measures** Total Sales, Avg Sales, No of Items, and Avg Rating. This helped me efficiently build visualization charts, such as bar charts, line charts, providing a comprehensive view of sales performance and customer satisfaction.

<br>

**1. Line Chart**  
- Sales by Establishment Year.
- I created a line chart to analyze the sales trend by outlet establishment year. This chart reveals how sales performance evolved over time, peaking around **2018**.

**2. Donut Chart** 
- Outlet Size Contribution.
- This chart shows the contribution of small, medium, and high-sized outlets to total sales. **Medium** outlets emerged as the highest contributors with **42.27%** of total sales.

**3. Stacked Bar Chart** 
- Outlet Location Performance.
- I used a stacked bar chart to compare sales across Tier 1, Tier 2, and Tier 3 locations. The chart shows that **Tier 3** locations contributed the most, generating **$472K** in revenue.

**4. Bar Chart**  
- Item Type Performance.
- This chart displays the performance of different product categories. **Fruits and Vegetables** generated the highest sales at **$178K**, closely followed by **Snack Foods** at **$175K**, while **Seafood** had the lowest contribution at **$9K**.

**5. Matrix** 
- Outlet and Product Summary.
- I created a matrix to show a **detailed summary** of sales metrics by outlet type. This matrix includes total sales, number of items, average sales, average rating, and item visibility, offering a comprehensive view of outlet-level performance.

**6. Donut Chart**  
- Fat Content Sales Breakdown.
- I used this chart to show the proportion of sales between Regular and Low-Fat items. **Low Fat** items dominate the sales, contributing **$776K** compared to **$425K** from **Regular** items.

<br>

<img width="878" alt="Blinkit Dashboard" src="https://github.com/user-attachments/assets/fef7f2ef-ae7d-470b-bcc6-ac74583cc2ec">

<br>
<br>

## INSIGHTS

1. **Total Sales Revenue**: The highest revenue is generated by **Supermarket Type1** outlets, making them the most profitable type.

2. **Average Sales per Outlet**: Outlets in **Tier 3** locations tend to perform better than those in other tiers, suggesting a higher demand in these regions.
   
3. **Sales by Product Category**: **Fruits and Vegetables** and **Snack Foods** are the leading product categories, indicating customer preference.
   
4. **Impact of Outlet Size**: **Medium-sized** outlets generate the highest sales, indicating an optimal size for operations.
   
5. **Sales Trends**: Sales have increased steadily over the years, with a significant spike after **2015**, reflecting potential business expansion or increased demand.
    
6. **Visibility Influence**: Items with moderate visibility tend to have higher sales, indicating that both over- and under-exposure can affect performance negatively.

---

## RECOMMENDATIONS

Based on the analysis, the following recommendations are suggested to improve Blinkit’s sales performance:

1. **Focus on Expanding Supermarket Type1 Outlets**: Given their strong performance, expanding this type of outlet could further boost revenue.

2. **Optimize Outlet Size for New Locations**: **Medium-sized** outlets perform best; new stores should align with this size.

3. **Promote High-Performing Categories**: Products like **Fruits and Vegetables** and **Snack Foods** should receive targeted promotions and advertising.

4. **Enhance Operations in Tier 3 Locations**: High demand in **Tier 3** suggests prioritizing resources and marketing efforts in these areas.
   
5. **Balanced Product Visibility Strategy**: Maintain optimal visibility for products, avoiding both over-exposure and under-promotion to maximize sales.
   
6. **Seasonal Promotions and Forecasting**: Use the identified trends to forecast demand and run targeted seasonal promotions to capitalize on peak sales periods.

<br>

---

## CONCLUSION

This Blinkit Sales Analysis project provides valuable insights into the performance of outlets and product categories. The analysis revealed that **Supermarket Type1** outlets and **Tier 3** locations are the most profitable, while **Fruits and Vegetables** and **Snack Foods** lead in sales. The recommendations suggest expanding high-performing **outlet types**, optimizing **outlet sizes**, and focusing marketing efforts on the most successful categories and regions.

These findings and recommendations can guide strategic decisions to enhance operations, improve customer satisfaction, and boost sales revenue. This project demonstrates how **Power BI’s data visualization and DAX measures** can be effectively used to gain business insights.

