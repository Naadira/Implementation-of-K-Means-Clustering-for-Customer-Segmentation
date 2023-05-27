# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import standard libraries in python for finding Implementation-of-K-Means-Clustering-for-Customer-Segmentation.
2. Initialize and print the data.head(),data.info(),data.isnull().sum()
3. Import sklearn.cluster import KMeans
4. Calculate the value of KMeans Clusters.
5. Plot the graph from Elbow method and find y_pred values .
6. Plot the graph from Customer Segments Graph.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Naadira Sahar N
RegisterNumber: 212221220034
*/

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers (1).csv")

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
![Screenshot (92)](https://github.com/Naadira/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135126/c2196681-6386-4049-944f-efa86feb587a)

![Screenshot (93)](https://github.com/Naadira/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135126/2e95b625-adab-406c-a51d-771efbcd5a7e)

![Screenshot (94)](https://github.com/Naadira/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135126/be036061-9bc8-4257-a369-5d521269e0a3)

![Screenshot (95)](https://github.com/Naadira/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135126/8f970182-18f8-4688-9e72-eb79bf2ed068)

![Screenshot (96)](https://github.com/Naadira/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135126/70c2f5b1-0fbc-4cf9-98ec-c8b84d4a823b)

![Screenshot (97)](https://github.com/Naadira/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135126/e30ab5bf-9954-45b4-bb2a-02e8aea567be)

![Screenshot (98)](https://github.com/Naadira/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/128135126/fe992493-332a-4cb0-b9c3-9204be9fd24d)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
