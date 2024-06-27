# Manufacture-Analysis-using-POWERBI

## Overview
This project involves accessing, preparing, modeling, exploring, and visualizing data using Power BI. The goal is to create a comprehensive report that provides insights into the dataset and helps in decision-making.

## Pipeline Summary

### 1. Data Access and Preparation
- **Data Sources**: Accessed data from multiple sources including CSV files, Excel spreadsheets, and databases.
- **Data Cleaning**:
  - Handled missing values by replacing them with the mean or median of the column.
  - Removed duplicate rows to ensure data consistency.
  - Corrected data types, such as converting text to date formats or numbers.
  - Standardized categorical variables by ensuring consistent naming conventions.
  - Filtered outliers to improve data quality and accuracy.
- **Data Transformation**: Applied various transformations such as pivoting, unpivoting, merging, and splitting columns to structure the data appropriately.

### 2. Data Modeling and Exploration
- **Creating Data Models**: Established relationships between tables to create a robust data model in Power BI.
- **Exploration Techniques**: Conducted exploratory data analysis (EDA) to understand data distributions, trends, and anomalies.
- **Power BI Features**: Utilized features like calculated columns and measures to derive additional insights from the data.

### 3. DAX Queries
- **Calculated Columns**:
  - Sales Amount: Created a new column that multiplies the quantity by the unit price.
    - `Sales Amount = [Quantity] * [Unit Price]`
  - Profit: Created a new column that calculates profit by subtracting the cost from the sales amount.
    - `Profit = [Sales Amount] - [Cost]`
  
- **Measures**:
  - Total Sales: Sum of the Sales Amount column.
    - `Total Sales = SUM('Sales'[Sales Amount])`
  - Total Profit: Sum of the Profit column.
    - `Total Profit = SUM('Sales'[Profit])`
  - Total Cost: Sum of the Cost column.
    - `Total Cost = SUM('Sales'[Cost])`
  - Average Sales: Average of the Sales Amount column.
    - `Average Sales = AVERAGE('Sales'[Sales Amount])`
  - % Growth: Percentage growth calculated by dividing the difference between current year sales and previous year sales by the previous year sales.
    - `% Growth = DIVIDE([Current Year Sales] - [Previous Year Sales], [Previous Year Sales])`
  - Current Year Sales: Calculates total sales for the current year.
    - `Current Year Sales = CALCULATE([Total Sales], YEAR('Sales'[Date]) = YEAR(TODAY()))`
  - Previous Year Sales: Calculates total sales for the previous year.
    - `Previous Year Sales = CALCULATE([Total Sales], YEAR('Sales'[Date]) = YEAR(TODAY()) - 1)`

### 4. Relationships
- **Sales Table and Products Table**:
  - Relationship Type: Many-to-One
  - Key: Sales[ProductID] to Products[ProductID]
- **Sales Table and Customers Table**:
  - Relationship Type: Many-to-One
  - Key: Sales[CustomerID] to Customers[CustomerID]
- **Sales Table and Date Table**:
  - Relationship Type: Many-to-One
  - Key: Sales[Date] to Date[Date]
- **Products Table and Manufacturers Table**:
  - Relationship Type: Many-to-One
  - Key: Products[ManufacturerID] to Manufacturers[ManufacturerID]

### 5. Data Visualization
- **Visual Types**: Created a variety of visuals to effectively represent the data, including:
  - **Bar Chart**: Visualizes total sales by product category, helping to identify top-performing categories.
  - **Line Chart**: Displays monthly sales trends over time, providing insights into seasonal patterns.
  - **Pie Chart**: Shows the distribution of sales by region, illustrating the geographical spread of the business.
  - **Matrix Visual**: Summarizes sales and profit by product and region, offering a detailed view of performance across different dimensions.
  - **Gauge Chart**: Represents sales performance against targets, indicating how well the business is meeting its goals.
  - **Scatter Plot**: Plots sales versus profit to identify correlations and outliers.
  - **Smart Narrative**: Automatically generates insights and summaries based on the data, providing context and explanations for key trends.

- **Interactive Elements**: Added slicers, drill-downs, and tooltips to enhance the interactivity of the report.
- **Conditional Formatting**: Applied conditional formatting to highlight key metrics and trends.
  - Example: Background color formatting based on growth percentages.
- **Report Customization**: Customized the report layout with themes, logos, and formatted titles for a professional appearance.
- **Advanced Visuals**: Utilized advanced visuals such as gauge charts and smart narratives to provide deeper insights.

## Conclusion
The project successfully demonstrates the use of Power BI for comprehensive data analysis and visualization. The final report provides valuable insights through interactive and visually appealing dashboards.
