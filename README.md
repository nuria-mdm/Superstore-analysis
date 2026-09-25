**Superstore Sales & Profitability Analysis**

An exploratory data analysis of ~10,000 retail transactions, focused on identifying where profit is actually being created or destroyed across discounting, regions, customer segments and order size — and translating each finding into a concrete business recommendation.

<!-- TODO: reemplaza estos enlaces por las rutas reales una vez subas los archivos -->

Notebook: notebook/Superstore_Sample_Analysis.ipynb Report: report/Executive_Report.pdf

Overview

The dataset covers order-level sales, discounts, profit, shipping and customer data from a US retail superstore between 2014 and 2017, across three product categories (Furniture, Office Supplies, Technology) and four regions (Central, East, South, West).

The analysis is structured around five business questions:

Discounting — how much discount can the business afford before it erodes margin, and does that threshold depend on product price?
Time trends — is growth stable, is there a seasonal pattern, and what explains the sharpest year-over-year profit drop?
Regional performance — which regions are strongest, and which carry structural risk?
Customer value — where does profit actually come from, and are there customers who generate high sales but negative profit?
Order-level economics — how should profit margin (%) be interpreted alongside absolute profit ($)?
Key findings

Discounting has a threshold effect, and the threshold depends on price tier. Profitability generally holds up to a 20% discount, but higher-priced sub-categories (Machines, Bookcases, Tables) turn structurally unprofitable above 10-11%. A single blanket discount cap is not the right policy; it should be tiered by price range.

The 2017 profit decline was localized, not a company-wide downturn. It was concentrated in Furniture (mainly Bookcases) and in the Central and South regions, while East and West grew over the same period, and it was not linked to heavier discounting.

Central is the most structurally fragile region. Its top three customers account for 47.6% of regional profit despite being just 0.5% of its customer base, and average shipping times run roughly double those of other regions.

Profit is far more concentrated than revenue. The top ~19% of customers generate over 81% of total profit, while a "high activity, low profit" segment of 137 customers (17% of the customer base) buys almost as often as top customers while averaging a $189 loss each.

Order-level profit margin can be misleading read on its own. The worst-looking margins belong almost entirely to very small orders, where a modest dollar loss produces a large percentage swing. Margin should be read together with absolute profit, not in isolation.

The full reasoning, supporting numbers and business recommendations for each finding are in the Executive Summary section of the notebook.

Methodology
Data cleaning: duplicate detection (exact and near-duplicate), a documented decision to drop a small set of unrecoverable missing values rather than impute them, and IQR-based outlier review with reasoning on which outliers reflect real transactions versus data issues.
Feature engineering: shipping time, line-level and order-level profit margin, discount bands, and price tiers derived from quantile-based binning.
Analysis: year-over-year and month-over-month trend decomposition, Pareto analysis, RFM customer segmentation, and a price-tier by discount-band cross-analysis.
Repository structure
notebook/     full analysis notebook
report/       one-page executive summary for a non-technical audience
images/       key charts exported for this README
data/         source dataset
Tech stack

Python, pandas, numpy, matplotlib, seaborn.

Running the analysis
pip install -r requirements.txt
jupyter notebook notebook/Superstore_Sample_Analysis.ipynb
Data source

Superstore Sample dataset, Kaggle.

Limitations

This is a descriptive analysis. Observed differences across regions, categories and time periods are not tested for statistical significance, so findings should be read as well-supported hypotheses rather than confirmed causal effects.

Author

Nuria Benítez

<!-- TODO: añade tu LinkedIn, email o portfolio -->
