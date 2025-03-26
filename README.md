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
NAME : VINODINI R
REG NO : 212223040244
```

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```
dt=pd.read_csv("/content/titanic_dataset.csv")
```
```
dt
```
<img width="775" alt="d21" src="https://github.com/user-attachments/assets/9b158723-8628-4afb-960f-719269c88c0b" />

```
dt.info()
```
<img width="576" alt="d2" src="https://github.com/user-attachments/assets/e5fcb6ae-60fc-4fd5-aae2-28df4fabd154" />

```
dt.set_index("PassengerId",inplace=True)
```
```
dt.describe()
```
<img width="576" alt="d3" src="https://github.com/user-attachments/assets/6c88937b-6c10-4b0b-9a7f-dc95773909bd" />


```
dt.shape
```
<img width="576" alt="d4" src="https://github.com/user-attachments/assets/b2e5ef01-4aaf-48c3-b0ad-77e665e9806d" />


```
dt.nunique()
```
<img width="576" alt="d5" src="https://github.com/user-attachments/assets/a7f0ba82-c599-4de7-96ed-6182a09601a0" />

```
dt["Survived"].value_counts()
```
<img width="576" alt="d6" src="https://github.com/user-attachments/assets/dca9efce-9416-4d7b-abd4-5efb53b39a89" />


```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```

<img width="576" alt="d7" src="https://github.com/user-attachments/assets/0da85651-4e43-4fc9-9200-6164f9cf8478" />

```
sns.countplot(data=dt,x="Survived")
```
<img width="576" alt="d8" src="https://github.com/user-attachments/assets/130621d1-4207-4a22-97f4-ce7c451710c3" />


```
dt.Pclass.unique()
```
<img width="576" alt="d9" src="https://github.com/user-attachments/assets/fb10fcb7-11bc-4b90-bd41-47858b76214f" />

```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```

<img width="835" alt="d10" src="https://github.com/user-attachments/assets/c9bdd853-c093-47f3-a5ee-3623897b999a" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
<img width="576" alt="d11" src="https://github.com/user-attachments/assets/7ca54b04-6c19-4335-a0c3-808440320026" />

```
sns.catplot(x="Survived",hue="Gender",data=dt,kind="count")
```


<img width="576" alt="d12" src="https://github.com/user-attachments/assets/9b78dfd4-3942-4411-a3fd-13841e5e7d1e" />

```
sns.catplot(x="Survived",hue="Gender",data=dt,kind="count")
```


<img width="576" alt="d13" src="https://github.com/user-attachments/assets/b8423b09-6d4c-4112-b644-06154ab51474" />

```
sns.scatterplot(x=dt["Age"],y=dt['Fare'])
```

<img width="576" alt="d14" src="https://github.com/user-attachments/assets/4024b120-846d-4e46-a948-a1304a9a0411" />

```
sns.jointplot(x="Age",y="Fare",data=dt)
```


<img width="576" alt="d15" src="https://github.com/user-attachments/assets/5b00a35d-41b1-49e2-b463-7d9ab7147515" />

```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```


<img width="576" alt="d16" src="https://github.com/user-attachments/assets/c05d8a65-9456-4cff-90e7-424a1434036c" />

```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```

<img width="804" alt="d17" src="https://github.com/user-attachments/assets/eb800629-edcd-4d7b-ac61-49f118225296" />

```
corr=dt.select_dtypes(include=['number']).corr()
sns.heatmap(corr,annot=True)
```


<img width="576" alt="d18" src="https://github.com/user-attachments/assets/da6f1838-6cd0-475b-b720-d131f4dd870b" />

```
sns.pairplot(dt)
```


<img width="960" alt="d19" src="https://github.com/user-attachments/assets/7e413260-c7e5-42b7-b295-e6b76e898b44" />




<img width="960" alt="d20" src="https://github.com/user-attachments/assets/ba85dd4d-8d2f-4264-bbad-60b42b8d0a2b" />




# RESULT
      To perform Exploratory Data Analysis on the given data is successfully completed.
