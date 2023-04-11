# Ex-04-Multivariate-Analysis
AIM
To perform Multivariate EDA on the given data set.

Explanation
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

ALGORITHM
STEP 1
Import the built libraries required to perform EDA and outlier removal.

STEP 2
Read the given csv file

STEP 3
Convert the file into a dataframe and get information of the data.

STEP 4
Return the objects containing counts of unique values using (value_counts()).

STEP 5
Plot the counts in the form of Histogram or Bar Graph.

STEP 6
Use seaborn the bar graph comparison of data can be viewed.

STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

STEP 8
Save the final data set into the file

CODE
/* 
**Multivariate EDA - SuperStore.csv**
import pandas as pd
import numpy as np
import seaborn as sbn
import matplotlib.pyplot as plt
df = pd.read_csv("/content/SuperStore.csv")
df.head(10)
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sbn.scatterplot(df['Postal Code'],df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Postal Code"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")
plt.figure(figsize=(17,7))
sbn.barplot(x=states.index,y="Postal Code",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("Postal Code")
plt.show()
states=df.loc[:,["Segment","Sales"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")
#plt.figure(figsize=(10,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("SALES")
plt.show()
sbn.barplot(df['Postal Code'],df['Ship Mode'],hue=df['Region'])
df.corr()
sbn.heatmap(df.corr(),annot=True)
*/

OUPUT
EDA - SuperStore.csv
![image](https://user-images.githubusercontent.com/96919035/231137020-d415f833-dc3c-48a0-82b2-f6867769486f.png)

![image](https://user-images.githubusercontent.com/96919035/231137100-3c87c09b-c1f5-427a-9fa4-bb432e58accb.png)

![image](https://user-images.githubusercontent.com/96919035/231137215-93d69d34-9d04-41b5-a9bd-7f677a523810.png)

![image](https://user-images.githubusercontent.com/96919035/231137262-af80f0ec-35d6-40aa-ac15-53d01edc8665.png)

![image](https://user-images.githubusercontent.com/96919035/231137333-705bd2bd-35e1-41e2-907a-58f3eb8770bf.png)

![image](https://user-images.githubusercontent.com/96919035/231137416-ea77d4dd-09ca-4b16-8446-2e7edd97286b.png)

![image](https://user-images.githubusercontent.com/96919035/231137480-8ae9a26c-a990-4104-9b96-e8284ba6657c.png)

RESULT
Thus the program to perform EDA on the given data set is successfully executed.

