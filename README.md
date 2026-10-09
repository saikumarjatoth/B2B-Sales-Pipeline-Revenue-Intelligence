[README (1).md](https://github.com/user-attachments/files/33248088/README.1.md)
# B2B Sales Pipeline & Revenue Intelligence

Analyze B2B opportunity data with SQL and prepare performance views for Tableau.

## Project highlights

- Analyzed **8,800 opportunities**.
- Measured a **63.15% closed-won rate** and **$10.01M won revenue**.
- Compared performance across **30 sales agents**, with closed-opportunity win rates ranging from **51% to 68%**.
- Prepared dashboard metrics for **2,089 active deals**, **$3.51M GTX Pro revenue**, and a **64.84% MG Special win rate**.

*These are the project figures supplied for the resume. The notebooks recalculate metrics from the dataset you provide; results depend on using the same source data and metric definitions.*

## Tools

- SQL (CTEs, aggregations, window functions)
- Python (pandas, SQLite)
- Tableau (dashboard layer)

## Repository files

- `01_sql_pipeline_analysis.ipynb` — data checks, SQL KPIs, agent ranking, and product performance.
- `02_tableau_dashboard_prep.ipynb` — exports analysis-ready tables for Tableau.

## Data setup

Place your source file at `data/sales_pipeline.csv`. The notebooks expect these canonical column names:

| Column | Meaning |
|---|---|
| `opportunity_id` | Unique opportunity identifier |
| `sales_agent` | Sales agent assigned to the opportunity |
| `product` | Product associated with the opportunity |
| `stage` | Deal stage; use `Won` and `Lost` for closed deals |
| `revenue` | Numeric opportunity revenue |
| `close_date` | Close date (optional; needed for monthly trend analysis) |

If your file uses different headers, rename them in the data-loading cell before running the analysis. Keep one row per opportunity and ensure revenue is numeric. Active deals are treated as stages other than `Won` or `Lost`; win rate is `Won / (Won + Lost)`.

The source dataset is not included in this repository. Only upload data you are allowed to share, and remove confidential customer or company information first.

## Run the notebooks

1. Create a `data/` folder in the repository and add `sales_pipeline.csv`.
2. Install dependencies: `pip install pandas jupyter`
3. Open the notebooks in Jupyter or Google Colab and run cells from top to bottom.
4. In the second notebook, generated CSVs are saved to `data/tableau_exports/`.
5. Connect Tableau to those CSVs and build KPI cards, an agent-performance ranking, product comparison, and (if dates are available) a monthly trend.

## Metric definitions

- **Closed win rate:** won opportunities divided by all closed opportunities.
- **Won revenue:** sum of `revenue` for opportunities with stage `Won`.
- **Active deals:** opportunities whose stage is neither `Won` nor `Lost`.
- **Product win rate:** won opportunities for a product divided by that product's closed opportunities.
