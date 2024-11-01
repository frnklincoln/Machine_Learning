# Machine Learning
Unsupervised Learning: detection of patterns in data without any labelling
Supervised: Using patterns found in "training", or labelled data, to predict or "classify" a new dataset

## Data Understanding

### Gene Expression Data
Gene expression data typically consists of measurements of gene activity levels across multiple samples. Each sample represents a patient or condition, and each feature represents a gene[1][2].

### Data Structure
Gene expression datasets often have:
- Many features (genes) but relatively few samples
- High dimensionality
- Potential for noise and batch effects

## Machine Learning Basics

### Types of Machine Learning Problems
For gene expression data, common tasks include:
- Classification (e.g., distinguishing cancer types)
- Clustering (e.g., finding groups of similar samples)
- Feature selection (identifying important genes)

### Key Concepts
1. **Supervised vs. Unsupervised Learning**: Understand the difference between learning with labeled data (supervised) and without labels (unsupervised)[1].

2. **Train-Test Split**: Learn to divide data into training and testing sets to evaluate model performance[1].

3. **Cross-validation**: Understand techniques to assess model performance and avoid overfitting[1].

## Data Preprocessing

### Essential Steps
1. **Data Normalization**: Adjust for technical variations between samples[2].
2. **Feature Selection**: Identify the most informative genes[1][2].
3. **Dimensionality Reduction**: Techniques like PCA to handle high-dimensional data[2].

## Machine Learning Algorithms

### Common Algorithms for Gene Expression Data
1. Support Vector Machines (SVM)
2. Random Forests
3. k-Nearest Neighbors (k-NN)
4. Neural Networks

Learn the basics of how these algorithms work and when to use them[1][3].

## Model Evaluation

### Metrics
Understand common evaluation metrics:
- Accuracy
- Precision
- Recall
- F1-score
- ROC curves

### Interpretation
Learn to interpret results in the context of biological significance[1].

## Tools and Libraries

### Programming Languages
R and Python are commonly used in bioinformatics and machine learning.

### Key Libraries
- For R: Bioconductor, DESeq2, MLSeq
- For Python: scikit-learn, pandas, numpy, matplotlib

## Practical Skills

1. **Data Manipulation**: Learn to handle and transform gene expression matrices[2].
2. **Visualization**: Create informative plots (e.g., heatmaps, PCA plots)[2].
3. **Statistical Analysis**: Understand basic statistical concepts relevant to gene expression analysis[1].

## Bioinformatics Knowledge

Having a basic understanding of molecular biology and genetics will help in interpreting results and designing meaningful experiments[3].

By focusing on these fundamentals, beginners can build a solid foundation for applying machine learning to gene expression data. It's important to start with simple datasets and gradually progress to more complex analyses as your understanding grows[1][2][3].

Citations:
[1] https://www.bioconductor.org/help/course-materials/2015/SeattleApr2015/D_MachineLearning.html
[2] https://openpress.universityofgalway.ie/genomicsdatascience/chapter/machine-learning-clustering/
[3] https://www.youtube.com/watch?v=IYzjpnBv2l4
[4] https://academic.oup.com/gigascience/article/doi/10.1093/gigascience/giad111/7516260
[5] https://github.com/fredhutchio/ml-pancancer-example/blob/main/2-Tutorials/Tutorial%201%20-%20Beginner.ipynb
[6] https://pmc.ncbi.nlm.nih.gov/articles/PMC4908320/
[7] https://www.sciencedirect.com/science/article/pii/S0006291X24007617
[8] https://www.youtube.com/watch?v=0xdCbt1hfSI




There have been several classification and feature selection methods utilized to identify differentially expressed genes in microarray data.
Such classifications include SVM, RBF Neural Netes, MLP Neural Nets, Bayesian, Decision Tree and Random Forest. The accuracies of these methods have been calculated using several validation methods such as v-fold validatiaon.

### Feature engineering
A computational approach used to handle high dimenstional gene expression datasets.
There are several techniques of feature engineering used in gene expression analysis:
 - Filter: Removes irrelevant and redundant data features based on quantifying the relationship between each feature and the target predicted variable
 - Wrapper: Utilizes a classification algorithm for evaluating the importance of data features, where the classifier is wrapped in a search algorithm to discover the best subset of data features
 -  Embedded: This method identifies important features that enchance the performance of a classification algorithm by embedding the feature engineering technique into the learning stage of the classifier

### Get the working directory
```python
# Load the os modu
import os
print(os.getcwd())
```
### Dealing with numeric-only columns
```python
numeric_df = df.select_dtypes(include = ['number'])
```
### check for a list of variables
```python
print(globals())
list(globals().keys())

```

### Deleting variables
```python
del variable1, varialbe2
```


### Data preparation
**Sample data without replacement** - meaning you don't want to select the same row multiple times.
```python
sample_size = min(8000, len(df)) # ensure the sample size does not exceed the available rows
sampled_data = df.sample(n = sample_size, random_state = 42, replace = False)
```
**Sample data with replacement** - selecting the same row multiple times
```python
sample_size = min(8000, len(df)) # ensure the sample size does not exceed the available rows
sampled_data = df.sample(n = sample_size, random_state = 42, replace = True)
```
**Using Fractional Sampling:** if you want to sample a certain fraction of the dataset, you can use the 'frac' arugment instead.
```python
# sample 80% of the dataset
sampled_data = df.sample(frac = 0.8, random_state = 42) # random_state is for reproducibility
```
**Saving to a Specific Path**
```python
df.to_csv("\path\to\directory\gene_expression_data.csv", index = False)
```

## Supervised Learning in Python:
The very basic implementation of building and training a model to make predictions:
 - import the data
   ```python
   import pandas as pd
   from sklearn.tree import DecisionTreeClassifier
   from sklearn.externals import joblib
   from sklearn import tree
   data = pd.read_csv(path/to/file)
   X = data.drop(coloumns = ['target']
   y = data['target']
   ```
 - create a model
   ```python
   model = DecisionTreeClassifier()
   model.fit(X, y)
   # Save the file
   joblib.dump(model, 'Training-model.joblib')
   ```
 - train the model
```python

```
Model persistance using joblib.dump() - allows you to save a file when your model has been built and trained. This prevent you from having to build and train the model each time a new dataset is to be tested (line 53).
To load the model:
```python
model = joblib.load('path/to/Training-model.joblib)
```
- Visualizing Decision Trees
  NB: The '.dot' in the out_file argument is a graphical description language.
```python
tree.export_graphviz(model, out_file = 'music-recommender.dot',
feature_names = ['age', 'gender', class_names = sorted(y.unique())]),
label = 'all'
rounded = True,
filled = True)
```




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
