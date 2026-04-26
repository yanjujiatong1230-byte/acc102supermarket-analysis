# ACC102 Mini Project – Supermarket Sales Analysis

1. What This Project Does

This is an ACC102 Track 2 mini project. It provides a complete data analysis pipeline that integrates, cleans, and analyses wholesale vegetable sales data from four Kaggle CSV files. The project answers three business questions: which vegetable categories are most profitable, whether discounts effectively drive sales, and how daily sales fluctuate over time. The final output translates raw transaction data into interpretable visual insights for retail managers.

2. What Is Inside This Repository

| File | Description |
|------|-------------|
| `acc102_track2.ipynb` | The main Jupyter Notebook – contains all code, markdown explanations, and visual outputs |
| `annex1.csv` | Product catalogue (item code, name, category) |
| `annex2.csv` | Sales transactions (~878,000 rows) – the main training/analysis dataset |
| `annex3.csv` | Wholesale prices by item and date |
| `annex4.csv` | Vegetable loss rates by item |

All four CSV files were sourced from Kaggle (Vegetable Wholesale Transaction Dataset, accessed 24 April 2026). They serve as the data foundation that the notebook reads, merges, cleans, and analyses.

###Due to GitHub's file size limits, the large raw data files (annex2.csv, annex3.csv, etc.) are not uploaded here. Please download them directly from the link above to run the analysis.
·https://www.kaggle.com/datasets/yapwh1208/supermarket-sales-data
·Access Date:24 April,2026
·Key Variable Description
The data consists of three CSV files:
| `annex2.csv` |:`sales_record.csv`
| Variable | Type | Description |
|----------|------|-------------|
| Date | date | Sale date |
| Time | string | Sale time (H:MM:SS; hours >24 indicate next day) |
| Item Code | string | Product identifier |
| Quantity Sold (kilo) | numeric | Quantity sold (kg, inferred) |
| Unit Selling Price (RMB/kg) | numeric | Retail unit price (CNY/kg) |
| Sale or Return | string | Transaction type: "sale" or "return" |
| Discount (Yes/No) | string | Whether a discount was applied |

| `annex3.csv` |:`wholesale_price.csv`
| Variable | Type | Description |
|----------|------|-------------|
| Date | date | Wholesale transaction date (YYYY/M/D) |
| Item Code | string | Product identifier (matches product_info) |
| Wholesale Price (RMB/kg) | numeric | Wholesale price in CNY per kilogram |

| `annex4.csv` |:`product_info.csv`
| Variable | Type | Description |
|----------|------|-------------|
| Item Code | string | Unique product identifier |
| Item Name | string | Product name (in Chinese) |
| Loss Rate (%) | numeric | Loss rate percentage |

·Setup Instructions：
The three CSV files were downloaded from a Kaggle dataset. To use the provided sample or replicate the analysis:
1).Obtain the full dataset (optional) 
   - Visit the Kaggle dataset page
   -Download the files: `product_info.csv`, `wholesale_price.csv`, `sales_record.csv`.
2). Place the files  
   - Create a project folder.
   - Put the three CSV files directly into that folder.
3). Load the data in Python
   ```python
   import pandas as pd
   products = pd.read_csv('product_info.csv')
   wholesale = pd.read_csv('wholesale_price.csv')
   sales = pd.read_csv('sales_record.csv')

·Small Sample (first 5 rows of each file)
`product_info.csv`
| Item Code | Item Name | Loss Rate (%) | Increase Rate (%) |
|-----------|-----------|---------------|-------------------|
| 102900005115168 | Niushou Shengcai | 4.39 | 10.46 |
| 102900005115199 | Sichuan Red Cedar | 10.46 | 10.8 |
| 102900005115250 | Xixia Black Mushroom (1) | 10.8 | 0.18 |
| 102900005115625 | Local Xiaomao Cabbage | 0.18 | 8.78 |
| 102900005115748 | White Caitai | 8.78 | 15.25 |

 `wholesale_price.csv`
| Date | Item Code | Wholesale Price (RMB/kg) |
|------|-----------|--------------------------|
| 2020/7/1 | 102900005115762 | 3.88 |
| 2020/7/1 | 102900005115779 | 6.72 |
| 2020/7/1 | 102900005115786 | 3.19 |
| 2020/7/1 | 102900005115793 | 9.24 |
| 2020/7/1 | 102900005115823 | 7.03 |

 `sales_record.csv`
| Date | Time | Item Code | Quantity | Sold (kilo) | Unit Selling Price (RMB/kg) | Sale 
|------|------|-----------|----------|-------------|-----------------------------|
or Return | Discount (Yes/No) |
----------|-------------------|
| 2020/7/1 | 15:07:9 | 102900005117056 | 0.396 | 7.6 | sale | No |
| 2020/7/1 | 17:27:3 | 102900005115960 | 0.849 | 3.2 | sale | No |
| 2020/7/1 | 19:45:5 | 102900005115823 | 0.409 | 7.6 | sale | No |
| 2020/7/1 | 20:23:7 | 102900005115908 | 0.421 | 10.8 | sale | No |
| 2020/7/1 | 21:55:6 | 102900005117056 | 0.539 | 8.4 | sale | No |

3. How to Use

1. Download or clone this repository to your local machine.
2. Make sure all four CSV files are in the same folder as `acc102_track2.ipynb`.
3. Open the notebook in Jupyter Notebook, JupyterLab, or VS Code.
4. Install the necessary packages if not already installed:
5. In the notebook menu, click Kernel → Restart & Run All Cells.
6. The notebook will run from start to finish and display all outputs.

Output

All analysis results are displayed at the end of the notebook:
- A bar chart comparing sales and profit by vegetable category
- A bar and pie chart showing the impact of discounts
- A daily sales trend line chart

These outputs provide direct, visual answers to the business questions posed at the start.
