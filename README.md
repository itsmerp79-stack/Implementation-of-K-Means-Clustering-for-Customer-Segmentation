# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the required libraries and load the Mall_Customers.csv dataset.
2.Select the features Annual Income and Spending Score for clustering.
3.Scale the data using StandardScaler.
4.Use the Elbow Method to find the optimal number of clusters.
5.Apply K-Means clustering, assign cluster labels, and visualize the clusters using a scatter plot.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by:RAJAPRABU.S
RegisterNumber:212225240113  
*/
import os os.environ["OMP_NUM_THREADS"] = "1"

import pandas as pd import numpy as np import matplotlib.pyplot as plt from sklearn.cluster import KMeans from sklearn.preprocessing import StandardScaler

df = pd.read_csv("C:/Users/acer/Downloads/Mall_Customers.csv")

print(df.head())

X = df[['Annual Income (k$)', 'Spending Score (1-100)']]

scaler = StandardScaler() X_scaled = scaler.fit_transform(X)

wcss = []

for i in range(1, 11): kmeans = KMeans(n_clusters=i, random_state=42, n_init=10) kmeans.fit(X_scaled) wcss.append(kmeans.inertia_)

plt.plot(range(1, 11), wcss) plt.title("Elbow Method") plt.xlabel("Number of Clusters") plt.ylabel("WCSS") plt.show()
```

## Output:
<img width="390" height="610" alt="image" src="https://github.com/user-attachments/assets/c154e7f6-ae5d-4f7c-a9b5-cbf2b06fb58f" />



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
