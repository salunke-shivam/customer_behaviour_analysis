# Customer Shopping Behavior Analysis 🛒📊

An end-to-end data science and analytics project designed to uncover actionable business insights from retail transaction data. This project encompasses data cleaning, feature engineering, database integration, and advanced SQL querying to analyze customer purchasing patterns and drive strategic decision-making.

## 📑 Table of Contents
- [Project Overview](#project-overview)
- [Tech Stack](#tech-stack)
- [Project Workflow](#project-workflow)
- [Key Business Insights](#key-business-insights)
- [File Structure](#file-structure)
- [Setup and Installation](#setup-and-installation)
- [Author](#author)

## 📖 Project Overview
Understanding customer behavior is critical for optimizing revenue, marketing, and inventory strategies. This project analyzes a dataset of 3,900 customer purchases to evaluate the impact of subscriptions, shipping preferences, demographics, and product ratings on overall sales. 

The analysis is divided into two phases:
1. **Data Preprocessing & ETL (Python):** Cleaning the dataset, handling missing values, engineering new business-centric features, and loading the processed data into relational databases.
2. **Data Analysis (SQL):** Writing complex queries to segment customers, rank products, and calculate revenue metrics.

## 🛠️ Tech Stack
* **Language:** Python 3, SQL
* **Libraries:** `pandas`, `SQLAlchemy`, `psycopg2`, `pymysql`, `pyodbc`
* **Databases Supported:** PostgreSQL, MySQL, MS SQL Server
* **Tools:** Jupyter Notebook, Git/GitHub, PowerPoint (for presentation)

## 🔄 Project Workflow
### 1. Data Cleaning & Feature Engineering (`Customer_Shopping_Behavior_Analysis.ipynb`)
* **Missing Value Imputation:** Imputed missing `Review Rating` values using the median rating of their respective product categories.
* **Data Standardization:** Converted column names to `snake_case` for SQL compatibility.
* **Feature Engineering:**
  * Created an `age_group` column (Young Adult, Adult, Middle-aged, Senior) using quantile binning.
  * Mapped text-based purchase frequencies into a numerical `purchase_frequency_days` column for easier time-series analysis.
  * Dropped redundant columns (e.g., `promo_code_used` which perfectly correlated with `discount_applied`).
* **Database Integration:** Automated the connection and data loading process to PostgreSQL, MySQL, and MS SQL Server using `SQLAlchemy`.

### 2. Exploratory Data Analysis (`customer_behavior_sql_queries.sql`)
Utilized advanced SQL concepts including **CTEs, Window Functions, and Aggregations** to answer strategic business questions:
* Revenue comparisons across demographics and shipping types.
* Customer segmentation (New, Returning, Loyal) based on purchase history.
* Identification of top-rated and highly discounted products.
* Subscription impact on total revenue and average spend.

## 💡 Key Business Insights
Based on the SQL analysis and strategic presentation:
* **Revenue by Gender:** Female customers generated slightly higher total revenue than male customers, indicating a potential avenue for optimized gender-based marketing.
* **The Subscription Advantage:** Subscribed customers account for **78% of the total revenue share** and spend 68% more on average compared to non-subscribers.
* **Customer Segmentation:** The customer base consists of 50% New buyers, 35% Returning buyers, and 15% Loyal (High-value) buyers.
* **Shipping Preferences:** Customers utilizing Express Shipping spend on average **$65 per transaction** (12% more) compared to those using Standard Shipping ($58).
* **Top Performers:** 'Blouse', 'Dress', and 'Shirt' consistently received the highest customer satisfaction ratings (4 to 5 stars).

## 📂 File Structure
```text
├── Customer_Shopping_Behavior_Analysis.ipynb  # Python ETL and preprocessing script
├── customer_behavior_sql_queries.sql          # 10 advanced SQL queries for business analysis
├── Customer-Shopping-Behavior-Analysis.pptx   # Executive presentation of insights and recommendations
├── customer_shopping_behavior.csv             # Raw dataset (ensure this is in the root directory)
└── README.md                                  # Project documentation


```
🚀 Setup and Installation
Prerequisites
Python 3.8+
A running instance of PostgreSQL, MySQL, or MS SQL Server.


Installation Steps
Clone the repository:
```Bash
git clone [https://github.com/yourusername/customer-behavior-analysis.git](https://github.com/yourusername/customer-behavior-analysis.git)
cd customer-behavior-analysis
```
Install required Python packages:
```Bash
pip install pandas sqlalchemy psycopg2-binary pymysql pyodbc
```
Database Configuration:
Open the Jupyter Notebook (Customer_Shopping_Behavior_Analysis.ipynb) and navigate to the database connection cells. Update the connection strings with your local database credentials:
```Python
username = "your_username"
password = "your_password"
host = "localhost"
port = "5432" # or 3306 for MySQL / 1433 for SQL Server
database = "customer_behavior"
```
Run the ETL Pipeline:
Execute the Jupyter Notebook to clean the data and push the customer table to your local database.
Run SQL Queries:
Open your preferred SQL client (e.g., pgAdmin, DBeaver, SQL Server Management Studio), connect to your database, and execute the queries in customer_behavior_sql_queries.sql to view the insights.
