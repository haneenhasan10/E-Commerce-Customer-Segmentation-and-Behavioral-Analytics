Project Overview:
This project focuses on analyzing customer purchasing behavior for an e-commerce platform using Unsupervised Machine Learning. By leveraging the RFM (Recency, Frequency, Monetary) framework, I segmented over 500,000 transactions into distinct groups. This allows businesses to implement targeted marketing strategies, improve customer retention, and maximize revenue.
Key Features & Workflow
1.	Data Cleaning: Handled missing values and removed canceled orders.
2.	Feature Engineering (RFM): Transformed raw transactional data into three behavioral metrics:
-	Recency: Days since the last purchase.
-	Frequency: Total number of purchases.
-	Monetary: Total amount spent.
3.	Data Scaling: Applied StandardScaler to normalize features for optimal clustering performance.
4.	Optimal K Selection: Used the Elbow Method and Silhouette Analysis to determine the best number of clusters.
5.	Customer Clustering: Implemented K-Means Clustering to categorize customers into 4 strategic segments.
6.	Advanced Visualization: Used t-SNE and PCA for dimensionality reduction to visualize high-dimensional clusters in a 2D space.
Results & Business Insights
The model achieved a Silhouette Score of 0.6, indicating good cluster separation and consistency.
Customer Personas:
•	Champions (Cluster 2): High-value, frequent shoppers who purchased recently.
•	Loyalists (Cluster 3): Consistent customers with high spending and steady engagement.
•	Potential Loyalists (Cluster 0): Moderate shoppers who visit every 1-2 months; prime targets for upselling.
•	At-Risk (Cluster 1): Inactive customers (8+ months since last purchase) who require urgent re-engagement.
Tech Stack
•	Language: Python
•	Libraries: Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn.
•	Algorithms: K-Means Clustering, t-SNE, PCA.
•	Environment: Google Colab / Jupyter Notebook.
