# Implementation of K Means Clustering for Customer Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.

2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3. Import KMeans and use for loop to cluster the data.

4. Predict the cluster and plot data graphs.

5. Print the outputs and end the program.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: 212223230012
RegisterNumber:  AMALJOSH MAADHAV J
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
    kmeans = KMeans(n_clusters = i, init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
```
```
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

KMeans(n_clusters=5)

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
plt.title("Customers Segments")
```

## Output:
### Dataset
![image](https://github.com/amal-2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/148410730/e8603cec-123b-4d18-b875-90fc621b61ea)

### Dataset information
![image](https://github.com/amal-2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/148410730/3cffe4fb-91f4-43d1-b78f-0c869e19648d)

![image](https://github.com/amal-2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/148410730/16b7e63b-f2ef-43dc-baa3-2f506f4e19ac)

### Elbow Method
![image](https://github.com/amal-2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/148410730/7ce56d51-19b5-467d-9ca4-4d290967552d)

### y_pred
![image](https://github.com/amal-2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/148410730/7fbac409-1c9a-49dd-b11e-e2e5e20f2687)

### Cluster representing customer-segment graph
![image](https://github.com/amal-2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/148410730/6cf1f431-85f7-48fc-853a-069ca74190b2)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
