This project leverages advanced unsupervised machine learning 
techniques to segment customers from an e-commerce dataset based 
on their purchasing behaviors. The primary objective is to enable 
targeted marketing, improve customer retention, and extract 
actionable insights using clustering and RFM analysis. --- 

## 🚀 Business Objective 
To design a data-driven segmentation strategy that categorizes 
customers into meaningful groups, enabling the business to: - Identify high-value (VIP) customers - Detect dormant or at-risk customers - Tailor marketing campaigns for each segment - Allocate resources more efficiently --- 
## � Dataset Overview - **Dataset**: Online Retail Data from UCI - **Size**: 541,909 transactions - **Features**: Invoice, Product, Quantity, Date, Price, Customer ID, 
Country - **Timeframe**: 1 Year of sales data 

--- 
## 🛠️ Workflow Summary 
### 1. 🔍 Data Preprocessing - Removed null values in `Customer ID` and `Description` - Filtered out negative `Quantity` and `Price` - Removed exact duplicates - Extracted time-based features: `day`, `month`, `hour`, and full `date` 
### 2. 📊 Exploratory Data Analysis (EDA) - Identified sales peaks by hour, day, and month - Visualized quantity and price distributions - Detected and removed outliers using the IQR method 
### 3. � Feature Engineering 
Constructed a customer-level dataset containing: 
| Feature | Description | 
|---------|-------------| 
| total_quantity | Total items purchased | 
| total_revenue  | Total money spent | 
| total_orders   | Total number of invoices | 
| total_products | Total product variety | 
Also performed RFM Analysis: 
| RFM Metric | Description | 
|------------|-------------| 
| Recency (R) | Days since last purchase | 
| Frequency (F) | Total orders made | 
| Monetary (M) | Total spending | 
➡️ Transformed into `RFM Score` and mapped to **Business 
Segments** like: - `VIP` - `Loyal` - `At Risk` - `Big Spender` - `Other` --- 
### 4. ⚖️ Scaling and Dimensionality Reduction - Standardized features using `StandardScaler` - Applied **PCA** to reduce dimensionality for clustering - Explained Variance Ratio: **~99%** - Components retained: 2 --- 

### 5. � Clustering Techniques 
#### ✅ KMeans Clustering 
- Tuned optimal `k` using the **Elbow Method** - Best k: **4 clusters** - Final cluster distribution: 
| Cluster ID | Customers | 
|------------|-----------| 
| Cluster 0  | 2330 
| Cluster 1  | 11     
| Cluster 2  | 1062 
| Cluster 3  | 2276

#### ❌ DBSCAN Clustering - Tuned `eps` and `min_samples` using silhouette score - Best score: **0.93** - But resulted in a single dense cluster ➜ not useful for segmentation --- 
## 📈 Visualizations - EDA plots: Monthly/Daily/Hourly sales heatmaps - PCA scatter plots before and after clustering - RFM segment distribution bar chart - KMeans clusters visualized in 2D space (via PCA) --- 
## � Final Dataset Structure 
| Customer ID | total_quantity | total_revenue | total_orders | RFM 
Score | Segment | KMeans Cluster | DBSCAN Cluster | 
|-------------|----------------|----------------|---------------|-------------|----------|------------------|------------------| 
This enriched dataset is ready for marketing teams to act on each 
segment. --- 
## � Tools & Technologies - Python - Pandas, NumPy - Matplotlib, Seaborn - Scikit-learn - Jupyter Notebook - Git & GitHub --- 
## 📌 Key Takeaways - **KMeans** proved to be the most effective clustering algorithm for 
this use-case - **PCA** was crucial for visualizing and optimizing clustering - **RFM Analysis** added strong business interpretability to technical 
clusters - The final insights can directly power: - Loyalty campaigns 
- Customer retention strategies - Personalized offe
