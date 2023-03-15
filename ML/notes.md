# Kinds of machine learning

Click for [Data Preparation and Feature Engineering Tutorial](https://github.com/taaaraaa/lighthouse-data-notes/blob/main/EDA/Data_Prep_and_Feature_Engineering.ipynb) as the prerequisite step in ML

## 1. Supervised learning
In supervised learning, each data point is labeled or associated with a category or value of interest. An example of a categorical label is assigning an image as either a ‘cat’ or a ‘dog’. An example of a value label is the sale price associated with a used car. The goal of supervised learning is to study many labeled examples like these, and then to be able to make predictions about future data points. For example, identifying new photos with the correct animal or assigning accurate sale prices to other used cars. This is a popular and useful type of machine learning.
### 1.1 Classification or categorization
### 1.2 Regression

## 2. Unsupervised learning

In unsupervised learning, data points have no labels associated with them. Instead, the goal of an unsupervised learning algorithm is to organize the data in some way or to describe its structure. Unsupervised learning groups data into clusters, as K-means does, or finds different ways of looking at complex data so that it appears simpler.
### 2.1 Clustering
- Density-based clustering
- Distribution-based clustering
- Hierarchical Clustering
- Centroid-based Clustering: [Kmeans](#kmeans-method)

### 2.2 Dimensionality Reduction

## 3. Reinforcement learning
In reinforcement learning, the algorithm gets to choose an action in response to each data point. It is a common approach in robotics, where the set of sensor readings at one point in time is a data point, and the algorithm must choose the robot’s next action. It's also a natural fit for Internet of Things applications. The learning algorithm also receives a reward signal a short time later, indicating how good the decision was. Based on this signal, the algorithm modifies its strategy in order to achieve the highest reward.

-----------------------
## Kmeans Method

1. Assign Cluster Centroids until convergence

    At the first iteration, Machine Chooses K centroids randomly based on the number of clusters we define

2. Calculate distance and assign it to the nearest centroid
3. Calculate the mean in each cluster and rechoose centroids (means)


**Algorithm Convergence** : No change anymore

This cycle continues untill the means are the same as previous centroids

If we run the Kmeans several times, it would give us different results. The best one is the one with the least Inertia.

 > **Inertia** is a performance metric. it's the mean squared distance between each instance and its closest centroid

You can control how many times  you want to run your K-Means via n_init. Sklearn runs it 10 times by default and return the model with the best score.

### 2 ways to choose K:
- Domain experience
- Exploring different Ks

``` Python
#Running Kmeans for several times
wcss = [] #Within cluster sum squares
for i in range(2,15):
    km = KMeans(n_clusters= i, random_state=seed)
    km.fit(X)
    wcss.append(km.inertia_)
```
### Elbow Method

After plotting inertia vs K, we can see what is the optimum number of clusters. (Elbow point)



### silhouette score

A more precise approach to choose the optimum K (but also more computationally expensive) is to use the silhouette score. The closer sil score to 1, the better.

The silhouette coefficient can vary between -1 and +1: a coefficient close to +1 means that the instance is well inside its own cluster and far from other clusters, while a coefficient close to 0 means that it is close to a cluster boundary, and finally a coefficient close to -1 means that the instance may have been assigned to the wrong cluster.
``` python
from sklearn.metrics import silhouette_score

km = KMeans(n_clusters = 5)
km.fit(X)
silhouette_score(X, km.labels_)
```
:memo: **Note:** In Unsupervised Learning, machine does the clustering, you need to do the interpretation yourself. When we have more than two or three dimensions. It's harder to interpret the results by simply plotting it. So we do EDA on each cluster to get more about it (why these customers are in the same segment/cluster).