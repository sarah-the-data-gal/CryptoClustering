# Cryptocurrency Clustering with PCA and K-Means
# Overview
This README describes how the analysis was performed, including data preparation, model training, and clustering optimization using Principal Component Analysis (PCA) and K-Means clustering.

# Instructions
1. Load the Data
Load the crypto_market_data.csv into a DataFrame.
2. Explore the Data
Get summary statistics of the data.
Plot the data to visualize its distribution and characteristics.
3. Prepare the Data
Use the StandardScaler() module from scikit-learn to normalize the data.
Create a DataFrame with the scaled data, using the "coin_id" index from the original DataFrame.
4. Find the Best Value for k (Original Scaled Data)
Use the elbow method to find the optimal value for k:
Create a list with k values from 1 to 11.
Create an empty list to store inertia values.
Compute inertia for each k value using a for loop.
Plot the elbow curve to visually identify the best k value.
5. Cluster Cryptocurrencies with K-Means (Original Scaled Data)
Initialize the K-means model with the optimal k value.
Fit the K-means model using the original scaled DataFrame.
Predict the clusters and add a new column with the predicted clusters to a copy of the original data.
Create a scatter plot using hvPlot with:
x-axis: price_change_percentage_24h
y-axis: price_change_percentage_7d
Color: cluster labels
Hover information: coin_id
6. Optimize Clusters with Principal Component Analysis (PCA)
Perform PCA on the original scaled DataFrame to reduce the features to three principal components.
Retrieve the explained variance to determine the information attributed to each principal component.
Create a new DataFrame with the PCA data, using the "coin_id" index from the original DataFrame.
7. Find the Best Value for k (PCA Data)
Use the elbow method on the PCA data to find the optimal value for k:
Create a list with k values from 1 to 11.
Create an empty list to store inertia values.
Compute inertia for each k value using a for loop.
Plot the elbow curve to visually identify the best k value.
8. Cluster Cryptocurrencies with K-Means (PCA Data)
Initialize the K-means model with the optimal k value.
Fit the K-means model using the PCA data.
Predict the clusters and add a new column with the predicted clusters to a copy of the PCA DataFrame.
Create a scatter plot using hvPlot with:
x-axis: price_change_percentage_24h
y-axis: price_change_percentage_7d
Color: cluster labels
Hover information: coin_id
# Findings and Lessons Learned
Data Normalization: Normalizing the data using StandardScaler was essential to ensure all features contributed equally to the analysis.

Elbow Method: This method helped identify the optimal number of clusters (k) by visualizing the point where the inertia decreases most rapidly.

PCA for Dimensionality Reduction: Using PCA to reduce the number of features helped simplify the clustering process. The explained variance indicated how much information was retained after the reduction.

Impact of PCA on Clustering: Clustering with PCA data resulted in tighter clusters and increased the number of entries in clusters 0 and 1 compared to the original analysis. This demonstrated that reducing the number of features can lead to more distinct and meaningful clusters.

By following these steps, we successfully clustered cryptocurrencies based on their 24-hour and 7-day price changes and optimized the clustering process using PCA.
