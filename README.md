# Customer Segmentation using Clustering

## About this Dataset
### Context
This data set is created only for the learning purpose of the customer segmentation concepts , also known as market basket analysis . I will demonstrate this by using unsupervised ML technique (KMeans Clustering Algorithm) in the simplest form.

### Content
You are owing a supermarket mall and through membership cards , you have some basic data about your customers like Customer ID, age, gender, annual income and spending score.
Spending Score is something you assign to the customer based on your defined parameters like customer behavior and purchasing data.
#### CustomerID (a unique identifier for each customer)
#### Gender (Male or Female)
#### Age (in years)
#### Annual Income (in thousands of dollars)
#### Spending Score (a score from 1 to 100, with higher scores indicating higher spending)



The aim of this project is to segment the customers of a mall into different groups based on their annual income and spending score.

### Data Preparation
The data set used in this project is the Mall_Customers_clustering data set. It contains information about the customers' gender, age, annual income, and spending score.

The data is loaded into a pandas DataFrame and the gender column is converted into dummy variables. The annual income and spending score columns are extracted and stored in a numpy array.

### Clustering
The code first imports necessary packages such as Pandas, Numpy, Matplotlib, Plotly, and some clustering algorithms from scikit-learn library such as SpectralClustering, KMeans, and MeanShift DBSCANB.


After reading the data file into a Pandas dataframe and transforming the gender column into a one-hot encoded representation, the code selects only two columns: "Annual Income (k$)" and "Spending Score (1-100)" as the features for clustering.

The first step is to determine the optimal number of clusters using the Elbow Method. The code uses the KMeans algorithm and calculates the inertia (sum of squared distances between the observations and their closest cluster center) for each number of clusters between 1 and 10. The result is plotted in a graph with the number of clusters on the x-axis and the inertia on the y-axis. The optimal number of clusters can be identified as the "elbow" in the graph.


The code then fits the KMeans algorithm with the optimal number of clusters (5 in this case) to the data and plots the results. Each customer is represented by a dot, with different colors representing different clusters.
The centroids of the clusters are also plotted as red dots.
The code then repeats the process, but this time with three features: "Age", "Annual Income (k$)", and "Spending Score (1-100)". The optimal number of clusters is determined using the same Elbow Method and the results are plotted in a 3D scatter plot using Plotly.

Finally, the code performs another clustering analysis using the DBSCAN algorithm and calculates the silhouette score for each number of clusters between 5 and 22. The silhouette score measures the similarity of an observation with its own cluster compared to other clusters, with higher scores indicating a better cluster assignment. The result is plotted in a graph with the number of clusters on the x-axis and the silhouette score on the y-axis.
