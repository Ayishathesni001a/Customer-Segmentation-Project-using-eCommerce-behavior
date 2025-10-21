# E-commerce Customer Segmentation

## 🚀 Project Overview
This project analyzes an e-commerce dataset to **segment customers** based on their purchase behavior using **unsupervised machine learning** techniques. The goal is to understand customer patterns, identify high-value customers, and provide actionable insights for targeted marketing and personalized offers.

**Techniques Used:**
- Data Cleaning & Preprocessing
- Feature Engineering (RFM: Recency, Frequency, Monetary)
- Exploratory Data Analysis (EDA)
- Outlier Handling & Scaling
- Dimensionality Reduction (PCA)
- Customer Segmentation (K-Means Clustering)
- Cluster Evaluation (Silhouette Score, Calinski-Harabasz Index, Davies-Bouldin Index)

---

## 📊 Dataset Overview
- **Source:** E-commerce transactions dataset  
- **Rows:** 525,461 transactions  
- **Columns:** Invoice, StockCode, Description, Quantity, InvoiceDate, Price, CustomerID, Country

**Key Observations:**
- Missing values in `CustomerID` and `Description` handled appropriately.
- Negative values in `Quantity` and `Price` identified as returns.
- Majority of transactions involve low-priced items and small quantities.
- RFM metrics calculated for each customer for segmentation.

---

## 🔹 Data Cleaning & Preprocessing
1. Handle missing values:
   - Filled missing `Description` with `"Unknown"`.
   - Dropped rows with missing `CustomerID`.
2. Remove duplicates and invalid records.
3. Handle negative values (returns) and outliers in `Quantity`, `Price`, and `Total Price`.
4. Feature Engineering:
   - **Total Price = Quantity × Price**
   - Extracted **Month**, **Day of Week**, and other time-based features.
5. Scaling for clustering using StandardScaler.

---

## 🔹 Exploratory Data Analysis (EDA)
- **Distribution Analysis:** Histograms and KDE plots for `Quantity` and `Price`.
- **Outlier Analysis:** Boxplots to visualize extreme values.
- **Relationships:** Scatterplots for `Quantity` vs `Price` and `Total Price`.
- **Correlation Analysis:** Heatmap to show how `Quantity`, `Price`, and `Total Price` relate.

**Key Insights:**
- Most customers buy inexpensive products in small quantities.
- High-priced items are rarely bought in bulk.
- Total spending driven by both quantity and price.

---

## 🔹 RFM Analysis
- **Recency:** Days since last purchase
- **Frequency:** Number of purchases
- **Monetary:** Total spending
- RFM table created per customer to capture purchasing behavior.

| Cluster | Recency | Frequency | Monetary | Interpretation |
|---------|---------|-----------|----------|----------------|
| 0       | Medium  | Low       | Medium   | Average customers |
| 1       | High    | Low       | Low      | Inactive / lost customers |
| 2       | Low     | High      | High     | Best / loyal customers |
| 3       | Low     | Medium    | High     | Valuable but less frequent buyers |

---

## 🔹 Clustering
- **Algorithm:** K-Means Clustering
- **Dimensionality Reduction:** PCA for 2D visualization
- **Optimal Clusters:** Determined using Silhouette Score

**Cluster Evaluation Metrics:**
- Silhouette Score: 0.6085 (good separation)
- Calinski-Harabasz Index: 3912.48
- Davies-Bouldin Index: 0.6277
- WCSS (Inertia): 3473.16

**Visualization:**
- Scatterplot of customers on PCA components colored by cluster shows clear segmentation.

---

## 🛠️ Tools & Libraries
- **Python**: pandas, numpy, matplotlib, seaborn
- **Machine Learning**: scikit-learn
- **Jupyter Notebook**: For EDA and analysis

---

## 💡 Key Takeaways
1. Identified **high-value and loyal customers** for marketing targeting.
2. Segmented customers for **personalized promotions** and **retention strategies**.
3. Clear patterns between purchase frequency, monetary value, and recency.
4. Data-driven insights to **boost sales and optimize marketing campaigns**.

---

## 📁 Project Structure
