# LITA-CAPSTONE-PROJECT
## SALE PERFORMNCE DATA ANALYSIS FOR A RETAIL STORE
## Dataset
![Screenshot 2024-11-05 151507](https://github.com/user-attachments/assets/8bd98069-b1ab-4daa-a0f2-c041caf53384)

## Project Overview
To analyze the sales performance of a retail store exploreing the data to uncover key insights such as top-selling products, regional 
performance, and monthly sales trends. Create reports and visualization based on the analysis.

## Data Description
The dataset  includes the following key columns:
1. OrderID: A unique identifier assigned to each order placed.
2. Customer ID: A unique identifier associated with the customer who placed the order
3. Product: The specific item or product purchased in the order
4. Region: The geographic location where the order was placed or delivered.
5. OrderDate: The date when the order was placed.
6. Quantity: The number of units sold for a product.
7. UnitPrice:The cost of a product.

## Data Source
This dataset that was freely provided by the facilitator.

## Time Period
The dataset spans from 2023-2024

## Explorative Data Analysis
This project was designed to address the following analysis goals:
- Top-selling products: Identify which products are sold most frequently (unit sold) to maintain adequate stock levels of materials.
- Regional performance: Sales comparison across different regions to help identify top- performing locations.
- Monthly sales trends

 ## Tools and Methods Used

Data cleaning: Removal of duplicates, ensuring data consistency by changing data types e.t.c This was done using Power Query
Data Analysis: The data was analyzed using Microsoft Excel, utilizing Pivot Tables to organize, summarize, and filter the data for easier interpretation.
Data Visualization: Utilizing Power BI, Different visualizations were created represent the key insights.

# ANALYSIS, VISUALIZATION, AND INFERENCE

##  Use pivot tables to summarize total sales by product, region, and month, and use Excel formulas to calculate metrics such as average sales per product and 
total revenue by region. 

### 1. Total sales per product
![Total sales by product](https://github.com/user-attachments/assets/68824dfc-15ee-4bea-9478-750395d15a58)
![Screenshot 2024-11-05 161719](https://github.com/user-attachments/assets/4cd10b3e-9697-46d5-878a-c9704c11dd9b)

### 2.Total sales per region
![Screenshot 2024-11-05 091454](https://github.com/user-attachments/assets/a3c0f885-5348-4420-8344-49b2df9353ed)
![Screenshot 2024-11-05 094243](https://github.com/user-attachments/assets/fba3f7c2-c105-4623-a1ca-bc935a00afc8)

### 3. Total sales per month
![Screenshot 2024-11-05 101759](https://github.com/user-attachments/assets/07b4ad16-98e0-4ad9-9a4b-212bd6c7b9c4)
![Screenshot 2024-11-05 102845](https://github.com/user-attachments/assets/72d4c68c-4a06-4722-a71a-fd905140d2ef)

### 4. Average sales per product
![Screenshot 2024-11-05 163000](https://github.com/user-attachments/assets/175f122b-d882-435a-ab49-02f7d38f7bf8)

### 5. Total revenue per region
![Screenshot 2024-11-05 164051](https://github.com/user-attachments/assets/e0bee198-59c1-475c-8464-b75e56010f00)

## Using SQL queries to extract key insights 

### TO RETRIEVE TOTAL SALES FOR EACH PRODUCT
``` select Product, Unitprice from dbo.salesdata 
select product, sum(quantity) as sales_per_product from dbo.salesdata 
group by product```






