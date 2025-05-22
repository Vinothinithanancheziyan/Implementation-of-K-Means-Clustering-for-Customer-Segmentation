# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

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

5. Print the outputs and end the program

## Program:
Program to implement the K Means Clustering for Customer Segmentation.

Developed by: VINOTHINI T
RegisterNumber: 212223040245
```python

import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv('Mall_Customers.csv')

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = [] #Within-Cluster Sum of Square.
#It is the sum of squared distance between each point & the centroid in a cluster

for i in range(1,11):
    kmeans = KMeans(n_clusters = i, init = "k-means++")
    kmeans.fit(data.iloc[:, 3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11), wcss)
plt.xlabel("Number of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:, 3:])
KMeans(n_clusters = 5)

y_pred = km.predict(data.iloc[:, 3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
![Image](https://github.com/user-attachments/assets/2c57fba9-05db-468a-ab76-3a20b9e37dab)

![Image](https://github.com/user-attachments/assets/462a9e2e-acc8-4131-92bc-3216d302e694)

![Image](https://github.com/user-attachments/assets/b79428bb-4de2-4039-8efd-37da62f8db9a)

![Image](https://github.com/user-attachments/assets/ea7ac083-35e9-47ea-84ea-12fdb344ea60)

![Image](https://github.com/user-attachments/assets/4f54f582-d347-4e85-b61a-f3b12c5b96a1)

![Image](https://github.com/user-attachments/assets/9cc774be-4ecc-4a35-a87d-a9aa0b27bf4b)

![Image](https://github.com/user-attachments/assets/57de202d-37ad-4984-a795-a6d6418adc99)

![Image](https://github.com/user-attachments/assets/2eaa3b3e-9afb-4e0b-8a73-9006653f91a0)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
