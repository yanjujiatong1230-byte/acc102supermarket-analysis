# ACC102 Mini Project – Supermarket Sales Analysis

1. What This Project Does

This is an ACC102 Track 2 mini project. It provides a complete data analysis pipeline that integrates, cleans, and analyses wholesale vegetable sales data from four Kaggle CSV files. The project answers three business questions: which vegetable categories are most profitable, whether discounts effectively drive sales, and how daily sales fluctuate over time. The final output translates raw transaction data into interpretable visual insights for retail managers.


2. What Is Inside This Repository

| File | Description |
|------|-------------|
| `acc102_track2.ipynb` | The main Jupyter Notebook – contains all code, markdown explanations, and visual outputs |
| `annex1.csv` | Product catalogue (item code, name, category, loss rate, increase rate) |
| `annex2.csv` | Sales transactions – the main analysis dataset |
| `annex3.csv` | Wholesale prices by item and date |
| `annex4.csv` | Vegetable loss rates by item |
| `requirements.txt` | Python package dependencies |
| `sample_data/` | Small samples (first 5 rows) of each CSV for quick testing |
| `README.md` | This file |


3. Dataset Source

All CSV files were sourced from Kaggle:

Vegetable Wholesale Transaction Dataset 
[https://www.kaggle.com/datasets/yapwh1208/supermarket-sales-data](https://www.kaggle.com/datasets/yapwh1208/supermarket-sales-data)  
Access Date:24 April 2026

4. Key Variable Description

annex1.csv — Product Catalogue

| Variable | Type | Description |
|----------|------|-------------|
| Item Code | string | Unique product identifier |
| Item Name | string | Product name |
| Loss Rate (%) | numeric | Vegetable loss rate percentage |
| Increase Rate (%) | numeric | Price increase rate percentage |

annex2.csv — Sales Transactions

| Variable | Type | Description |
|----------|------|-------------|
| Date | date | Sale date (YYYY-MM-DD) |
| Time | string | Sale timestamp |
| Item Code | string | Product identifier (links to annex1.csv) |
| Quantity Sold (kilo) | numeric | Quantity sold in kg; negative values = returns |
| Unit Selling Price (RMB/kg) | numeric | Retail unit price in CNY per kg |
| Sale or Return | string | Transaction type: `sale` or `return` |
| Discount (Yes/No) | string | Whether a discount was applied (`Yes` / `No`) |

annex3.csv — Wholesale Prices

| Variable | Type | Description |
|----------|------|-------------|
| Date | date | Wholesale price date |
| Item Code | string | Product identifier (links to annex1.csv) |
| Wholesale Price (RMB/kg) | numeric | Wholesale price in CNY per kg |

annex4.csv — Vegetable Loss Rates

| Variable | Type | Description |
|----------|------|-------------|
| Item Code | string | Product identifier (links to annex1.csv) |
| Loss Rate (%) | numeric | Vegetable loss rate percentage |

---

5. Data File Availability

| File | Size | Included in Repo? | Notes |
|------|------|-------------------|-------|
| `annex1.csv` | Small | ✅ Yes | Product catalogue – uploaded directly |
| `annex2.csv` | ~878,000 rows | ❌ No | Exceeds GitHub's 25 MB recommended limit |
| `annex3.csv` | Large | ❌ No | Exceeds GitHub's 25 MB recommended limit |
| `annex4.csv` | Large | ❌ No | Exceeds GitHub's 25 MB recommended limit |

>The full dataset cannot be uploaded because it is too large, the following are provided as required by the ACC102 rubric:
> - ✅ Original source link(see Section3)
> - ✅ Access date(see Section3)
> - ✅ Key variable descriptions (see Section 4)
> - ✅ Setup instructions (see Section 6)
> - ✅ Small sample in `sample_data/` folder(see Section 7)


6.How to Set Up and Run

Step 1: Download the Dataset
Download `annex2.csv`, `annex3.csv`, and `annex4.csv` from Kaggle:  
[https://www.kaggle.com/datasets/yapwh1208/supermarket-sales-data]

Step 2: Place Files Correctly
Place all four CSV files (`annex1.csv`, `annex2.csv`, `annex3.csv`, `annex4.csv`) in the same folder as `acc102_track2.ipynb`.
> `annex1.csv` is already included in this repository. The other three files must be downloaded manually.

Step 3: Install Required Packages
Open a terminal in the project folder and run:
```bash
pip install -r requirements.txt

Step 4: Run the Notebook
    Open `acc102_track2.ipynb` in Jupyter Notebook, JupyterLab, or VS Code.
In the menu, click **Kernel → Restart & Run All Cells**.
The notebook will run from start to finish and display all outputs.

7.Small Sample Data

A small sample (first 5 rows) of each CSV file is provided in the `sample_data/` folder for quick testing. For full analysis, download the complete datasets from Kaggle.

 `sample_data/annex1_sample.csv`

| Item Code | Item Name | Loss Rate (%) | Increase Rate (%) |
|-----------|-----------|---------------|-------------------|
| 102900005115168 | Niushou Shengcai | 4.39 | 10.46 |
| 102900005115199 | Sichuan Red Cedar | 10.46 | 10.80 |
| 102900005115250 | Xixia Black Mushroom (1) | 10.80 | 0.18 |
| 102900005115625 | Local Xiaomao Cabbage | 0.18 | 8.78 |
| 102900005115748 | White Caitai | 8.78 | 15.25 |

 `sample_data/annex2_sample.csv`

| Date | Time | Item Code | Quantity Sold (kilo) | Unit Selling Price (RMB/kg) | Sale or Return | Discount (Yes/No) |
|------|------|-----------|---------------------|-----------------------------|----------------|-------------------|
| 2020-07-01 | 09:15:07 | 102900005117056 | 0.396 | 7.6 | sale | No |
| 2020-07-01 | 09:17:27 | 102900005115960 | 0.849 | 3.2 | sale | No |
| 2020-07-01 | 09:17:33 | 102900005117056 | 0.409 | 7.6 | sale | No |
| 2020-07-01 | 09:19:45 | 102900005115823 | 0.421 | 10.0 | sale | No |
| 2020-07-01 | 09:20:23 | 102900005115908 | 0.539 | 8.0 | sale | No |

 `sample_data/annex3_sample.csv`

| Date | Item Code | Wholesale Price (RMB/kg) |
|------|-----------|--------------------------|
| 2020-07-01 | 102900005115762 | 3.88 |
| 2020-07-01 | 102900005115779 | 6.72 |
| 2020-07-01 | 102900005115786 | 3.19 |
| 2020-07-01 | 102900005115793 | 9.24 |
| 2020-07-01 | 102900005115823 | 7.03 |



8.Output

All analysis results are displayed at the end of the notebook:
- A bar chart comparing sales and profit by vegetable category
- A bar and pie chart showing the impact of discounts
- A daily sales trend line chart

These outputs provide direct, visual answers to the business questions posed at the start.
