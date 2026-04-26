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

https://www.kaggle.com/datasets/yapwh1208/supermarket-sales-data
Due to GitHub's file size limits, the large raw data files (annex2.csv, annex3.csv, etc.) are not uploaded here. Please download them directly from the link above to run the analysis.


 3. How to Use

1. Download or clone this repository to your local machine.
2. Make sure all four CSV files are in the same folder as `acc102_track2.ipynb`.
3. Open the notebook in Jupyter Notebook, JupyterLab, or VS Code.
4. Install the necessary packages if not already installed:
5. In the notebook menu, click Kernel → Restart & Run All Cells.
6. The notebook will run from start to finish and display all outputs.

## Output

All analysis results are displayed at the end of the notebook:
- A bar chart comparing sales and profit by vegetable category
- A bar and pie chart showing the impact of discounts
- A daily sales trend line chart

These outputs provide direct, visual answers to the business questions posed at the start.