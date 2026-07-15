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
