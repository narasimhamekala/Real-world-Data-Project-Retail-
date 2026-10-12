# Real-world Data Project: Retail Sales Analysis & Profit Prediction

**Domain:** Retail | **Language:** Python | **Task:** End-to-end data analysis + prediction

## Problem
Which products, regions and pricing decisions drive profit, and can we predict whether an order will be profitable?

## Project structure
```
Task4_RealWorld_Data_Project/
├── analysis.ipynb      # full code: cleaning, EDA, modelling, findings
├── data/retail_sales.csv
├── visuals/            # all charts (PNG)
├── report.pdf          # written report with charts and conclusions
└── README.md
```

## Workflow
1. **Cleaning:** removed 60 duplicates, filled 215 missing cells, capped 279 extreme sales values.
2. **EDA:** trends, category / sub-category / region performance, discount impact, correlations.
3. **Modelling:** Logistic Regression and Random Forest predict whether an order is profitable.
   Best accuracy 94.9% (baseline 78.5%).

## Key findings
- Total sales were $2,665,359 with $453,958 profit, an overall margin of 17.0%.
- December is the strongest month, contributing 14.0% of all sales (seasonal peak).
- Office Supplies has the best margin (23.7%); Furniture has the weakest (5.8%).
- Sub-category 'Copiers' earns the most profit ($145,530); 'Furnishings' earns the least ($3,035).
- Region South has the best margin (18.8%); Central the weakest (13.3%).
- Discounts of 40% or more make up 20.2% of orders and produced a net profit of -$49,384 in total (a loss); discount and margin correlate at -0.92.
- Random Forest predicts whether an order is profitable with 94.9% accuracy (baseline 78.5%) and AUC 0.988.
- The most influential features were: Discount, Sales, Month.

## Recommendations
- Cap discounts at roughly 30% and require approval above that level, since deeper discounts erase the margin.
- Review pricing and discounting in the weakest segments (Furniture, Central region, and 'Furnishings').
- Build inventory and marketing capacity ahead of December and the Q4 season.
- Use the profit-prediction model as a pre-approval check: flag discounted orders likely to lose money before they are confirmed.

## How to run
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook analysis.ipynb
```
(Or upload the folder to Google Colab and run all cells.)

## Data note
The included dataset is a simulated Superstore-style retail dataset. To use a real one, download the Kaggle "Superstore Sales" dataset, save it as `data/retail_sales.csv` (columns: Order Date, Ship Mode, Segment, Region, Category, Sub-Category, Sales, Quantity, Discount, Profit) and re-run the notebook.
