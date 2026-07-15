# Restaurant Business Performance Analysis

## Business Objectives & Aims

The aim of this project is to develop an end-to-end Business Intelligence solution that transforms restaurant transaction data into actionable insights to support strategic decision-making.

The analysis focuses on understanding sales performance, identifying key revenue drivers, evaluating menu performance, and uncovering opportunities to improve operational efficiency and business growth.

## Key Objectives

### 1. Analyse Business Performance

- Evaluate overall sales trends and revenue performance.
- Identify the highest-performing menu items and categories.
- Analyse factors contributing to business growth.

### 2. Understand Product & Menu Performance

- Determine which products generate the highest revenue.
- Evaluate product performance based on sales contribution.
- Identify opportunities for menu optimisation and promotional strategies.

### 3. Develop Data-Driven Insights

- Clean, transform and analyse raw business data.
- Apply SQL and Python techniques to explore trends and patterns.
- Create dashboards that communicate insights clearly to stakeholders.

### 4. Support Business Decision-Making

- Translate analytical findings into practical recommendations.
- Highlight opportunities to improve profitability and operational performance.
- Demonstrate how data can support strategic business decisions.

# Dataset Overview

The analysis uses restaurant transaction data containing order-level details and menu information. The dataset represents customer purchasing activity and provides insight into sales performance, product demand and operational trends.

The data consists of two key tables:

### Order Details Table

Contains transaction-level information for each menu item purchased.

Key fields include:

- `order_details_id` - Unique identifier for each transaction line
- `order_id` - Customer order identifier
- `order_date` - Date the order was placed
- `order_time` - Time the order was placed
- `item_id` - Identifier linking transactions to menu items

### Menu Items Table

Contains product information required for menu and revenue analysis.

Key fields include:

- `item_id` - Unique product identifier
- `item_name` - Menu item name
- `category` - Product category
- `price` - Selling price

---

# Data Assessment & Quality Checks

Before analysis, an initial data assessment was performed using Python to understand the dataset structure, identify data quality issues and determine preparation requirements.

## Dataset Structure

The order details dataset contains:

- **12,234 transaction-level records**
- **5,370 unique customer orders**
- **32 unique menu items**

Each row represents an individual item purchased within an order. As multiple items can belong to the same order, order-level metrics will be calculated using unique `order_id` values rather than transaction row counts.

---

# Data Quality Findings

## Missing Values

A data quality assessment identified:

- 137 missing values within the `item_id` field.

Further investigation showed these records represented 137 unique customer orders.

Since `item_id` is required to connect transactions with menu information, these records cannot be accurately analysed for product-level insights. As they represented approximately 1.12% of the dataset, they will be removed during the cleaning stage to maintain analytical accuracy.

---

## Duplicate Records

A duplicate record assessment was performed:

- No duplicate transaction records were identified.

This confirms that each transaction detail record represents a unique entry within the dataset.

---

## Data Formatting Issues

The following transformation requirements were identified:

- `order_date` requires conversion from text format into a datetime field.
- `order_time` requires formatting to support time-based analysis.
- `item_id` requires conversion from float to integer format after missing values are addressed.

---

# Data Preparation Approach

The following cleaning and transformation steps will be performed:

- Remove records with missing product identifiers.
- Standardise data types.
- Validate relationships between transaction and menu tables.
- Create analysis-ready datasets for SQL querying, Python analysis and BI dashboard development.

# Data Cleaning & Transformation

Following the initial data assessment, the raw datasets were cleaned and transformed using Python and Pandas to create reliable, analysis-ready datasets for business intelligence reporting.

The cleaning process focused on improving data quality, standardising fields, and preparing the data structure for SQL analysis and dashboard development.

---

# Order Details Cleaning

The order details dataset contained 12,234 transaction-level records.

The following transformations were performed:

## Missing Data Handling

- Identified 137 records with missing `item_id` values.
- Investigated the impact of missing records and found they represented 137 unique orders.
- As `item_id` was required to connect transactions with menu information, these records were removed to prevent inaccurate product-level analysis.

The removal affected approximately 1.12% of the dataset.

---

## Data Type Standardisation

The following fields were transformed:

- Converted `order_date` from text format into a datetime field.
- Converted `order_time` into a time format to support time-based analysis.
- Corrected `item_id` from float format to integer format after missing records were removed.

---

## Feature Engineering

Additional fields were created to support business analysis:

- `order_month` — Used to analyse monthly sales trends.
- `day_of_week` — Used to identify demand patterns across weekdays.
- `order_hour` — Used to identify peak ordering periods.

These fields support future analysis of customer behaviour and operational performance.

---

# Menu Dataset Cleaning

The menu dataset contained 32 menu items and required minimal transformation.

Checks performed:

- Verified there were no missing values.
- Confirmed appropriate data types.
- Validated pricing fields for numerical analysis.
- Standardised column naming conventions to support database relationships.

The menu dataset was prepared as a reference table containing product information including:

- Item name
- Category
- Price

---

# Final Clean Dataset Structure

The cleaned datasets were prepared for integration:

### Orders Table

Contains:

- Transaction identifiers
- Order date and time
- Product identifiers
- Time-based analytical fields

### Menu Table

Contains:

- Product identifiers
- Menu item names
- Categories
- Pricing information

These datasets are now ready for SQL querying, data modelling and dashboard development.

---

# Tools Used

- Python
- Pandas
- NumPy
- Data Cleaning Techniques
- Data Validation
- Feature Engineering

# Power BI Data Preparation & Data Modelling

After completing data exploration and cleaning using Python, the cleaned datasets were imported into Power BI for further transformation, modelling and business intelligence development.

The objective of this stage was to create a scalable data model that could support accurate reporting and dashboard analysis.

---

# Power Query Transformation

Power Query was used to validate and prepare the cleaned datasets before building the analytical model.

Transformations performed included:

- Imported cleaned transaction and menu datasets into Power BI.
- Reviewed and validated column data types.
- Ensured date, time and numerical fields were correctly formatted.
- Prepared datasets for relationship modelling.
- Validated data quality before loading into the reporting layer.

---

# Data Model Design

A star schema approach was implemented to separate transactional data from descriptive information.

This structure improves:

- Data organisation
- Report performance
- Scalability
- Accuracy of business calculations

The final model consists of:

## Fact Table — Fact_Sales

Contains transactional-level sales data.

Fields include:

- `order_details_id`
- `order_id`
- `order_date`
- `order_time`
- `item_id`
- `order_month`
- `day_of_week`
- `order_hour`

This table represents individual menu item transactions.

---

## Dimension Table — Dim_Menu

Contains descriptive product information.

Fields include:

- `item_id`
- `item_name`
- `category`
- `price`

This table provides additional context for analysing product performance.

---

# Relationship Design

The tables were connected using a one-to-many relationship:

Dim_Menu
|
| 1
|
*
Fact_Sales


Relationship:

`Dim_Menu[item_id] → Fact_Sales[item_id]`

This allows transaction data to be analysed by:

- Menu item
- Category
- Product pricing

while maintaining a clean and efficient data structure.

---

# Business Intelligence Workflow

The completed workflow demonstrates an end-to-end analytics process:

Raw Data  
↓  
Data Exploration (Python)  
↓  
Data Cleaning & Validation (Python/Pandas)  
↓  
Power Query Transformation  
↓  
Star Schema Data Model  
↓  
DAX Measures & KPI Development  
↓  
Power BI Dashboard & Insights

---

# Tools Used

- Power BI Desktop
- Power Query
- Data Modelling
- Star Schema Design
- Python
- Pandas
- CSV Data Integration

# DAX Measures & KPI Development

To support business reporting, reusable DAX measures were created within Power BI.

Key metrics developed include:

## Revenue Analysis

- Total Revenue
- Monthly Revenue

## Order Performance

- Total Orders
- Total Items Sold
- Average Order Value
- Average Items Per Order

These measures were designed to provide consistent calculations across dashboards and enable interactive business analysis.

