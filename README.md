# CryptoClustering
## Unsupervised Learning Module 19 Challenge
This script contains code that creates a model to predict cryptocurrency price changes.

### Preparing the Data
The code first reads a csv file containing crypto market data transfers it to a DataFrame. It then retrieves the summary stats and creates a line plot displaying the dataframe info. It then uses the StandardScaler() module from scikit-learn to normalize the data from the CSV file, then transfers the normalized data to another dataframe.

### Finding k Using Scaled Data
To find the best value for k using the scaled data, this code uses the elbow method. It first creates a list with the number of k values from 1 to 11, along with an empty list to store the inertia values. It then creates a for loop to compute the inertia with each possible value of k and a dictionary with the data to plot the elbow curve. It then creates another line plot with all the inertia values computed with the different values of k to visually identify the optimal value for k. It then answers the question: What is the best value for k? This is answered by locating the "elbow" in the line chart, or the point at which the slope starts to even out. In this case it would be 4.

### Clustering Cryptocurrencies with K-means
To cluster the cryptocurrencies for the best value for k on the scaled data, the code first creates a K-means model with the amount of clusters being the best value for k (4) and a random state (in this case we used 7).The model is then fitted using the original scaled DataFrame. The code then predicts the clusters to group the cryptocurrencies using the scaled data and then creates a copy of the dataframe witha new column for the predicted clusters.

### Optimizing Clusters with Principal Component Analysis
The code then creates a PCA model and reduces the features to three principal components using a "fit_transform." It then uses the explained variance ratio to display a total variance of about 90% for the three principal components. It then creates a new dataframe with the PCA data.

### Finding the Best Value for k Using the PCA Data
Once again this code uses the elbow method to find the best value for k, this time using the PCA data. It repeats the same steps as before using the new dataframe and once again finds the elbow at 4.

### Clustering Cryptocurrencies with K-means Using the PCA Data
To cluster the cryptocurrencies for the best value for k on the PCA data, the code creates another K-means model with the best value for k for the PCA data (still 4), and then fits the K-means model using the PCA data. The clusters are predicted once again to group the cryptocurrencies using the PCA data, and creates a copy of PCA dataframe with a new column to store the predicted clusters. Another scatterplot is created displaying the clusters for the PCA data, and the question: "What is the impact of using fewer features to cluster the data using K-Means?" is answered,
