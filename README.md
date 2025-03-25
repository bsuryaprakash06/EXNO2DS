# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
Developed By: Surya Prakash B
Reg.No: 212224230281

```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/d2f571d9-2adb-4be5-a035-a83e3c94fddf)

```
df.info()
```
![image](https://github.com/user-attachments/assets/3e7b013e-cef4-49dc-bab8-0f02f0aac0a4)
```
df.shape
```
![image](https://github.com/user-attachments/assets/8dfc4a05-2527-46d2-93b7-05dd330f24dc)


Categorical Data Analysis


```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/7a73c7cb-ffc2-4a89-a33d-cd38625ce048)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/71e5d1c1-e09e-4e60-b66d-5d46a8fe352c)

```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/bb3f519e-31b0-406e-a897-80e2e08bd3d6)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/524a4ff9-494e-4d3f-8be9-28d74ec865b5)

```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/aeebb0fa-9fc9-4df1-aa9d-23e357feba06)
```
df.Pclass.unique()
```
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/fdf8f88b-b51a-4e35-87c8-7eadee8d4b26)


Bivariate Analysis


```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/12b4dc89-23cf-455a-b633-0322bf264191)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/f7b1b331-421d-40be-85c1-ff300afaa598)

```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/0c748d5c-0a97-4910-bec8-44c0dc57f7c2)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/983846bd-510e-4687-8a99-3c4c9276b2de)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/3c44d9d4-9e12-4597-a076-c5d38efe979d)



Multi Variate Analysis
```

fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/86ff1c95-1b71-4988-bb78-1323f6bae4ec)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
```
numeric_df = df.select_dtypes(include=np.number)
corr = numeric_df.corr()
sns.heatmap(corr, annot=True)
```
![image](https://github.com/user-attachments/assets/adfd1c08-15cb-4a59-9f9a-55fc13f746f9)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/e4061fe9-b0b8-414d-a055-bae141e39396)

# RESULT
 We have performed Exploratory Data Analysis on the given data set successfully.
