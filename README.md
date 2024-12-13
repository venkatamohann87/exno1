# Exno:1
Data Cleaning Process

## Name: VENKATA MOHAN N
## REGISTER NO: 24900969
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
###### import pandas as pd 
###### df=pd.read_csv("/content/sampleIDS/.csv")
###### df




![image](https://github.com/user-attachments/assets/c814aec5-4a62-4ad5-a6ff-de388bc89a4f)

###### df.head()

![image](https://github.com/user-attachments/assets/8b6602e1-4272-4dd6-987f-d24d7cd4b62c)

###### df.tail(5)

![image](https://github.com/user-attachments/assets/30f8a730-0ba3-49d5-8e3e-60921f4623d8)

###### df.isnull()
![image](https://github.com/user-attachments/assets/f6c0523a-ec2e-49e2-9a05-f5868793b10e)

df.notnull()

![image](https://github.com/user-attachments/assets/f2094bc9-c262-417b-8a29-8b767c984987)
df.dropna(axis=0)

![image](https://github.com/user-attachments/assets/7d59f6cf-fcc1-4079-bb78-a3b1ec7d5e88)
df.dropna(axis=1)

![image](https://github.com/user-attachments/assets/f0a124fd-ae63-4ee5-93cd-36294a8a7d08)
###### df.fillna(0)
![image](https://github.com/user-attachments/assets/1ed378d6-2eb9-43cd-a3f4-c599f0075f92)

### IQR:
import pandas as pd 
##### import seaborn as sns
##### ir=pd.read_csv('/content/iris.csv')
##### ir
![image](https://github.com/user-attachments/assets/007e469e-a6be-4f1e-8045-bdb1599b462d)

ir.describe()
![image](https://github.com/user-attachments/assets/8d89737c-0e6b-438d-a469-088c08bee22b)

sns.boxplot(x="sepal_width',data=ir)

![image](https://github.com/user-attachments/assets/f9f72454-a0d6-4d65-8d70-cc45beb89376)

c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
#### =3.3
rid=ir[((ir.sepal_width<(c1-1.5*iqr))&(ir.sepal_width>(c3+1.5*iqr)))]
rid["sepal_width]
![image](https://github.com/user-attachments/assets/662e7f55-e72a-49e0-8261-de1bcf94143d)
dtype:float64
###### delid =ir[~()ir.sepal_width<(c1-1.5*iqr))&(ir.sepal_width>(c3+1.5*iqr)]

##### delid
![image](https://github.com/user-attachments/assets/b2554188-09af-4cad-a789-bb901b3cc6f3)
sns.boxplot(x="sepal_width",data=delid)
![image](https://github.com/user-attachments/assets/023aa261-14bd-48e4-b937-be666f7c187b)

### z score


impot matplotlib.pyplot as plt
##### import pandas as pd
###### import numpy as np
import scipy .stats as stats
###### dataset=pd.read_csv("/content/heights.csv")
dataset

![image](https://github.com/user-attachments/assets/401f1e4c-f0d2-4f1d-97be-d15504014c0c)

df=pf.read _csv("heights.csv")
###### q1=df["heights"].quantile(0.25)
###### q2=df["heights"].quantile(0.5)
###### q3=df["heights"].quantile(0.75)
iqr=q3-q1
###### =0.9249999999998

low=q1-1.5*iqr
###### low
##### =3.8625000000000003
high=q2+1.5*iqr
###### high
##### =7.5625

df11=df[((df["heights"]>=low)&(df["heights"]<=high))]
###### df11
![image](https://github.com/user-attachments/assets/c6f8e593-1553-43a7-a8fe-0841b5dd2855)

z=np.abs(stats.zscore(df["heights"]0))
###### z
![image](https://github.com/user-attachments/assets/2a9e1ff1-4dd5-4ce4-b822-8e5f51dd82c2)

df11=df[z<3]
###### df11
![image](https://github.com/user-attachments/assets/9a4cf8a2-17cf-492a-9e2f-cb3e0fa4c8b8)



# Result
        thus the data cleaning process and detecting and removal of outliers are executed sucessfully  
