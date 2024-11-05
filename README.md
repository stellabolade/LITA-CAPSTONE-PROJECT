# LITA-CAPSTONE-PROJECT
## SALE PERFORMANCE DATA ANALYSIS FOR A RETAIL STORE
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
### 1. retrieve the total sales for each product category.

```
select Product, Unitprice from dbo.salesdata
select product, sum(quantity) as sales_per_product from dbo.salesdata
group by product
```
 ![Screenshot 2024-11-05 170655](https://github.com/user-attachments/assets/d6c8d2b9-ca19-4f38-927d-006aaef652a3)

### 2. find the number of sales transactions in each region. 

```
select region, sum(quantity) as sales_per_region from salesdata
group by region
```
![Screenshot 2024-11-05 192612](https://github.com/user-attachments/assets/e7a0a772-f5d6-421b-8788-3d18599fe884)

### 3. find the highest-selling product by total sales value. 

```
Select product, sum(quantity) as total_sales from salesdata
group by product
order by total_sales DESC
```
![Screenshot 2024-11-05 195433](https://github.com/user-attachments/assets/3dbba2c5-c02a-44bc-8a89-6a298631ba2d)

### 4.calculate total revenue per product. 

```
select product, sum(revenue) as total_revenue from salesdata
group by product
```
![Screenshot 2024-11-05 195625](https://github.com/user-attachments/assets/2f92d00d-f501-42b3-8ae9-4deec8c23a4d)

### 5. calculate monthly sales totals for the current year. 

```
select product, sum(revenue) as total_revenue from salesdata
group by product
```
![Screenshot 2024-11-05 195814](https://github.com/user-attachments/assets/495b2bb8-a79e-40e9-82b8-fea8a7548bfe)


### 6. find the top 5 customers by total purchase amount. 

```
select top 5
Customer_id,Sum(Quantity) as total_purchase
From Salesdata
Group by Customer_id 
Order by total_purchase DESC
```

![Screenshot 2024-11-05 200133](https://github.com/user-attachments/assets/d6562ba6-d854-4689-a3fe-d8e93e313c71)


### 7. calculate the percentage of total sales contributed by each region. 

```
select region, sum(revenue)/sum(quantity)*0.1 as percentage_of_total_sales
FROM dbo.salesdata
GROUP BY region
ORDER BY percentage_of_total_sales
```
![Screenshot 2024-11-05 200321](https://github.com/user-attachments/assets/59e5bccb-65ce-4019-ab60-5efabac3a399)

### 8. identify products with no sales in the last quarter.

```
SELECT product, sum(quantity) AS sales
FROM dbo.salesdata
WHERE month(orderdate) between 10 and 12 --months 10, 11, and 12 (October to December)
GROUP BY Product
Having SUM (Quantity)= 0
```
![Screenshot 2024-11-05 200456](https://github.com/user-attachments/assets/f336dc18-bff6-4519-98c8-2aed10e4ac23)




