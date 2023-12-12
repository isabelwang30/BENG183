# Hierarchical Clustering

## Overview
1. What is Clustering?
2. Hierarchical Clustering Techniques
3. Calculating Similarity
4. Limits on Hierarchical Clustering
5. Significance of Hierarchical Clustering

## What is Clustering?

### Clustering vs Classification/Regression

For classification and regression, the computer is given a dataset with **datapoints** as well as **labels**. Each datapoint is then attirbuted with the corresponding **label** based on what technique you use. 

For clustering, you are only given a dataset with **datapoints** and **no labels**. This makes hierarchical clustering an **unsupervised machine learning method.** 

Given a set of *n* datapoints, group the datapoints into an unknown *k* clustering where the objects belonging to each cluster are more similar than those outside of the cluster. 

## Hierarchical Clustering Techniques

### Agglomerative clustering

Initially, each data point is an individual cluster.

1. Calculate the proximity from each point to the rest
2. Merge the two closest data points and update the matrix
3. Continue until all the datapoints are in one cluster

Data can be represented with a dendrogram, which shows visually where the data merged and split.

![dendrogram image](dendrogram.png)

### Divisive Clustering

Initially consider all datapoints to be in one cluster.
1. Calculate the difference between points within the cluster
2. Seperate those which are not similar.
3. Your result is *n* clusters.

## Calculating Similarity

A key step in both divisive and agglomerative clustering is calculating the similarity and difference between points. How do we do this?

### Min distance (Single-linkage algorithm)

    *Sim(C1,C2) = Min Sim(Pi,Pj) such that Pi ∈ C1 & Pj ∈ C2*

Take the two closest points in each cluster, calculate their similarity and declare that the similarity of the two clusters.
<img width="281" alt="Clustering3" src="https://github.com/b1sanchez/BENG183/assets/96998684/e6951f68-7066-4621-ad34-54e97064c30a">

**Benefit** from single-linkage is that they can be used to calculate the distance between clusters that are not necessarily elliptical. 

**Downsides** of single-linkage is that it is not sensitive to noise.

### Max distance (Complete-linkage algorithm)

    *Sim(C1,C2) = Max Sim(Pi,Pj) such that Pi ∈ C1 & Pj ∈ C2*

Pick the two farthest points from each other, calculate their similarity to determine the similarity between the two clusters.
<img width="299" alt="Clustering2" src="https://github.com/b1sanchez/BENG183/assets/96998684/1899541b-f2c4-4025-a137-150e3944e9b7">

**Benefit** of complete-linkage is that it is sensitive to noise.

**Downside** to complete-linkage is that it will group large groups together in inaccurate ways.

### Mean distance (UPGMA Linkage)

    *Sim(C1,C2) = ∑ sim(Pi, Pj)/|C1|x|C2 where, Pi ∈ C1 & Pj ∈ C2*

Take all pairs of points and calculate their similarity to create an average across clusters.
<img width="274" alt="Clustering1" src="https://github.com/b1sanchez/BENG183/assets/96998684/7442a8e0-054e-4e28-9f51-d0b432ae2f03">

**Benefit** of mean distance is that mean distance is sensitive to noise.

**Downside** of mean distance is that it is biased towards globular clusters.

## Different Ways to Measure Distance 



## Limits on Hierarchical Clustering

The time-complexity for hierarchical clustering is very high, making it inefficient for large datasets. All three of the main ways to calculate similarity of flawed in their own way which makes it an imperfect method. 

## Significance of Hierarchical Clustering
1) High Accuracy
   - Relabable and accurate results
3) Flexible
   - Any type of data
4) Optimial generalzation 
   - Creates clusters based on the similarity between the objects rather than predetermined classifications 

## Other types of clustering
1. K-means clustering: declares the *k* number of clusters from the start. 
2. Density-based clustering: creates clusters based off of density rather than absolute distance.

There are many other forms of clustering as well! See all the world has to offer below:

![clusters](clusters)(/Users/ellasay/Downloads/clusters.png)

## References
1. UCSD BENG 183 Lecture Slides
2. [Advantages of Hierarchical Clustering](https://codinginfinite.com/hierarchical-clustering-applications-advantages-and-disadvantages/)





