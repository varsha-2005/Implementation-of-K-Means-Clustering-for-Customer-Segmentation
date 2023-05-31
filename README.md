# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. import pandas as pd
2. impoet the necessary libraries from sklearn
3. by using kmeans predict y
4. by using plt.scatter predict the graph of customer segments

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Varsha.G
RegisterNumber: 212222230166
*/

import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
  
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```

## Output:
data.info():

![image](https://github.com/MavillaPranathi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343610/552ddfd5-594f-455d-9810-ffa6d8065a92)

data.isnull().sum() function

![image](https://github.com/MavillaPranathi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343610/b0c1eed9-a891-492b-9434-a30f05930a26)

Elbow method graph:

![image](https://github.com/MavillaPranathi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343610/c45165ff-ee84-432f-bfc7-764cbf36669f)

KMeans clusters

![image](https://github.com/MavillaPranathi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343610/c76df224-2d9a-4365-a8c0-4b8ff1cd7194)

y_predict

![image](https://github.com/MavillaPranathi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343610/d846f8f2-7b50-470e-8ae6-f035bd153879)

 Customer segments Graph
 
![image](https://github.com/MavillaPranathi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343610/617ae534-8e1c-4a5d-af98-432bd6d9ad45)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
