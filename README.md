# Retail Customer Segmentation

RFM and K-means learning project by Nivedha Sivakumar.

## Repairs
- Exclude missing customer IDs instead of inventing customers from invoice IDs.
- Combine transaction partitions, remove exact duplicates, and explicitly exclude cancellations, nonpositive purchases, and invalid required values.
- Define frequency as distinct invoices and recency against a recorded snapshot date.
- Use log-transformed, standardized RFM; compare k=2..6 with fixed seeds and sampled silhouette scores; check seed stability with adjusted Rand index.
- Publish aggregate outputs only. The prior notebook is retained in Git history.

## Reproduce
Use Python 3.12 and `pip install -r requirements.txt`. Put authorized `train.xlsx` and `test.xlsx` in `data/`, then run `retail_customer_segmentation.ipynb` top-to-bottom. The files are treated as transaction partitions for descriptive analysis, not a supervised train/test benchmark.

Executed successfully top-to-bottom on the local source data using Python 3.12. Exact tested package versions are recorded in requirements-lock.txt. All six saved figures across the two retail projects were visually reviewed. Direct package versions are pinned in requirements.txt; requirements-lock.txt records the full shared review environment (including packages unused by this project).

## Limits
Purchase-only profiles exclude refunds and unidentified customers. Internal cluster separation does not establish targeting value or revenue uplift. Course-split provenance and redistribution rights are unverified; source data and customer-level outputs are not published.

## Executed results

Analyzed 392,692 retained positive-purchase rows across 4,338 identified customers. Selected k=2 from k=2..6 by sampled silhouette (0.425); agreement across the two tested random seeds was ARI=1.000. This does not establish stability over time or business value. Segment profiles are shown below.
Exact duplicate rows are assumed to be duplicate observations; without a transaction-line identifier, legitimate identical line items cannot be distinguished with certainty.

Machine-readable aggregate results are in `results.json`; source data and customer-level predictions are excluded.
