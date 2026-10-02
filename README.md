# Quick Commerce Delivery Performance & Customer Satisfaction
### Blinkit vs Swiggy vs JioMart: a data analytics case study

## Business Problem

Quick-commerce platforms compete on speed and reliability. This case study acts as an analyst brief: **which platform delivers best, what drives customer dissatisfaction and refunds, and what should be fixed first?**

## Key Questions

1. How do the three platforms compare on delivery time, delay rate and service rating?
2. How do delays affect customer ratings and refund requests?
3. Which product categories have the highest refund rates?
4. Does order value relate to delays, ratings or refunds?
5. What do customers complain about most (from feedback text)?

## Dataset

| Item | Detail |
| --- | --- |
| Rows | 100,000 orders |
| Columns | 11 |
| Nature | Synthetic (simulated) quick-commerce order data |
| License | Apache 2.0 |

**Columns:** Order ID, Customer ID, Platform, Order Date & Time, Delivery Time (Minutes), Product Category, Order Value (INR), Customer Feedback, Service Rating, Delivery Delay, Refund Requested.

**Source:** Kaggle, Blinkit, Swiggy & JioMart Orders Dataset by danishshaikh18 (synthetic quick-commerce order data), kaggle.com/datasets/danishshaikh18/blinkit-swiggy-and-jiomart-orders-dataset.

> **Limitation:** The data is synthetic, so findings describe this dataset and should not be read as real-world performance of these companies.

## Approach

- [ ] Step 1: Understand the data
- [ ] Step 2: Define the problem and questions
- [ ] Step 3: Data cleaning
- [ ] Step 4: Exploratory data analysis
- [ ] Step 5: Key insights
- [ ] Step 6: Recommendations
- [ ] Step 7: Final report / presentation

## Tools

_(Fill in: Python / pandas / Excel / SQL / Power BI, etc.)_

## Repository Structure

```
quick-commerce-delivery-analysis/
├── data/
│   ├── raw/
│   │   └── ecommerce_delivery_analytics.csv  # source data; never edit
│   └── cleaned/
│       └── orders_cleaned.csv                # generated in Step 3
├── notebooks/
│   ├── 01_data_understanding.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_eda.ipynb
│   └── 04_insights.ipynb
├── visuals/                                     # PNG charts for the report
├── report/
│   └── final_report.md
└── README.md
```

The source CSV is kept at the repository root for compatibility and copied
unchanged to `data/raw/` as the canonical analysis input. Generate
`data/cleaned/orders_cleaned.csv` from the data-cleaning notebook in Step 3.

## Data Quality Notes

_(Fill in during Step 3: issues found and how they were handled.)_

## Key Findings

_(Fill in after Step 5.)_

## Recommendations

_(Fill in after Step 6.)_

## Author

_Your name · LinkedIn · GitHub_
