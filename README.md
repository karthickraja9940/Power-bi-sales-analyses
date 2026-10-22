# Power BI Sales Analysis – E-Commerce Dataset

## 📊 Project Overview

This project focuses on analyzing an **E-Commerce Sales Dataset** using **Microsoft Power BI**. The objective is to apply **DAX (Data Analysis Expressions)** to create calculated columns and measures, and then build interactive visualizations to understand sales, profitability, targets, and business performance.

This project is part of my **Data Analytics learning journey** and is included in my Data Analyst portfolio.

---

## 🎯 Problem Statement

As a Data Analyst, the goal of this project is to analyze an E-Commerce Sales dataset using Power BI.

The dataset contains multiple related tables with information about:

- Orders
- Customers
- Products
- Sales
- Profit
- Sales Targets

The project focuses on:

- Creating calculated columns using DAX
- Creating analytical measures using DAX
- Analyzing sales and profitability
- Comparing actual sales with targets
- Identifying sales trends
- Analyzing sub-category performance
- Creating interactive Power BI visualizations
- Generating meaningful business insights

---

## 📁 Dataset Description

The project uses three related datasets.

### 1. List of Orders

| Column | Description |
|---|---|
| Order ID | Unique order identifier |
| Order Date | Date of the order |
| Customer Name | Customer name |
| City | Customer city |
| State | Customer state |
| Category | Product category |
| Amount | Sales amount |
| Profit | Profit generated |

### 2. Order Details

| Column | Description |
|---|---|
| Order ID | Unique order identifier |
| Category | Product category |
| Sub-Category | Product sub-category |
| Quantity | Quantity sold |
| Amount | Sales amount |
| Profit | Profit generated |

### 3. Sales Target

| Column | Description |
|---|---|
| Category | Product category |
| Month of Order Date | Sales target month |
| Target | Target sales amount |

---

# 🧮 DAX Calculated Columns

## 1. Category Type

A calculated column named **Category Type** was created in the `Order Details` table by combining the `Category` and `Sub-Category` columns.

Example DAX:

```DAX
Category Type = 
'Order Details'[Category] & " - " & 'Order Details'[Sub-Category]
```

This creates a combined category such as:

```text
Electronics - Phones
Furniture - Chairs
Clothing - Sarees
```

---

## 2. Revenue per Order

A calculated column was created to calculate revenue using **Amount × Quantity**.

```DAX
Revenue per Order = 
'Order Details'[Amount] * 'Order Details'[Quantity]
```

This helps analyze the revenue generated from each order based on quantity sold.

---

## 3. Sales Category

A calculated column named **Sales Category** was created to classify sales as either **Above Average** or **Below Average** based on the Amount value.

```DAX
Sales Category =
IF(
    'Order Details'[Amount] >=
    AVERAGE('Order Details'[Amount]),
    "Above Average",
    "Below Average"
)
```

This classification helps identify orders that perform above or below the average sales amount.

---

# 📐 DAX Calculated Measures

## 1. Order Count

A measure was created to calculate the total number of orders.

```DAX
Order Count =
COUNTROWS('Order Details')
```

---

## 2. Average Profit in Delhi

A measure was created to calculate the average profit for orders placed in Delhi.

```DAX
Average Profit in Delhi =
CALCULATE(
    AVERAGE('List of Orders'[Profit]),
    'List of Orders'[City] = "Delhi"
)
```

This measure helps evaluate the average profitability of sales in Delhi.

---

## 3. Year-to-Date Sales

A YTD measure was created to calculate cumulative sales from the beginning of the year up to the selected/current date.

```DAX
YTD Sales =
TOTALYTD(
    SUM('List of Orders'[Amount]),
    'List of Orders'[Order Date]
)
```

This measure helps track sales performance throughout the year.

---

# 📊 Power BI Visualizations

The following interactive visualizations were created as part of the analysis.

## 1. Sales Target Achievement by Category

**Visual:** Clustered Column Chart

This visualization compares:

- Actual Sales
- Sales Target

across different product categories.

**Purpose:**  
To identify categories that are meeting, exceeding, or falling below their sales targets.

---

## 2. Maximum Profit Margin by Sub-Category

**Visual:** Donut Chart

This visualization analyzes the maximum profit margin across different product sub-categories.

**Purpose:**  
To identify sub-categories with stronger profitability.

---

## 3. Monthly Sales Trend

**Visual:** Line Chart

The line chart displays sales performance across different months.

**Purpose:**

- Identify sales trends
- Find high-sales months
- Find low-sales months
- Understand changes in sales over time

---

## 4. Profit vs Quantity by Sub-Category

**Visual:** Scatter Chart

The scatter chart compares:

- Profit
- Quantity Sold

across different sub-categories.

**Purpose:**  
To understand whether higher quantities sold are associated with higher profits.

---

## 5. Total Sales Amount vs Sales Target

**Visual:** Cards

Cards were created to display:

- Total Sales Amount
- Total Sales Target

This provides a quick comparison between actual sales performance and the target.

A **Multi-row Card** was also created to display the minimum target for each segment/category.

---

## 6. Sales Performance Matrix

**Visual:** Matrix

The matrix analyzes actual sales against sales targets across:

- Categories
- Months

**Purpose:**  
To provide a detailed view of sales performance and target achievement.

---

## 7. Geographic Sales Analysis

**Visual:** Map

A map visualization was created using city-level information to display total sales geographically.

**Purpose:**

- Identify high-performing cities
- Identify regional sales patterns
- Understand geographic distribution of sales

---

## 8. Sales Distribution by Sub-Category

**Visual:** Treemap

The treemap represents sales distribution across different product sub-categories.

**Purpose:**  
To quickly identify sub-categories contributing the largest and smallest portions of total sales.

---

## 9. Order Count Analysis by State

**Visual:** Funnel Chart

A funnel chart was created to visualize order counts across different states.

**Purpose:**  
To compare order volume between states and identify states with higher or lower order counts.

---

# 🛠️ Tools & Technologies

- **Microsoft Power BI**
- **DAX (Data Analysis Expressions)**
- **Power Query**
- **Data Modeling**
- **Data Visualization**
- **GitHub**

---

# 🔄 Project Workflow

```text
E-Commerce Dataset
        ↓
Import Data into Power BI
        ↓
Review Data Model
        ↓
Create Calculated Columns
        ↓
Create DAX Measures
        ↓
Create Visualizations
        ↓
Analyze Sales & Profitability
        ↓
Generate Business Insights
```

---

# 📌 Key Skills Demonstrated

Through this project, I practiced and demonstrated:

- Power BI
- DAX
- Calculated Columns
- Calculated Measures
- Data Analysis
- Data Modeling
- Sales Analysis
- Profitability Analysis
- Target vs Actual Analysis
- Time-Series Analysis
- Geographic Analysis
- Interactive Data Visualization
- Business Intelligence

---

# 💡 Business Analysis

The dashboard helps a business understand:

- Which categories generate higher sales
- Which sub-categories perform better
- How sales change over time
- How actual sales compare with targets
- Which locations generate more sales
- Which states have higher order volumes
- The relationship between quantity sold and profit
- Which areas may require additional business attention

---

# 📷 Dashboard

Power BI dashboard screenshots can be added here:

```text
[Add Power BI Dashboard Screenshot Here]
```

Additional screenshots of DAX calculations and visualizations can also be included to demonstrate the analysis process.

---

# 🚀 Portfolio Project

This project is part of my journey toward becoming a **Data Analyst**.

I am building my portfolio by completing practical projects using:

- Excel
- Power BI
- SQL
- Data Analysis
- Data Visualization

---

## 👤 Author

**Karthick Raja**

Aspiring Data Analyst

GitHub:  
https://github.com/karthickraja9940

---

## ⭐ Conclusion

This Power BI project demonstrates how DAX calculations and interactive visualizations can transform raw E-Commerce data into meaningful business information.

The analysis provides a foundation for understanding sales performance, profitability, targets, customer locations, and product-level performance using Power BI.



















# Power-bi-sales-analyses
