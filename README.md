# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:
1.Import standard libraries in python for finding Implementation-of-K-Means-Clustering-for-Customer-Segmentation.

2.Initialize and print the data.head(),data.info(),data.isnull().sum()

3.Import sklearn.cluster import KMeans

4.Calculate the value of KMeans Clusters.

5.Plot the graph from Elbow method and find y_pred values .

6.Plot the graph from Customer Segments Graph.
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by:NAVEENAA V.R
RegisterNumber:212221220035 
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers.csv")

print("data.head() function:")
data.head()

print("data.info():")
data.info()

print("data.isnull().sum() function:")
data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[] #Within-Cluster Sum of Square.

for i in range(1,11):
kmeans=KMeans(n_clusters=i,init="k-means++")
kmeans.fit(data.iloc[:,3:])
wcss.append(kmeans.inertia_)
         
print("Elbow method Graph:")
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

print("KMeans clusters:")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

print("y_pred:")
y_pred=km.predict(data.iloc[:,3:])
y_pred

print("Customer segments Graph:")
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
## data.head()
![image](https://github.com/Naveenaa28/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131433133/71a80d7e-1d16-47bd-a04c-c93aa11ea4c2)
## data.info()
![image](https://github.com/Naveenaa28/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131433133/059c5aa9-7e80-4517-88c8-b55c65b4576f)
## data.isnull().sum()
![image](https://github.com/Naveenaa28/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131433133/d56bc72a-2f83-42d7-8063-0c4feb1a2bf6)
## Elbow method graph
![image](https://github.com/Naveenaa28/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131433133/5801e101-7103-4902-b3e0-472bd6ef8d8f)
## K Means clusters
![image](https://github.com/Naveenaa28/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131433133/94248b1c-2584-4d39-8366-b529e1253caf)
## y_pred
![image](https://github.com/Naveenaa28/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131433133/e766550c-561f-4a53-b7a5-db88b4e43c5a)
## Customers Segments Graph
![image](https://github.com/Naveenaa28/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131433133/5b4e80f3-d8cd-4edc-8f5c-467ba1fb545d)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
