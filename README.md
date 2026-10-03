# Quick Commerce Delivery Performance & Customer Satisfaction
### Blinkit vs Swiggy Instamart vs JioMart: an end-to-end data analytics case study (simulated data)

> **Disclaimer:** This project uses a **simulated dataset**. All patterns (delivery speeds, delay rates, refund behavior, city effects) are assumptions, not real performance of Blinkit, Swiggy Instamart or JioMart. The goal is to demonstrate a complete analytics workflow: audit, clean, explore, quantify, model and recommend.

---

## 1. Business Problem

**Stakeholder:** Head of Operations at a quick-commerce company.

The Head of Operations needs to understand which platforms, cities, time slots and product categories have the most late deliveries, how those delays affect customer ratings and refund requests, and what they cost in revenue, so they can decide where to focus operational fixes first.

## 2. Key Questions

### Core questions
| # | Question | Main columns |
| --- | --- | --- |
| Q1 | Which platform and city have the highest late-delivery rate? | `Platform`, `City`, `Delayed` |
| Q2 | At which hours and weekdays do delays peak? | `Order Date & Time`, `Delayed` |
| Q3 | What factors (distance, basket size, rush hour) are linked to longer delays? | `Delivery Distance (km)`, `Order Value (INR)`, `Delivery Delay (Minutes)` |
| Q4 | Which product categories drive the most orders, and which have the highest late and refund rates? | `Product Category`, `Delayed`, `Refund Requested` |
| Q5 | Do delays lead to lower ratings and more refund requests? | `Delivery Delay (Minutes)`, `Service Rating`, `Refund Requested` |

### Extended questions
| # | Question | Main columns |
| --- | --- | --- |
| Q6 | What types of complaints are most common, and where do they cluster? | `Customer Feedback`, `Platform`, `Product Category` |
| Q7 | Is there a tipping point in delay minutes after which ratings drop sharply? | `Delivery Delay (Minutes)`, `Service Rating` |
| Q8 | Which platform is fastest on average, and which most reliably meets its promise? | `Delivery Time (Minutes)`, `Promised SLA (Minutes)`, `Delayed`, `Platform` |
| Q9 | Which city and time-slot combinations are the worst hot spots? | `City`, hour, `Delayed` |
| Q10 | What is the estimated revenue at risk from refund requests, by platform and category? | `Refund Requested`, `Order Value (INR)` |
| Q11 | After a late or refunded order, do customers reorder less often? | `Customer ID`, `Order Date & Time`, `Delayed`, `Refund Requested` |

### Advanced analysis
| # | Task | Purpose |
| --- | --- | --- |
| A1 | Statistical tests (chi-square / z-test) on platform and city differences | Confirm differences are significant, not just visible |
| A2 | Predictive model for late delivery (logistic regression, random forest) with feature importance | Identify which factors matter most and flag high-risk orders |

Comparisons use **rates (percentages)**, not raw counts, so larger cities and categories are not unfairly penalized. Where a tested relationship is absent, it will be reported as such.

---

## 3. Data

### Original source
Kaggle, Blinkit, Swiggy & JioMart Orders Dataset by danishshaikh18 (synthetic quick-commerce order data), kaggle.com/datasets/danishshaikh18/blinkit-swiggy-and-jiomart-orders-dataset (Apache 2.0). 100,000 rows, 11 columns.

### Why a second dataset?
An audit of the Kaggle file found it could not support the questions above:
- `Order Date & Time` contains only a time fragment (no date or hour), so time analysis is impossible.
- `Delivery Delay` is a Yes/No flag, so delay length cannot be measured.
- About 46% of orders request refunds, which is implausible.
- Only 13 distinct feedback comments exist.

### Simulated dataset (used for the analysis)
`data/raw/quick_commerce_orders_simulated.csv` was generated from the Kaggle file using `scripts/generate_realistic_data.py` (fixed random seed, fully reproducible). It has 100,800 rows and 16 columns. It adds realistic timestamps, delay minutes, city, payment method, distance and promised delivery time, and includes deliberate data-quality issues for the cleaning step. The original file is kept unchanged in `data/raw/`.

| Column | Description |
| --- | --- |
| Order ID, Customer ID | Identifiers |
| Platform, City | Where the order was placed |
| Order Date & Time | Order timestamp (Jan to Mar 2025) |
| Product Category, Order Value (INR) | What and how much |
| Payment Method | UPI, Card, Cash on Delivery, Wallet |
| Delivery Distance (km) | Distance to customer |
| Promised SLA (Minutes) | Delivery time promised |
| Delivery Time (Minutes) | Actual delivery time |
| Delivery Delay (Minutes), Delayed | Minutes beyond promise, and Yes/No flag |
| Service Rating | 1 to 5 (about 22% missing) |
| Customer Feedback | Free text (about 55% blank) |
| Refund Requested | Yes/No |

---

## 4. Approach

- [x] Step 1: Understand the data
- [x] Step 2: Define the problem and questions
- [ ] Step 3: Data cleaning
- [ ] Step 4: Exploratory data analysis (Q1 to Q9)
- [ ] Step 5: Business impact and customer behavior (Q10, Q11)
- [ ] Step 6: Statistical tests and predictive model (A1, A2)
- [ ] Step 7: Insights and recommendations
- [ ] Step 8: Final report / presentation

## 5. Tools

Python (pandas, NumPy, matplotlib, seaborn, scipy, scikit-learn), Jupyter Notebook, Git/GitHub.

## 6. Repository Structure

```
quick-commerce-delivery-analysis/
├── data/
│   ├── raw/        # original Kaggle CSV + simulated CSV (never edited)
│   └── cleaned/    # cleaned output
├── notebooks/      # numbered analysis notebooks
├── scripts/        # generate_realistic_data.py
├── visuals/        # charts used in the report
├── report/         # final write-up
└── README.md
```

## 7. Data Quality Notes
_(Fill in during Step 3: issues found and how each was handled.)_

## 8. Key Findings
_(Fill in after the analysis. All findings apply to simulated data.)_

## 9. Recommendations
_(Fill in after the analysis.)_

## 10. Limitations
- Data is simulated; patterns reflect assumptions, not real company performance.
- Relationships found may partly reflect how the simulation was designed.
- Ratings are missing for about 22% of orders; results may not represent non-raters.

## Author
_Your name · LinkedIn · GitHub_