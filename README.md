 E-Commerce Sales Analysis

 Project Overview

This project performs an **E-Commerce Sales Analysis** using Python and Jupyter Notebook.

The analysis is based on a sales dataset containing information about orders, customers, products, categories, sales, quantity, discounts, profit, locations, and regions.

The main purpose of this project is to clean and analyze the sales data and identify useful business insights related to:

* Sales performance
* Profitability
* Product performance
* Category performance
* Regional performance
* Monthly sales trends
* State-level sales
* Discount and profit relationships



 Project Objectives

The main objectives of this project are:

1. Load and inspect the e-commerce sales dataset.
2. Identify missing values and data-quality issues.
3. Check and correct data types.
4. Convert order and shipping dates into proper datetime format.
5. Create useful date-based columns for analysis.
6. Calculate total sales and total profit.
7. Analyze sales by category and region.
8. Identify top-performing products.
9. Analyze sales by state.
10. Analyze the relationship between discount and profit.
11. Create charts to communicate important business insights.

 Project Structure

text
Ecommerce-Sales-Analysis/
│
├── Ecommerce_Sales_Analysis.ipynb
├── sales.csv
└── README.md
```

### Files

**`Ecommerce_Sales_Analysis.ipynb`**

The main Jupyter Notebook containing the complete data analysis, data cleaning, calculations, and visualizations.

**`sales.csv`**

The dataset used for the analysis.

README.md

Project documentation explaining the dataset, methodology, analysis, and results.

 Dataset

The dataset contains **4,213 records and 17 original columns** in the notebook.

The original columns include:

| Column        | Description                     |
| ------------- | ------------------------------- |
| Row ID        | Unique row identifier           |
| Order ID      | Unique order identifier         |
| Order Date    | Date when the order was placed  |
| Ship Date     | Date when the order was shipped |
| Ship Mode     | Shipping method                 |
| Customer Name | Customer name                   |
| Segment       | Customer segment                |
| Product       | Product name                    |
| Category      | Product category                |
| Sub-Category  | Product sub-category            |
| Sales         | Sales amount                    |
| Quantity      | Quantity purchased              |
| Discount      | Discount applied                |
| Profit        | Profit generated                |
| City          | Customer city                   |
| State         | Customer state                  |
| Region        | Customer region                 |

The notebook initially shows `Order Date`, `Ship Date`, and `Sales` as object-type fields, which are then processed during data preparation.



Technologies Used

The project uses:

Python
Jupyter Notebook
Pandas
NumPy
 Matplotlib
Seaborn

Pandas and NumPy are imported at the beginning of the notebook for data manipulation and numerical analysis.


 Data Analysis Workflow

The project follows these major steps:

```text
Load Dataset
     ↓
Data Inspection
     ↓
Data Cleaning
     ↓
Data Type Conversion
     ↓
Date Feature Creation
     ↓
Exploratory Data Analysis
     ↓
Business Analysis
     ↓
Data Visualization
     ↓
Business Insights
```



 Data Cleaning

The dataset is inspected for:

* Missing values
* Duplicate records
* Incorrect data types
* Date formatting
* Numeric data issues
* Inconsistent values

The notebook checks the structure and data types using methods such as:

```python

df.info()
```

and:

```python
df.describe()
```

The notebook also performs duplicate checking using business-related columns.

---

  Date Feature Engineering

The original `Order Date` field is converted into a datetime format.

The notebook creates additional date-related columns:

```python
df["Order Month"]
df["Order Year"]
df["Month Name"]
df["Year Month"]
```

These columns are used to support monthly and yearly sales analysis.

Example:

```text
Order Date → 2024-02-10

Order Month → 2
Order Year  → 2024
Month Name  → February
Year Month  → 2024-02
```

---

 Business Analysis

1. Monthly Sales

Monthly sales are analyzed to understand sales trends over time.

The analysis uses the `Year Month` field to organize sales chronologically.

The project also uses a line chart to visualize monthly sales trends.



2. Sales by Category

Sales are grouped by product category to identify which categories generate the most revenue.

The notebook calculates:

```python
df.groupby("Category")["Sales"].sum()
```

A bar chart is used to visualize category-level sales performance.


 3. Sales by Region

Sales are analyzed across different geographical regions.

The regions include:

* Central
* West
* East
* South

This analysis helps compare revenue performance across regions.



4. Profit by Region

Profit is grouped by region to identify which geographical areas contribute most to overall profitability.

The notebook calculates regional profit using:

```python
df.groupby("Region")["Profit"].sum()
```

A bar chart is created to visualize the results.



 5. Top 10 Products by Sales

The project identifies the top 10 products based on total sales.

The calculation groups sales by product, sorts them in descending order, and selects the top 10 products.

```python
df.groupby("Product")["Sales"].sum()
```

A horizontal bar chart is used to compare the top-performing products.

---

## 6. Sales by State

Sales are also grouped by state to identify the strongest state-level markets.

The notebook uses:

```python
df.groupby("State")["Sales"].sum()
```

This analysis can help identify locations with higher sales performance.

---

 7. Discount and Profit Analysis

The project investigates how discounts affect profitability.

The analysis includes:

* Discount bands
* Average profit by discount band
* Discount vs. profit relationship
* Correlation between discount and profit

The purpose is to determine whether higher discounts are associated with lower profitability.

---

  Key Results

Based on the analysis results obtained from the project:

| KPI                 |        Result |
| ------------------- | ------------: |
| Total Sales         | $5,296,907.13 |
| Total Profit        |   $534,110.89 |
| Total Orders        |         3,500 |
| Average Order Value |     $1,513.40 |

Category Performance

Technology is the highest-selling category with sales of approximately:

$3,447,751.75

Regional Sales

The regional sales results show:

| Region  |         Sales |
| ------- | ------------: |
| Central | $1,377,785.78 |
| West    | $1,336,727.86 |
| East    | $1,333,694.80 |
| South   | $1,248,698.69 |

 Best Sales Month

The best Year-Month identified in the analysis is:

December 2023 — $355,100.78

The best calendar month across all years is:

December — $843,468.20

Discount and Profit

The analysis shows a negative correlation between discount and profit:

Correlation = -0.416

This indicates that, within this analysis, higher discounts tend to be associated with lower profit.

---

  Visualizations

The project creates visualizations including:

 Monthly Sales

A line chart showing sales trends over time.

 Sales by Category

A bar chart comparing sales across categories.

## Profit by Region

A bar chart comparing profit across regions.

Top 10 Products

A horizontal bar chart showing the products with the highest sales.

These visualizations make the results easier to understand and communicate.

---

 Business Insights

The analysis provides several useful observations:

1. Technology is the strongest sales category, generating the highest revenue among the analyzed categories.

2. Central region has the highest regional sales among the four regions.

3. Central region also has the highest total profit in the provided regional analysis.

4. December is the strongest calendar month, indicating stronger sales performance during this period.

5. The top-selling products are mainly laptop products, which dominate the top 10 product list.

6. The negative discount-profit correlation (-0.416) suggests that increasing discounts may reduce profitability.

7. State-level analysis can be used to identify high-performing geographical markets.


 How to Run the Project

## Step 1: Install Python

Install Python from the official Python website or use Anaconda.

## Step 2: Install Required Libraries

Open Anaconda Prompt or Command Prompt and run:

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

Step 3: Open Jupyter Notebook

Run:

```bash
jupyter notebook
```

Step 4: Open the Project

Open:

```text
Ecommerce_Sales_Analysis.ipynb
```

 Step 5: Keep the Dataset in the Project Folder

Make sure:

```text
sales.csv
```

is available to the notebook.

Step 6: Run the Notebook

Run the notebook cells from top to bottom.

This is important because the notebook creates new columns such as `Order Month`, `Order Year`, `Month Name`, and `Year Month` during the analysis.



 Important Note

The notebook uses a local file path to load the CSV dataset. For example:

```python
df = pd.read_csv(
    r"C:\Users\hp\OneDrive\Desktop\Ecommerce_sales Analysis\sales.csv"
)
```

When sharing the project with another person, this path should be changed to a relative path such as:

```python
df = pd.read_csv("sales.csv")
```

This allows the project to work on different computers without changing the user's personal folder path.



 Project Purpose

This project demonstrates practical skills in:

* Data loading
* Data cleaning
* Data type conversion
* Feature engineering
* Exploratory Data Analysis (EDA)
* GroupBy analysis
* Business KPI calculation
* Sales analysis
* Profit analysis
* Data visualization
* Business insight generation

It can be used as a portfolio project or as part of a data analytics internship submission.



 Author

Aman Rana

E-Commerce Sales Analysis Project

---

## License

This project is intended for educational, learning, and portfolio purposes.
