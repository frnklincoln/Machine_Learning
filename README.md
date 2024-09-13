# Machine_Learning
## Unsupervised Learning in R:
### Determination of cluster Number 
[link](https://medium.com/@ozturkfemre/unsupervised-learning-determination-of-cluster-number-be8842cdb11)

[youtube](https://www.youtube.com/watch?v=7xHsRkOdVwo)

**Cluster number determination:**
it is important to predetermine the number of cluster for the clustering alogrithm to work. These alogrithms include:
k-means, l-medoids and hierarchical clustering.
Due data structure complexity, determination of optimal number of clusters may not be easy simply by observing the structure of the data. As such, there are a number of methods that can be utilized to determine optimal number of clusters. Such types of methods are:
Elbo Method
- Average Silhouette Method
- Gap Statistic Method
- calinski - Harabasz Method
- Davies - Bouldin Method

  **NB:** the code for these methods can be found in link provided above.

  
### K-means clustering
Clustering can be defined as grouping observations with similar characteristics in a dataset. Observations wihtin the same clusters have similar characteristics and properties, whilst observations in different clusters are dissimilar. similarities within clusters are based on calculated distances. The most widely used metrics for calculating distance between two points are: Euclidean and Manhattan.

***key characteristics between Euclidean and Manhanttan:***

**Euclidean:**
- distance metrics uses sum of the squared differences.
- Straight-line Distance measures the shortest path (the hypotenuse) between two points - suitable for direct distances.
- Euclidean is sensitive to outliers due to the squared differences, larger deviations have a disportionately larger effect on the distance calculation.
- Euclidean distance tends to produce spherical clusters

**Manhattan:**
- Distance metrics uses the sum of absolute differences between the corresponding coordinates - all deviations are treated equally.
- It employs a grid-like path, where it distance is measured based on horizontal and vertical paths, akin to navigating a city grid.
- It is robust to outliers due to absolute values - less sensitive to extreme differences.
- Manhattan tends to produce rectangular clusters.

[link](https://www.udemy.com/) to figures that shows differences between Eclidean and Manhattan

In K-means clustering, the centre of each cluster, or centroid, correpsonds to the mean of the points allocated to the cluster. The fundamental principle of k-means clustering is to define clusters with the aim of minimizing intra-cluster variablity, also known as total within-clusters variation.

Centroid is the average of each cluster
single-linkage is the closest point in each cluster
Complete-linkage is the furthest point in each cluster.

In heirarchical clusters - the height of the branches in the 'dendogram' most similarity.
