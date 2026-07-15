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
