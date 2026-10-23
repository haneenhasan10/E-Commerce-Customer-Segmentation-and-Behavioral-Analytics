## Project Overview:

This project focuses on analyzing customer purchasing behavior for an e-commerce platform using Unsupervised Machine Learning. By leveraging the RFM (Recency, Frequency, Monetary) framework, I segmented over 500,000 transactions into distinct groups. This allows businesses to implement targeted marketing strategies, improve customer retention, and maximize revenue.


## Data and cleaning
- Both sheets of the Excel file are combined (they overlap in December 2010, so exact duplicates are removed).
- Removed: rows without Customer ID, cancelled invoices, non-positive quantity or price, and non-product codes (postage, fees, manual adjustments).
- **5,852 customers** analysed.

## Method
1. **RFM features** per customer: Recency (days since last purchase), Frequency (number of invoices), Monetary (total spend).
2. **log1p transform + StandardScaler.** RFM data is heavily right-skewed, and without the log transform K-Means spends clusters on a few extreme customers.
3. **Choosing k:** compared k = 2–10 using elbow, silhouette and Davies-Bouldin, restricted to k = 3–6 with no cluster under 3% of customers. Result: **k = 4**.
4. **K-Means** (`n_init=10`, `random_state=42`) and segment profiling using medians.
5. **PCA** to visualise the segments in 2D.

## Results

| Segment | Customers | % customers | Median recency (days) | Median orders | Median spend | % revenue |
|---|---|---|---|---|---|---|
| Champions | 1,110 | 19.0 | 15 | 13 | 5,117.7 | 71.6 |
| At Risk | 1,468 | 25.1 | 157 | 5 | 1,580.4 | 18.5 |
| Potential Loyalists | 1,220 | 20.8 | 23 | 3 | 707.7 | 5.9 |
| Hibernating / Lost | 2,054 | 35.1 | 398 | 1 | 291.4 | 4.1 |

**Key finding:** Champions are 19% of customers but generate about 72% of revenue, while the 35% who are Hibernating / Lost generate about 4%.

**Suggested actions:**
- Champions: reward and retain (early access, loyalty perks), avoid heavy discounting.
- At Risk: re-engagement campaign with a time-limited offer.
- Potential Loyalists: encourage repeat orders (reminders, tiered offers).
- Hibernating / Lost: low-cost email reactivation only.

## Validation
- Silhouette score: **0.365**
- Davies-Bouldin index: **0.940**

These scores indicate moderate separation. The PCA plot shows the customers as one continuous cloud divided into four regions, which is typical for RFM data. The segments are **practical groups for marketing, not naturally separated clusters.**



## Tech stack
Python, pandas, NumPy, scikit-learn, Matplotlib, Seaborn. Runs in Google Colab or Jupyter.

## How to run
1. Download `online_retail_II.xlsx` (UCI Online Retail II) and upload it to Colab, or edit `file_path` in the notebook.
2. Run all cells.
