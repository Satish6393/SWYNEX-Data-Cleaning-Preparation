# SWYNEX Data Cleaning & Preparation

## Project Overview

This project was completed as part of the SWYNEX Technologies Data Analyst Internship.

The project focuses on cleaning and preparing the UCI Online Retail II dataset for analysis and dashboard development. The dataset contains retail transaction records from 2009 to 2011.

The cleaned dataset was further used to develop an interactive Power BI dashboard for sales analysis.

---

## Internship Task

**Task 1: Data Cleaning & Preparation**

The objective was to:

- Identify missing values
- Identify duplicate records
- Check incorrect data types
- Identify inconsistent or non-standard records
- Clean and prepare the dataset
- Create a final analysis-ready dataset

---

## Dataset

**Dataset:** Online Retail II

**Source:** UCI Machine Learning Repository

The dataset contains retail transactions with the following fields:

- Invoice
- StockCode
- Description
- Quantity
- InvoiceDate
- Price
- Customer ID
- Country

The original Excel workbook contained two sheets:

- Year 2009-2010
- Year 2010-2011

After combining both sheets:

**Original Records:** 1,067,371  
**Original Columns:** 8

---

## Tools & Technologies

- Python
- Pandas
- Jupyter Notebook
- Microsoft Excel
- Power BI
- GitHub

---

## Data Cleaning Process

### 1. Combining Dataset

The two yearly sheets were combined into a single DataFrame for consistent analysis.

### 2. Duplicate Records

Exact duplicate rows were identified using Pandas.

- Original records: 1,067,371
- Exact duplicate rows removed: 34,335

The duplicate records were removed using `drop_duplicates()`.

### 3. Missing Values

Initial missing values were identified in:

- Description: 4,382
- Customer ID: 243,007

After the cleaning process, missing Customer IDs remained in the dataset.

These records were retained because removing them would also remove otherwise valid transaction records.

### 4. Negative Price Records

Five records contained negative prices.

These records were identified as accounting adjustment entries with the description:

`Adjust bad debt`

They were removed because they do not represent normal retail sales transactions.

### 5. Zero Price Records

Records with `Price = 0` were investigated separately.

After duplicate removal and negative-price filtering, 6,014 zero-price records remained.

These records were removed from the main analysis dataset because they do not contribute to sales revenue and included non-standard operational or adjustment records.

### 6. Data Type and Text Cleaning

The following fields were cleaned and standardized:

- Customer ID converted to nullable integer type
- Invoice converted to string
- StockCode converted to string
- Description converted to string
- Country converted to string
- Leading/trailing spaces removed from text fields

### 7. Sales Amount

A new calculated column was created:
SalesAmount = Quantity * Price

This column was used as the primary sales metric in Power BI.

### 8. Final Dataset

After cleaning:

Final Records: 1,027,017
Final Columns: 9

The final dataset contains the original transaction fields plus:

SalesAmount

The cleaned dataset is saved as:

online_retail_II_cleaned.csv

### 9. Power BI Dashboard

The cleaned dataset was imported into Power BI to create an interactive sales dashboard.

KPI Cards
Total Sales
Total Quantity
Total Transactions
Total Customers
Dashboard Visuals
Monthly Sales Trend
Annual Sales
Top 10 Customers by Sales
Top 10 Products by Sales
Sales by Country
Top 10 Countries by Sales
Interactive Filters
Date
Country
Product

The dashboard allows users to filter the analysis dynamically and observe changes across KPIs and visualizations.

Dashboard File

Power BI dashboard:

SWYNEX_Online_Retail_Sales_Dashboard.pbix

### 10. Project Structure

SWYNEX-Data-Cleaning-Preparation/
│
├── data/
│   ├── raw/
│   │   └── online_retail_II.xlsx
│   │
│   └── cleaned/
│       └── online_retail_II_cleaned.csv
│
├── notebook/
│   └── SWYNEX_Task1_Data_Cleaning.ipynb
│
├── dashboard/
│   └── SWYNEX_Online_Retail_Sales_Dashboard.pbix
│
├── README.md
│
└── requirements.txt

### 11. Requirements

Main Python libraries used:

pandas
numpy
openpyxl
jupyter

Install dependencies using:

pip install -r requirements.txt


### 12. Project Outcome

The project demonstrates an end-to-end data preparation workflow:

Raw Dataset → Data Profiling → Data Cleaning → Data Validation → Feature Creation → Clean Dataset → Power BI Dashboard

The resulting dataset is prepared for further business and sales analysis.

### 13. Internship

Organization: SWYNEX Technologies
Domain: Data & AI
Role: Data Analyst Intern
Project: Data Cleaning, Preparation & Sales Dashboard

### 14. Project Files

### Cleaned Dataset

The cleaned dataset is available here:

[Download Cleaned Dataset](https://drive.google.com/file/d/1kDZavS-xPI6EUdHfP9Yxyy5ckbuvCUl3/view?usp=sharing)

### Power BI Dashboard

The Power BI dashboard file is available here:

[Download Power BI Dashboard](https://drive.google.com/file/d/1BW3VHNRo9OWxQRYeLRhvpfKjWzH8p1r_/view?usp=sharing)

### Jupyter Notebook

The complete data cleaning process is available in this repository:

`notebook/SWYNEX_Online_Retail_Sales_Dashboard.ipynb`
