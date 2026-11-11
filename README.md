# Retail Customer Segmentation

An exploratory customer segmentation capstone by Nivedha Sivakumar, using transaction data to construct recency, frequency, and monetary (RFM) features and group customers with K-means.

## Methods implemented

- Missing-value inspection, duplicate checks, and transaction exploration.
- Monthly customer activity summaries.
- RFM feature construction and log transformation.
- Feature standardization with `StandardScaler`.
- K-means clustering with elbow and silhouette analysis.
- A three-cluster solution and visual comparison of segment characteristics.

The monthly grouping is an activity summary; it should not be described as a validated cohort retention analysis.

## Files and data

- `retail_customer_segmentation.ipynb`: original computational cells, with saved outputs and nonessential metadata removed for public sharing.
- `requirements.txt`: package names referenced by the notebook; this is not a tested environment lockfile.

The notebook describes UK online retail transactions from December 2010 to December 2011. Its inputs are `train.xlsx` and `test.xlsx`, expected beside the notebook. Required columns include `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, and `Country`.

Input files and customer-level outputs are excluded from the public package. Restore authorized copies locally to reproduce the analysis. The exact source and redistribution license for these course-provided splits have not been verified.

## Execution status

The source notebook records Python 3.9.7. It has not been rerun during repository preparation, and the original environment lockfile is unavailable. Saved numerical findings and cluster labels have not been independently validated.

Create an isolated environment, install the dependencies, place authorized input files beside the notebook, and open it in Jupyter. Validate compatibility before interpreting the results. An execution check is:

```sh
jupyter nbconvert --execute --to notebook --output retail_customer_segmentation.executed.ipynb retail_customer_segmentation.ipynb --ExecutePreprocessor.timeout=1800
```

## Interpretation limits

The original exploration replaces missing customer identifiers with invoice identifiers. This can treat transactions as separate customers and distort customer-level RFM values. Cancellation and return treatment, numeric-only aggregation compatibility, and random seeds also need review before using the clusters for decisions. Cluster numbers are arbitrary and should be interpreted from their feature profiles after a fresh run. No revenue uplift or validated targeting outcome is claimed.

## Author

Nivedha Sivakumar | [GitHub](https://github.com/NivedhaSiva) | [LinkedIn](https://linkedin.com/in/nivedhasivakumar)
