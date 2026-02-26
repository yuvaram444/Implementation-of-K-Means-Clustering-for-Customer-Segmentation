# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load and preprocess data: Import data, inspect it, and handle missing values if any.
2. Determine optimal clusters: Use the Elbow Method to identify the number of clusters by plotting WCSS against cluster numbers.
3. Fit the K-Means model: Apply K-Means with the chosen number of clusters to the selected features.
4. Assign cluster labels to each data point.
5. Plot data points in a scatter plot, color-coded by cluster assignments for interpretation.

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: YUVARAM S
RegisterNumber: 212224230315
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
```
```
data.head()
```
```
data.info()
```
```
data.isnull().sum()
```
```
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++",n_init=10)
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
```
```    
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
```
```
km = KMeans(n_clusters=5, n_init=10)
km.fit(data.iloc[:, 3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
```
```
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
```
```
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster1")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster2")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster4")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster5")
plt.legend()
plt.title("Customer Segments")
```

## Output:
<img width="1121" height="198" alt="image" src="https://github.com/user-attachments/assets/0f285a4e-486a-48f0-afd1-e297e37f450e" />
<img width="1117" height="240" alt="image" src="https://github.com/user-attachments/assets/e6008719-33fa-41a3-9896-d9279421c0af" />
<img width="1118" height="138" alt="image" src="https://github.com/user-attachments/assets/084f7fc6-c514-44de-88f5-49a7f725f3df" />
<img width="1119" height="551" alt="image" src="https://github.com/user-attachments/assets/c4a67553-ab32-43aa-9870-07d33fda9312" />
<img width="1118" height="210" alt="image" src="https://github.com/user-attachments/assets/7c8a443a-8614-4ea7-bd8e-23720612789e" />
<img width="1119" height="532" alt="image" src="https://github.com/user-attachments/assets/dae09c1f-4796-4b81-881d-fc3cc6141e4c" />









## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
