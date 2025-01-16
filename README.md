# CryptoClustering

# **Cryptocurrency Clustering with KMeans and PCA**

This project demonstrates how to group cryptocurrencies based on their market performance using clustering techniques. The workflow leverages KMeans for clustering and Principal Component Analysis (PCA) for dimensionality reduction, enabling both detailed analysis and clear visualization of the clustering results.

---

## **Features**
This project includes the following functionalities:
1. **Data Preprocessing:**
   - Load cryptocurrency market performance data from a CSV file.
   - Normalize the data using `StandardScaler` to standardize feature values and eliminate scale differences.

2. **KMeans Clustering:**
   - Apply the KMeans algorithm to group cryptocurrencies based on their performance metrics.
   - Use the Elbow Method to determine the optimal number of clusters.

3. **Principal Component Analysis (PCA):**
   - Reduce the dimensionality of the dataset to three principal components while retaining ~90% of the data variance.
   - Simplify clustering and improve visualization clarity.

4. **Visualization:**
   - Plot Elbow curves to visualize the optimal number of clusters for both the original and PCA-reduced datasets.
   - Generate scatter plots to show clustering results in two dimensions, color-coded by cluster.

5. **Comparison of Results:**
   - Analyze the impact of PCA on clustering by comparing Elbow curves and scatter plots before and after dimensionality reduction.


## **How It Works**
### 1. **Data Loading**
- The project begins by loading cryptocurrency market data from `crypto_market_data.csv`. This dataset includes metrics such as:
  - Price change percentages over different timeframes (24h, 7d, 14d, etc.).
  - Market trends over longer durations (30d, 60d, 200d, 1y).

### 2. **Data Preprocessing**
- The data is normalized using `StandardScaler` to ensure that all features have equal weight in the clustering process.
- The normalized data is stored in a new DataFrame for further analysis.

### 3. **Finding the Optimal Number of Clusters**
- The Elbow Method is used to determine the optimal number of clusters (`k`). It involves:
  - Running KMeans for a range of `k` values (1 to 11).
  - Calculating the inertia (sum of squared distances to cluster centers) for each `k`.
  - Plotting the inertia values to visually identify the "elbow point."

### 4. **KMeans Clustering**
- Once the optimal `k` is identified, KMeans clustering is performed on the normalized dataset.
- The resulting clusters are added as a new column to the DataFrame for visualization and analysis.

### 5. **Dimensionality Reduction with PCA**
- PCA reduces the dataset to three principal components while retaining significant variance (~90% in this case).
- Clustering is performed again on the PCA-reduced dataset, and the Elbow Method is used to find the optimal `k`.

### 6. **Visualization**
- Scatter plots visualize the clusters:
  - For the original dataset, clusters are plotted using metrics such as price change percentages.
  - For the PCA-reduced dataset, clusters are visualized in the principal component space (PC1, PC2).

### 7. **Comparison**
- Elbow curves and scatter plots are compared side-by-side to evaluate the impact of PCA on clustering.

---

## **Key Outputs**
1. **Elbow Curves:**
   - Visualizes inertia values for different `k` values, identifying the optimal number of clusters.
   - Plots are generated for both the original and PCA-reduced datasets.

2. **Scatter Plots:**
   - Color-coded scatter plots of clusters.
   - Original data uses raw metrics like price change percentages for plotting.
   - PCA-reduced data uses principal components for plotting.

3. **Explained Variance:**
   - Displays the total variance retained by the PCA-reduced dataset (e.g., ~89.5%).

---

## **FAQ**

### **1. What is the purpose of PCA in this project?**
PCA reduces the number of features while preserving most of the data’s variance. This simplifies the clustering process and improves visualization by reducing noise and redundancy in the data.

### **2. Why use the Elbow Method to determine k?**
The Elbow Method helps balance between:
- Minimizing inertia (sum of squared distances to cluster centers).
- Avoiding overfitting by keeping the number of clusters manageable.
