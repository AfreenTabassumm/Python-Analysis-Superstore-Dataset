
# 📊 Superstore Sales — Exploratory Data Analysis

## 📌 Project Overview

This project performs an end-to-end **Exploratory Data Analysis (EDA)** on the **Sample Superstore Sales Dataset** using Python.

The objective is to understand sales performance, profitability, customer behavior, product performance, regional trends, and identify areas where the business can improve revenue and profitability.

The analysis was performed using:

* 🐼 **Pandas** — Data manipulation and analysis
* 🔢 **NumPy** — Numerical analysis
* 📊 **Matplotlib** — Data visualization
* 📈 **Seaborn** — Statistical visualization
* 📓 **Jupyter Notebook** — Analysis environment

---

## 🎯 Business Objective

The primary objective of this project is to answer important business questions such as:

1. What is the overall Sales and Profit performance?
2. Which Categories generate the highest Sales?
3. Which Categories and Sub-Categories generate the highest Profit?
4. Which Products are the top performers?
5. Which Products and Sub-Categories are loss-making?
6. Which Regions and States perform best?
7. Which Customer Segments generate the most revenue and profit?
8. How do Sales and Profit change over time?
9. Is there a relationship between Sales and Profit?
10. Where are the major outliers?
11. What business actions can improve profitability?

---

# 📁 Project Structure

```text
Superstore-Sales-EDA/
│
├── Sample - Superstore.xls
│
├── Superstore_EDA_Analysis.ipynb
│
├── Superstore_Cleaned.csv
│
└── README.md
```

---

# 🛠️ Technologies Used

| Technology       | Purpose                      |
| ---------------- | ---------------------------- |
| Python           | Data analysis                |
| Pandas           | Data cleaning & manipulation |
| NumPy            | Numerical calculations       |
| Matplotlib       | Data visualization           |
| Seaborn          | Statistical visualization    |
| Jupyter Notebook | EDA development              |

---

# 🔍 Project Workflow

The project follows a structured data analytics workflow:

```text
Raw Dataset
     ↓
Data Loading
     ↓
Data Quality Check
     ↓
Data Cleaning
     ↓
Exploratory Data Analysis
     ↓
Statistical Analysis
     ↓
Visualization
     ↓
Business Insights
     ↓
Recommendations
```

---

# 🧹 1. Data Loading & Data Cleaning

The dataset is loaded using Pandas.

```python
df = pd.read_excel("Sample - Superstore.xls", engine="xlrd")
```

### Data preparation includes:

* Checking dataset dimensions
* Inspecting column names
* Checking data types
* Identifying missing values
* Detecting duplicate records
* Removing duplicate records
* Converting date columns
* Creating additional time-based features

### Created Time Features

```text
Order Year
Order Month
Order Month Name
Order Quarter
```

These features are used for time-series analysis.

---

# 📊 2. Descriptive Statistics

Statistical analysis is performed using:

```python
df.describe()
```

This helps understand:

* Mean
* Median
* Standard deviation
* Minimum
* Maximum
* Quartiles
* Distribution of numerical variables

---

# 💰 3. Business KPI Analysis

The project calculates important business KPIs including:

### Key KPIs

* Total Sales
* Total Profit
* Total Quantity
* Unique Orders
* Unique Customers
* Profit Margin %

These KPIs provide a high-level overview of business performance.

---

# 📦 4. Category Analysis

Sales and Profit are analyzed across different product categories.

### Analysis includes:

* Sales by Category
* Profit by Category
* Quantity by Category

Visualization is used to compare category performance.

---

# 🗂️ 5. Sub-Category Analysis

The project analyzes individual product sub-categories.

### Metrics:

* Sales
* Profit
* Quantity

The analysis identifies:

* High-sales sub-categories
* High-profit sub-categories
* Low-profit sub-categories
* Loss-making sub-categories

This helps identify areas where pricing, discounts or product strategy may need improvement.

---

# 🌎 6. Regional Analysis

Sales and Profit are analyzed by geographical regions.

### Analysis includes:

* Sales by Region
* Profit by Region
* Number of Orders by Region

The project also analyzes performance at the **State level** to identify high-performing and weak-performing markets.

---

# 👥 7. Customer Segment Analysis

Customer performance is analyzed using segments.

Metrics include:

* Sales
* Profit
* Orders

This helps identify which customer segments contribute most to business performance.

---

# 📅 8. Time-Series Analysis

Sales and Profit trends are analyzed over time.

### Monthly Analysis

The project calculates:

```text
Monthly Sales
Monthly Profit
```

### Yearly Analysis

The project calculates:

```text
Yearly Sales
Yearly Profit
Yearly Orders
```

This helps identify:

* Growth trends
* Seasonal patterns
* Strong/weak periods
* Changes in profitability

---

# 🏆 9. Product Performance Analysis

Products are ranked based on:

* Sales
* Profit
* Orders

The project identifies:

### Top Products by Sales

Products generating the highest revenue.

### Top Products by Profit

Products contributing the most profit.

### Bottom Products by Profit

Products with the weakest profitability.

---

# 🔴 10. Loss-Making Analysis

One of the important objectives of the project is identifying transactions where:

```python
Profit < 0
```

The analysis calculates:

* Number of loss-making transactions
* Loss-making sales value
* Total loss
* Loss percentage
* Loss by Sub-Category

This helps the business identify products that generate revenue but negatively affect profitability.

---

# 📈 11. Sales vs Profit Analysis

A scatter plot is used to analyze the relationship between:

```text
Sales ↔ Profit
```

This helps identify:

* High Sales / High Profit products
* High Sales / Low Profit products
* Low Sales / High Profit products
* Loss-making transactions

A high Sales value does not necessarily mean high profitability.

---

# 🔥 12. Correlation Analysis

A correlation matrix and heatmap are used to understand relationships between numerical variables.

Example:

```python
corr = df.select_dtypes(include=np.number).corr()

sns.heatmap(
    corr,
    annot=True,
    cmap="coolwarm"
)
```

This helps identify relationships between variables such as:

* Sales
* Profit
* Quantity
* Other numerical fields

---

# 🚨 13. Outlier Detection

The project uses the **IQR (Interquartile Range)** method to detect outliers.

### Formula

```text
IQR = Q3 - Q1

Lower Bound = Q1 - 1.5 × IQR

Upper Bound = Q3 + 1.5 × IQR
```

Outliers are analyzed for:

* Sales
* Profit
* Quantity

Outlier analysis is useful because unusually large transactions can significantly affect overall business KPIs.

---

# 👤 14. Customer Analysis

Customers are analyzed using:

* Total Sales
* Total Profit
* Number of Orders

The project identifies:

* Top customers by Sales
* Top customers by Profit
* High-value customers

These insights can support customer retention and cross-selling strategies.

---

# 💡 Business Insights

The project automatically generates business insights based on the actual dataset.

Examples of insights generated include:

* Highest-sales category
* Most profitable category
* Weakest category by profit
* Most profitable region
* Weakest region by profit
* Highest-profit product
* Lowest-profit product
* Percentage of loss-making transactions

---

# 🚀 Business Recommendations

Based on the analysis, the following recommendations can be considered:

### 1. Focus on Profitable Growth

Prioritize products and categories that generate both:

```text
High Sales + High Profit
```

Instead of optimizing revenue alone.

### 2. Investigate Loss-Making Products

Analyze products with negative profit to identify:

* Excessive discounts
* Low pricing
* High shipping costs
* Poor product economics
* Unprofitable product combinations

### 3. Review High-Sales / Low-Profit Products

Some products may generate significant revenue but contribute very little profit.

These products should be reviewed for pricing and discount optimization.

### 4. Improve Regional Profitability

Weak-performing states and regions should be investigated for:

* Shipping costs
* Pricing
* Discounts
* Product mix
* Customer demand

### 5. Customer Retention

Focus retention and cross-selling strategies on high-value customers.

### 6. Use Time-Series Trends

Monthly Sales and Profit trends can support:

* Inventory planning
* Marketing campaigns
* Demand forecasting
* Resource planning

### 7. Monitor Business KPIs

A recurring dashboard should track:

```text
Sales
Profit
Profit Margin
Orders
Customers
Quantity
Loss Rate
Average Order Value
```

---

# 📊 Visualizations Created

The project includes multiple visualizations:

### Distribution Charts

* Sales Distribution
* Profit Distribution

### Category Charts

* Sales by Category
* Profit by Category
* Sales by Sub-Category

### Geographic Charts

* Sales by Region
* Profit by Region
* Top States by Sales

### Customer Analysis

* Sales by Segment
* Profit by Segment

### Time-Series

* Monthly Sales Trend
* Monthly Profit Trend
* Year-wise Sales & Profit

### Product Analysis

* Top 10 Products by Sales
* Bottom Products by Profit

### Statistical Analysis

* Sales vs Profit Scatter Plot
* Correlation Heatmap
* Outlier Analysis

---

# ▶️ How to Run the Project

## 1. Clone the Repository

```bash
git clone https://github.com/yourusername/Superstore-Sales-EDA.git
```

## 2. Navigate to the Project

```bash
cd Superstore-Sales-EDA
```

## 3. Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn openpyxl xlrd jupyter
```

## 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

## 5. Open

```text
Superstore_EDA_Analysis.ipynb
```

Run all cells sequentially.

---

# 📦 Requirements

```text
pandas
numpy
matplotlib
seaborn
openpyxl
xlrd
jupyter
```

---

# 📌 Key Learning Outcomes

Through this project, the following Data Analytics skills are demonstrated:

* Data Cleaning
* Data Preprocessing
* Exploratory Data Analysis
* Descriptive Statistics
* KPI Development
* Data Visualization
* Time-Series Analysis
* Customer Analysis
* Product Analysis
* Geographic Analysis
* Correlation Analysis
* Outlier Detection
* Business Problem Solving
* Data-Driven Recommendations

---

# 💼 Skills Demonstrated

```text
Python
Pandas
NumPy
Matplotlib
Seaborn
EDA
Data Cleaning
Data Visualization
Business Analysis
Statistical Analysis
KPI Analysis
Data Storytelling
```

---

# 🔮 Future Improvements

The project can be extended with:

* Power BI Dashboard
* Customer Segmentation
* RFM Analysis
* Sales Forecasting
* Profit Forecasting
* Discount vs Profit Analysis
* CLV Analysis
* Advanced statistical testing
* Machine Learning-based sales forecasting
* Automated reporting

---

# 📊 Future Power BI Dashboard

The Python analysis can be converted into a Power BI dashboard containing:

### Page 1 — Executive Summary

* Total Sales
* Total Profit
* Profit Margin
* Total Orders
* Total Customers
* Sales Trend
* Profit Trend

### Page 2 — Product Analysis

* Category Performance
* Sub-Category Performance
* Top 10 Products
* Bottom 10 Products
* Profitability Analysis

### Page 3 — Customer Analysis

* Customer Segments
* Top Customers
* Customer Sales
* Customer Profit

### Page 4 — Geographic Analysis

* Region Performance
* State Performance
* Sales by State
* Profit by State

### Page 5 — Profitability

* Loss-Making Products
* Profit Margin
* Sales vs Profit
* Discount Analysis

---

# 👨‍💻 Author

**Afreen Tabassum**

Aspiring Data Analyst | Python | SQL | Power BI | Excel

### Core Interests

* Data Analytics
* Business Intelligence
* Data Visualization
* Business Analysis
* MIS Analytics

---



This project is intended for **educational and portfolio purposes**.
