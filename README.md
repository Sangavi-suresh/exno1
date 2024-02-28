# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output

```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/ab31b7f2-bdf4-4c88-b5c5-5cba0e994202)

```
print(df.head(7))
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/690fae64-e0e2-4a0b-a70d-e720fe6862c6)

```
print(df.tail(2))
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/97015bba-e2eb-4cfd-b734-dd299509abac)

```
df.info()
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/322e58de-9f38-4ec5-a6a2-2f8a92880ddb)


```
print(df.describe())
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/e44467ab-c889-450c-a1b0-8d9ccda2edab)


```
df.isnull().sum()
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/446fcecf-541b-44f8-9567-5ae3671e8274)

```
df.nunique()
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/19a4e3ee-121e-4e24-902b-1c4d1dfb9310)


```
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/76fe5bec-f4f0-4854-9ed8-156b818c652d)


```
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/a542ae2e-9cf3-4812-bb87-e771629ea27b)

```
min=df.M4.min()
min
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/79200c1d-b9e6-470b-895f-15e8cb4a3cf4)


```
df.M4.fillna(min,inplace=True)
df
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/cc35123a-d6f6-47cb-b750-7236662c969a)
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/61d393d4-fbd1-408b-bd9b-77f692dda4dd)

```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/aa1646d0-c884-4a8e-89de-c7f4dc067922)


```
sns.boxplot(data=af)
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/9eb34ffe-9d31-4693-802c-601999e73492)

```
sns.scatterplot(data=af)
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/2d7e4831-2dce-43fa-8351-fd92d8929e38)


```
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/473e6703-c66d-4fef-b272-463b6936a359)

```
af=af[((af>=low)&(af<=high))]
af
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/5f7363db-634b-4087-890f-b844f9ddd10e)


```
af.dropna()
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/20de3f01-d8c8-41cc-99a1-86e8e73f829e)

```
sns.boxplot(data=af)
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/c742661c-d7f4-418f-868d-1e5f471f02d3)

```
sns.scatterplot(data=af)
```

![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/60149721-d0a9-42d7-8787-f35736864149)

```
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/38bd5317-4adb-456a-afad-95bc6b7baa5b)

```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![image](https://github.com/Sangavi-suresh/exno1/assets/118541861/4665d2e4-ec15-4f82-9967-7ebef1281c85)






# Result
     
Thus the given program executed successfully.
