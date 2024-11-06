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

## ANALYSIS, VISUALIZATION, AND INFERENCE

##  Excel Analysis


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

## Visualization with Power BI

### Dashboard Overview

![Sales visual](https://github.com/user-attachments/assets/9c260f67-d3d2-4de7-babc-a854630d304d)

### Visuals and inference

### Total sales by product

![Total sales by product](https://github.com/user-attachments/assets/1a2ca644-8c1b-4ce4-92a9-262fd00d842d)

- Shoes are the highest selling product with total sales of $613K, indicating they are the most popular and possibly the most profitable product.

- Shirts are the second highest selling product with sales of $486K, also indicating strong sales performance.

- Hats and Gloves have moderate sales, with $316K and $297K respectively, suggesting a steady demand.

- Jackets have lower sales at $208K, which might indicate a more niche market or seasonal demand.

- Socks have the least sales at $181K, making them the least popular product among the six.

### Total sales by region

![Total sales by region](https://github.com/user-attachments/assets/f6e57e12-0202-40df-a0b4-74e044e0a131)

- The South region has the highest total sales, amounting to $928K. This indicates a strong market presence or a larger customer base in the South.

- The East region follows, with total sales of $486K, suggesting moderate market performance.

- The North region has total sales of $387K, showing it has a smaller market share compared to the South and East.

- The West region has the lowest total sales at $300K, indicating the smallest market size or presence among the four regions.

### Quantity sold by product

![Quantity sold by product](https://github.com/user-attachments/assets/6d734c3b-d977-40b1-a5fa-6c49075a5475)

- The highest selling product is Hat with 16k units sold; this is followed by Shoes with 14k units sold.

- Shirts and Gloves each have 12K units sold, suggesting a similar level of demand for these products.

- Socks have a lower quantity sold at 8K, indicating they are less popular compared to Hats, Shoes, Shirts, and Gloves.

- Jackets have the lowest quantity sold at 5K, making them the least popular item among the six products.

### Quantity sold by region

![Quantity by region](https://github.com/user-attachments/assets/2f3d3739-e78f-4827-a604-ef8ce28ecac9)

The chart reveals that the South region has the highest quantity sold at 24K, indicating it is the most significant market or has the highest demand for the products. The East region follows with 20K units sold, showing a strong market presence but less than the South. The North region has a total of 12K units sold, suggesting moderate demand compared to the South and East, while the West region has the lowest quantity sold at 11K, indicating it is the smallest market or has the lowest demand for the products.

### Total sales by year and month
### 2023
![Total sales by year and month](https://github.com/user-attachments/assets/fac6602f-1f17-490a-903a-79c389bf5263)
### 2024
![year 2024](https://github.com/user-attachments/assets/eb8e7724-e0a8-468d-8231-bcf04f9af829)


January 2023 starts with moderate sales, while February 2023 shows a significant peak with the highest sales exceeding $600K.

March 2023 experiences a sharp drop to about $248K, followed by a further decrease in April 2023 to $7K, the lowest sales month.

Sales gradually recover in May 2023 ($60K) and June 2023 ($99K), with a noticeable spike in July 2023 ($238K) and October 2023 ($134K).

A decline in November 2023 ($104K) and December 2023 ($49K) suggests lower end-of-year activity.

Sales increase again in January 2024 to $198K, followed by a sharp decline in February 2024 ($29K), then moderate recovery through March 2024 ($95K) and April 2024 ($39K).

The second half of 2024 shows significant sales improvement, with peaks in June 2024 ($148K), July 2024 ($137K), and August 2024 ($174K), indicating stronger sales performance compared to the same months in the previous year.

### Quantity sold by year and month
![Quantity by month and year](https://github.com/user-attachments/assets/ce15dd5e-a9e4-4c80-a4e6-40d5718416a0)

In 2023, there were significant peaks in sales quantities in February and July, with quantities sold reaching 5.0K and 5.9K, respectively. These peaks suggest strong market demand during these months, possibly due to seasonal factors or promotional events. However, sales dipped sharply in April and May, with quantities dropping to 1.5K and 1.0K, indicating a period of low demand.

For 2024, the sales quantities exhibit a fluctuating pattern. January 2024 started strong with 4.0K units sold, and the highest quantity sold in February and March at 5.5K each, indicating continued strong demand in the early part of the year. However, sales dropped significantly in April and May, similar to the previous year, with quantities at 2.0K and 1.5K. Sales then picked up again in June with 3.9K units and fluctuated for the rest of the year.

### Recommendations

For high performing products like Shoes and Shirts, Increase marketing efforts to maintain and boost sales. Expansion and introduction of new designs should be considered.
For low performing products, Campaigns and promotions should be intensiified. Discounts or bundles can be offered, to attract customers.
Regions with high revenue should maintain and strengthen the market presence with targeted marketing campaigns, ensuring sufficient inventory to meet high demand; while others should engage in localized promotions to boost sales.
The store should utilize peak Months and Plan major marketing campaigns maximize sales, launch new products or limited-time offers during these periods; while low performing months should intensify promotion, implement clearance sales.
