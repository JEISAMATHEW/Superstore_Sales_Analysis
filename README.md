# 🛒 Superstore Sales Data Analysis with Basic Python

## 📌 Project Overview

The **Superstore Sales Data Analysis** is a pure Python project that reads a real retail sales dataset and answers practical business questions about sales, profitability, discounts, products, regions, and yearly trends.

The project follows a simple end-to-end analysis workflow:

**Load Data → Clean & Convert Data → Aggregate with Dictionaries → Rank & Classify → Business Insights**

It uses only built-in Python (the `csv` module, lists, dictionaries, loops, and functions), with no pandas, no NumPy, and no external libraries. The goal is to show that meaningful business analysis can be built from Python fundamentals.

## 🏬 Industry

**Retail — Office Supplies, Furniture, and Technology Products**

## 💡 Business Problem

Retail businesses need to know where their profit comes from and where it leaks away. Which regions and product categories earn the most? Which products sell the most? Which sub-categories lose money? Do heavy discounts help or hurt profit?

Answering these questions requires reading raw transaction records, converting text values into numbers, grouping the data, and turning the totals into clear recommendations.

This project uses basic Python to do exactly that.

## 🎯 Objective

Analyse the Superstore sales records using only core Python and evaluate:

- Total sales, total profit, and overall profit margin
- Profit performance across regions
- Profit performance across product categories and sub-categories
- Top-selling products by sales value
- The relationship between discount levels and profit
- Sales trends from 2014 to 2017

The project finishes with written key insights, recommendations, and limitations.

## ✨ Key Features

- Data loaded directly from CSV using Python's built-in `csv` module
- Row-by-row data cleaning with error handling
- Reusable function (`total_by`) that groups and totals any column
- Dictionary-based aggregation for region, category, sub-category, product, and year
- Top 5 product ranking using sorting with `lambda`
- Discount classification into four bands using `if / elif / else`
- Sub-category profitability ranking to find loss-making products
- Yearly sales trend extracted from date text
- Clear markdown sections, written insights, and a limitations note

## 📊 Dataset

- **Source:** Superstore Dataset (Kaggle) — https://www.kaggle.com/datasets/vivek468/superstore-dataset-final
- **File:** `Sample - Superstore.csv`
- **Size:** 9,994 rows and 21 columns
- **Coverage:** 2014 to 2017
- **Platform:** Kaggle Notebook

Each row represents one order line (one product within an order). Key columns used in this analysis:

| Column | Description |
|---|---|
| `Order Date` | Date of the order, stored as month/day/year text |
| `Region` | Sales region (South, West, Central, East) |
| `Category` | Product category (Furniture, Office Supplies, Technology) |
| `Sub-Category` | Detailed product group (for example Tables, Phones, Copiers) |
| `Product Name` | Name of the product sold |
| `Sales` | Sales value of the order line |
| `Quantity` | Units sold |
| `Discount` | Discount applied, as a fraction (0.2 means 20%) |
| `Profit` | Profit or loss on the order line |

The dataset was not uploaded to this repository. Download it from the Kaggle link above.

## 🧹 Data Handling & Validation

CSV files return every value as text, so the data must be cleaned and converted before any calculation.

The notebook demonstrates:

- Opening the file with `encoding="latin-1"` so special characters read correctly.
- Using `csv.DictReader` so each row is a dictionary with named columns.
- Converting `Sales`, `Discount`, and `Profit` to `float`, and `Quantity` to `int`.
- Removing extra spaces from text fields with `.strip()`.
- Wrapping conversions in `try / except` so a bad row is skipped instead of crashing the program.
- Counting skipped rows to validate the cleaning step.

**Result:** all 9,994 rows were converted successfully, with 0 rows skipped.

## 🧠 Python Concepts Demonstrated

- **File handling:** `open()`, `with` statement, and the `csv` module
- **Data types:** strings, integers, floats, and type conversion
- **Lists and dictionaries:** storing rows and building grouped totals
- **Loops:** `for` loops over rows and categories
- **Conditionals:** `if / elif / else` for discount bands
- **Functions:** reusable helpers (`total_by`, `sort_by_value`, `discount_band`)
- **Error handling:** `try / except` with `ValueError` and `KeyError`
- **Dictionary accumulation:** `dict.get(key, 0) + value` pattern
- **Sorting:** `sorted()` with `key=lambda` and `reverse=True`
- **Generator expressions:** `sum(row["Sales"] for row in ...)`
- **String methods:** `.strip()` and `.split("/")` for date parsing
- **Formatted output:** f-strings with number formatting such as `{value:,.2f}`

## 📈 Business Insights

- **Overall performance:** The business made a profit of 286,397 on sales of 2,297,201, a margin of about 12.5%.
- **Regions:** West (108,418) and East (91,523) generate most of the profit. Central (39,706) is the weakest region.
- **Categories:** Technology (145,455) and Office Supplies (122,491) drive profit. Furniture earns only 18,451.
- **Loss-making products:** Tables (-17,725), Bookcases (-3,473), and Supplies (-1,189) lose money. Tables and Bookcases explain Furniture's weak result.
- **Best sub-categories:** Copiers (55,618) and Phones (44,516) earn the most profit.
- **Top product:** The Canon imageCLASS 2200 Advanced Copier leads with 61,600 in sales, more than double the next product.
- **Discounts:** Average profit per order line is +66.90 with no discount, +26.50 at 1-20%, -77.86 at 21-40%, and -106.71 above 40%.
- **Sales trend:** Sales dipped about 3% in 2015, then grew to 733,215 in 2017.

## ✅ Recommendations

- Cap discounts at 20%, since heavy discounting is linked to losses.
- Review pricing and discounts on Tables and Bookcases.
- Investigate why the Central region earns the least profit.
- Keep investing in Copiers, Phones, and Accessories, the strongest profit makers.

## ⚠️ Limitations

Each row is an order line, not a full order. The analysis shows that heavy discounts and losses happen together, but it does not prove that discounts alone cause the losses.

## 🛠️ Technology / Tools

- **Python 3** — built-in features only (`csv` module)
- **Kaggle Notebook** — writing and running the analysis
- **Git & GitHub** — version control and project documentation

## 🔄 Project Workflow

```text
Business Questions
        ↓
Load CSV with csv.DictReader
        ↓
Clean Data & Convert Text to Numbers
        ↓
Group Totals with Dictionaries (total_by)
        ↓
Rank Products & Sub-Categories (sorted + lambda)
        ↓
Classify Discounts into Bands (if / elif / else)
        ↓
Yearly Trend from Date Text
        ↓
Key Insights, Recommendations & Limitations
```

## 📁 Project Structure

```text
python-sales-data-analyzer/
│
├── sales-data-analysis-basic-python.ipynb
├── Video.mp4
├── Superstore.csv
├── Image.png
└── README.md
```

| File | Contents |
|---|---|
| `sales-data-analysis-basic-python.ipynb` | Complete analysis with 8 sections, saved outputs, key insights, recommendations, and limitations |
| `Superstore.csv` | Superstore sales dataset (9,994 rows, 21 columns) used by the notebook |
| `Image.png` | Screenshot of the notebook output |
| `Video.mp4` | Walkthrough of the project |
| `README.md` | Project overview, objectives, Python concepts, insights, and run instructions |

## ▶️ How to Run

1. Open the Superstore dataset on Kaggle: https://www.kaggle.com/datasets/vivek468/superstore-dataset-final
2. Create a new Kaggle Notebook and attach the dataset using **Add Input**.
3. Import or copy the notebook `sales-data-analysis-basic-python.ipynb` into Kaggle.
4. Check that `file_path` in the load cell matches the path shown in your notebook's input panel.
5. Run the cells from top to bottom, in order, because each cell uses results from the earlier ones.
6. Review the output to see sales, profit, discount, and trend results.

> **Execution Tip:** If you get a file-not-found error, copy the exact path printed by the first cell into `file_path`. The name contains spaces and a hyphen: `Sample - Superstore.csv`.

## 🎯 Business Value

This type of analysis helps retail and analytics teams:

- Monitor overall sales, profit, and margin.
- Identify the most and least profitable regions and categories.
- Spot loss-making product groups early.
- Understand how discount levels affect profit.
- Track yearly sales growth.
- Turn raw transaction data into clear, actionable recommendations.

## 🚀 Future Enhancements

- Add monthly and quarterly sales trends.
- Analyse profit by customer segment and by state.
- Save the summary results to a text or CSV report using file writing.
- Add a simple menu so users can choose which report to see.
- Add charts using matplotlib.
- Rebuild the analysis with pandas and compare the code.
- Store the data in SQL and re-run the questions as queries.
- Build an interactive Tableau dashboard from the results.

## 📌 Project Deliverables

- Complete pure-Python analysis notebook with saved outputs
- Data cleaning and validation with error handling
- Reusable grouping and sorting functions
- Region, category, sub-category, product, discount, and yearly analysis
- Written key insights, recommendations, and limitations
- GitHub repository documentation
