# Initial Data Assessment

## Order Details Dataset

The order details dataset contains 12,234 records representing individual menu item transactions.

## Key Findings

### Data Completeness

- The dataset contains 137 missing values within the item_id field.
- Further analysis showed that these records represented 137 unique orders.
- As item_id is required to accurately link transactions with menu information, these records cannot be reliably used for product, category or revenue analysis.
- Since the missing records represent approximately 1.12% of the dataset, they will be removed during the cleaning stage to maintain analytical accuracy.

### Data Formatting

- order_date is currently stored as a text field and requires conversion into a datetime format.
- order_time is stored as text and requires transformation for time-based analysis.
- item_id is stored as a float due to missing values and requires data type correction.

### Product Coverage Assessment

The order details dataset contains 32 unique menu item identifiers.

These identifiers will be matched with the menu items dataset to retrieve additional product information, including item names, categories and pricing.

This relationship enables product-level analysis such as:
- Revenue contribution by menu item
- Category performance
- Product demand trends
- Menu optimisation opportunities

## Preparation Required

The dataset will require cleaning and transformation before being used for SQL analysis, dashboard development and business reporting.

## Menu Dataset Assessment

The menu dataset contains 32 records representing available restaurant menu items.

### Data Quality Findings

- No missing values were identified across any fields.
- Data types were appropriate for analysis.
- Menu item identifiers were correctly formatted as integers.
- Price values were stored as numeric fields, allowing revenue calculations.

### Relationship Validation

The menu dataset will be linked with the order details dataset using the menu_item_id and item_id fields.

This relationship will allow transaction-level records to be enriched with product details such as item names, categories and pricing.
