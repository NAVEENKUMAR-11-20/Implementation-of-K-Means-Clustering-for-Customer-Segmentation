# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
 1.Import pandas and matplotlib.pyplot
 2.Read the dataset and transform it
 3.Import KMeans and fit the data in the model
 4.Plot the Cluster graph

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: NAVEEN KUMAR P 
RegisterNumber:  24901080

import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

data = pd.read_csv("C:/Users/LENOVO/Downloads/Mall_Customers.csv")

data.head()


data.info()
print("Missing values in each column:")
print(data.isnull().sum())


wcss = []
for i in range(1, 11):
    kmeans = KMeans(n_clusters=i, init="k-means++", random_state=42)
    kmeans.fit(data.iloc[:, 3:]) 
    wcss.append(kmeans.inertia_)
plt.figure(figsize=(8, 5))
plt.plot(range(1, 11), wcss, marker='o')
plt.title("Elbow Method")
plt.xlabel("Number of Clusters")
plt.ylabel("WCSS")
plt.grid(True)
plt.show()
optimal_clusters = 5
kmeans = KMeans(n_clusters=optimal_clusters, init="k-means++", random_state=42)
kmeans.fit(data.iloc[:, 3:])
data["cluster"] = kmeans.labels_

df_clusters = [data[data["cluster"] == i] for i in range(optimal_clusters)]


plt.figure(figsize=(10, 7))
colors = ["red", "black", "blue", "green", "magenta"]
labels = [f"Cluster {i}" for i in range(optimal_clusters)]

for i, df in enumerate(df_clusters):
    plt.scatter(
        df["Annual Income (k$)"], df["Spending Score (1-100)"],
        c=colors[i], label=labels[i]
    )

plt.title("Customer Segments")
plt.xlabel("Annual Income (k$)")
plt.ylabel("Spending Score (1-100)")
plt.legend()
plt.grid(True)
plt.show()

*/
```

## Output:
![Screenshot 2024-12-11 133917](https://github.com/user-attachments/assets/7207cd6f-2a16-4a26-9fa7-772174d21752)
![Screenshot 2024-12-11 133940](https://github.com/user-attachments/assets/ef1da2a1-7778-48d9-8c57-d8874a5032d7)

![Screenshot 2024-12-11 133851](https://github.com/user-attachments/assets/591d9043-686a-4cfa-a8ae-a3c575b83a49)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
