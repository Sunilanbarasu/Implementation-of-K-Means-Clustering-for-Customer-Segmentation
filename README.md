# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import dataset and print head,info of the dataset

2.check for null values

3.Import kmeans and fit it to the dataset

4.Plot the graph using elbow method

5.Print the predicted array

6.Plot the customer segments
 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Sunil.A
RegisterNumber:  212224220113
*/

import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km=KMeans(n_clusters=5)

km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])

y_pred

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

plt.title("Customer Segment")
```

## Output:
# 1.Data.head():
![image](https://github.com/user-attachments/assets/751fc9f6-2f88-4a8f-baad-4c3913aab193)

# 2.Data.info():
![image](https://github.com/user-attachments/assets/298b04fc-834f-4058-a59d-e6eb412317a7)

# 3.Data.isnull().sum():
![image](https://github.com/user-attachments/assets/866e2b16-f4ad-4e84-9d7d-9bcc5208914b)

# 4.Plot using elbow method:
![image](https://github.com/user-attachments/assets/7257f944-6542-4685-a6db-6dc8e6465f96)

# 5. K_means Clustering:
![image](https://github.com/user-attachments/assets/ecd7de8e-2571-4f45-b76f-80c0f7e6cabb)

# 6.Y_pred Array:
![image](https://github.com/user-attachments/assets/6fec4db4-2a34-40e2-8d6b-5babb0c0e29b)

# 7.Customer Segment:
![image](https://github.com/user-attachments/assets/85895f5c-9ec8-4fae-a446-28e6639c065d)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
