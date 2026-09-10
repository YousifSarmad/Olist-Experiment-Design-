# Olist Seller-Offer Prioritization — A/B Experiment Design

A full experiment design (not just analysis) for a proposed change to Olist's marketplace: ranking competing sellers on the same product by predicted customer satisfaction instead of the current default rule.

## Business problem

Olist connects many small Brazilian sellers to large storefronts. When multiple sellers fulfill the same product, the platform currently has no satisfaction-aware way to choose between them. This project designs a randomized experiment to test whether a satisfaction-aware seller-ranking rule improves the customer experience.

## What this notebook covers

- **Target population definition** — orders touching a "multi-seller" product (~3.7% of products, but 12.8% of order line items and 13.6% of revenue — a meaningful, addressable slice).
- **Population profiling** — comparing the eligible population against the rest of the platform to confirm it's the right group to target.
- **Business case sizing** — quantifying how much seller choice actually matters (customers buying the identical product from different sellers can see nearly a half-star average rating gap).
- **Metric selection** — primary metric (average post-purchase review score), guardrail/secondary metrics.
- **Hypothesis, significance level, and power/sample-size calculation** — the experiment is comfortably powered (~6,300 customers per arm vs. a ~1,692 minimum requirement at the tightest margin of error).
- **Randomization strategy** — randomizing at the customer level (not order level) to avoid contamination from repeat buyers, and a balance check confirming no pre-existing bias between test and control (all metrics p > 0.05).
- **Handoff table** — a ready-to-use `customer_unique_id` + `group` assignment table for engineering.

## Stack

Python, pandas, NumPy, SciPy (stats), Matplotlib, Seaborn

## Data

Source: [Olist Brazilian E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (Kaggle). Not included in this repo — download and place the CSVs in a local `olist_data/` folder.

## Run it

```bash
pip install -r requirements.txt
jupyter notebook olist_experiment_design.ipynb
```
# Olist-Experiment-Design-
