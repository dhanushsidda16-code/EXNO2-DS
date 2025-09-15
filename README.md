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
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset (1).csv")
df
```      
<img width="1477" height="521" alt="Screenshot 2025-09-15 114051" src="https://github.com/user-attachments/assets/d4313809-a192-4c05-9fc4-3da1477a9adc" /> 

```
df.info()
```
<img width="569" height="422" alt="Screenshot 2025-09-15 114219" src="https://github.com/user-attachments/assets/ab733a62-64d1-4891-be2d-4a79f9384681" /> 

```
df.describe()
```
<img width="917" height="369" alt="Screenshot 2025-09-15 114235" src="https://github.com/user-attachments/assets/3c745af0-94d9-43ca-81f8-0f625f503ecc" /> 

```
df.dtypes
```
<img width="277" height="563" alt="Screenshot 2025-09-15 114253" src="https://github.com/user-attachments/assets/d0302155-e141-4832-8320-a1a6fb9f3b17" /> 

```
df.shape
```
<img width="189" height="83" alt="Screenshot 2025-09-15 114307" src="https://github.com/user-attachments/assets/0b218a21-80cb-496c-a60b-b5941ef459e4" /> 

```
df['Age'].value_counts()
```
<img width="1567" height="599" alt="Screenshot 2025-09-15 114327" src="https://github.com/user-attachments/assets/b5aae641-cf22-4f50-aacc-f9c524fbead6" /> 

```
df.set_index('PassengerId',inplace=True)
df
```
<img width="248" height="612" alt="Screenshot 2025-09-15 114343" src="https://github.com/user-attachments/assets/91589c61-7d31-4456-9fd2-677be3270464" /> 

```
df.nunique()
```
<img width="292" height="538" alt="Screenshot 2025-09-15 114425" src="https://github.com/user-attachments/assets/3d8dc5d1-77f2-427d-b8ab-5c1809f25efa" /> 

```
sns.countplot(data=df,x='Survived')
```
<img width="798" height="583" alt="Screenshot 2025-09-15 114529" src="https://github.com/user-attachments/assets/3eb84367-76fa-4517-9342-d2ac87e3c201" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1447" height="561" alt="Screenshot 2025-09-15 114549" src="https://github.com/user-attachments/assets/9a9527c8-00a5-4a43-86b0-83f0fda6d5a9" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
<img width="1019" height="651" alt="Screenshot 2025-09-15 114611" src="https://github.com/user-attachments/assets/67b0f6f0-e2c0-4c29-8f47-728af0c305a6" /> 

```
df.boxplot(column='Age',by='Survived')
```
<img width="784" height="613" alt="Screenshot 2025-09-15 114647" src="https://github.com/user-attachments/assets/cc70a93d-ce42-464b-b90f-8ca7cbe8381e" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="896" height="585" alt="Screenshot 2025-09-15 114707" src="https://github.com/user-attachments/assets/95e8bdd5-e340-458d-815c-09ad53b4dd75" /> 

```
df.rename(columns={'Sex':'Gender'},inplace=True)
fig, ax1 = plt.subplots(figsize=(8, 5))
sns.boxplot(x='Pclass', y='Age', hue='Gender', data=df, ax=ax1)
```
<img width="964" height="588" alt="Screenshot 2025-09-15 114720" src="https://github.com/user-attachments/assets/0ebc8dcd-ce82-4955-b309-c2ffb3ac33d5" /> 

```
import seaborn as sns
sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind='box',data=df)
```
<img width="1424" height="645" alt="Screenshot 2025-09-15 114740" src="https://github.com/user-attachments/assets/c2b69e6e-3459-4d78-80df-f00596656dd9" /> 

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="892" height="638" alt="Screenshot 2025-09-15 114811" src="https://github.com/user-attachments/assets/fb9f0e27-051a-4aa3-8b59-0aeb3d64765b" />

# RESULT 
Thus exploratory data analysis on the given dataset has been executed successfully.
        
