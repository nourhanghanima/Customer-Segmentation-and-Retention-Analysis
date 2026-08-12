# Which Customers Should We Prioritize for a Retention Campaign?

RFM segmentation and cohort retention analysis on UK online retail transaction data, built entirely
in R (tidyverse). Answers two questions: **which customer segments matter most, and when does the
business actually lose people?**
**[Read the full report](customer_segmentation_retention.html)** · Analysis in
[`customer_segmentation_retention.Rmd`](customer_segmentation_retention.Rmd)

## Summary

- Built customer-level RFM (Recency, Frequency, Monetary) profiles for ~5,900 customers from
  ~805,000 cleaned transaction lines, and scored/segmented them by quintile.
- A small "Long time regular" segment (~1 in 5 customers) generates the large majority of total
  revenue — a sharp Pareto concentration.
- Built monthly acquisition cohorts and tracked retention over time with a cohort heatmap; most
  churn happens within the first month after a customer's initial purchase, after which retention
  stabilizes into a smaller, steadier core.
- **Recommendation:** target retention spend at the "At Risk" segment — high-value customers who've
  gone quiet — rather than spreading it evenly or chasing low-value "Lost" customers, and pair it
  with a first-30-days onboarding nudge, since that's where most attrition actually happens.

## Data

[Online Retail II](https://archive.ics.uci.edu/dataset/502/online+retail+ii), UCI Machine Learning
Repository — real transactions from a UK-based online gift-ware retailer, December 2009 to December
2011. CC BY 4.0.

> Chen, D. (2012). *Online Retail II* [Dataset]. UCI Machine Learning Repository.
> https://doi.org/10.24432/C5CG6D

## Method

1. **Clean** — drop cancelled orders, missing customer IDs, and zero-price adjustment rows.
2. **RFM** — compute recency, frequency, and monetary value per customer; score each 1-5 by
   quintile; combine into segments (Long time regular, Loyal, New Customers, At Risk, Lost, Other).
3. **Cohort retention** — assign each customer a cohort (month of first purchase), track what share
   of each cohort was still buying in each subsequent month, visualize as a heatmap.
4. **Recommendation** — grounded in what the segmentation and retention curve actually show, not a
   generic template.

## Tech stack

R, tidyverse (dplyr, ggplot2, lubridate, readr), R Markdown, knitr.






Claude is AI and can make mistakes. Please double-check responses.
