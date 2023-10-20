# CryptoClustering

Instructions
Rename the Crypto_Clustering_starter_code.ipynb file as Crypto_Clustering.ipynb.

Load the crypto_market_data.csv into a DataFrame.

Get the summary statistics and plot the data to see what the data looks like before proceeding.

![image](https://github.com/amccollough1/CryptoClustering/assets/133404805/ae8777e7-b915-462d-9689-20eb76f6c355)


![bokeh_plot](https://github.com/amccollough1/CryptoClustering/assets/133404805/031234cb-7b36-45d5-9050-42e3a805ae3e)

Prepare the Data
Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.

Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

The first five rows of the scaled DataFrame should appear as follows:

![image](https://github.com/amccollough1/CryptoClustering/assets/133404805/8572c247-e8c1-45e7-8c5f-5719a196a23e)


Find the Best Value for k Using the Original Scaled DataFrame

Use the elbow method to find the best value for k using the following steps:


Create a list with the number of k values from 1 to 11.

Create an empty list to store the inertia values.

Create a for loop to compute the inertia with each possible value of k.

Create a dictionary with the data to plot the elbow curve.

Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

![bokeh_plot](https://github.com/amccollough1/CryptoClustering/assets/133404805/819f91d8-7ede-473e-ae4d-d2fc898ea31b)


Answer the following question in your notebook: What is the best value for k?

Answer: 4

Cluster Cryptocurrencies with K-means Using the Original Scaled Data

Use the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:

Initialize the K-means model with the best value for k.

Fit the K-means model using the original scaled DataFrame.

Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.

Create a copy of the original data and add a new column with the predicted clusters.

Create a scatter plot using hvPlot as follows:

Set the x-axis as "PC1" and the y-axis as "PC2".

Color the graph points with the labels found using K-means.

Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

![bokeh_plot-1](https://github.com/amccollough1/CryptoClustering/assets/133404805/bd47919c-7f20-4fdd-b1aa-65e2958122fd)


Optimize Clusters with Principal Component Analysis

Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.

Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:

What is the total explained variance of the three principal components?

Answer: PC1 retained ~37%, PC2 retained ~35%, and PC3 retained ~18% of original data.

Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

The first five rows of the PCA DataFrame should appear as follows:

![image](https://github.com/amccollough1/CryptoClustering/assets/133404805/953d907f-5997-44b9-9e52-157fb81f553a)


Find the Best Value for k Using the PCA Data

Use the elbow method on the PCA data to find the best value for k using the following steps:

Create a list with the number of k-values from 1 to 11.
Create an empty list to store the inertia values.
Create a for loop to compute the inertia with each possible value of k.
Create a dictionary with the data to plot the Elbow curve.
Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

![bokeh_plot_elbow](https://github.com/amccollough1/CryptoClustering/assets/133404805/5fc166ca-ebe6-481c-81af-80120e6a02bb)


Answer the following question in your notebook:

What is the best value for k when using the PCA data?

Answer: 4

Does it differ from the best k value found using the original data?

Answer: No it does not differfrom the best k value found using the original data. 

Cluster Cryptocurrencies with K-means Using the PCA Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:

Initialize the K-means model with the best value for k.
Fit the K-means model using the PCA data.
Predict the clusters to group the cryptocurrencies using the PCA data.
Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.

Create a scatter plot using hvPlot as follows:
Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
Color the graph points with the labels found using K-means.
Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

![bokeh_plot_last](https://github.com/amccollough1/CryptoClustering/assets/133404805/ca1cfaec-ebcc-45ea-8391-3a83d6b4baec)



Answer the following question:

What is the impact of using fewer features to cluster the data using K-Means?

 Overall , the impact of the PCA data resulted in tighter clusters, than the original analysis showed.
