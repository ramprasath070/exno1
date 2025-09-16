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
import numpy as np
import pandas as pd
df = pd.read_csv("SAMPLEIDS.csv")
df
```
<img width="992" height="847" alt="image" src="https://github.com/user-attachments/assets/ee153505-edde-432e-a3a2-584524414f06" />

```
df.head()
```
<img width="977" height="253" alt="image" src="https://github.com/user-attachments/assets/d8a2a1d1-047c-4454-801a-03a78bf0d586" />

```
df.tail()
```
<img width="998" height="247" alt="image" src="https://github.com/user-attachments/assets/fda2b0f3-62ae-40fc-aae6-551e63ef5033" />

```
df.isnull()
```
<img width="821" height="855" alt="image" src="https://github.com/user-attachments/assets/f66fa59f-f3fe-46d8-b25e-c5f6b0161927" />

```
df.isnull().sum()
```
<img width="172" height="557" alt="image" src="https://github.com/user-attachments/assets/be3221c3-0b7e-4bd3-ba5d-1de92e0cd2cf" />



```
df.dropna()
```
<img width="1053" height="561" alt="image" src="https://github.com/user-attachments/assets/269afcad-5a0c-4f5e-ad93-458f2b3d157f" />

```
df.fillna(5)
```
<img width="1078" height="871" alt="image" src="https://github.com/user-attachments/assets/67e6932a-b280-4859-a6e6-723e096d1ba4" />


```
df.fillna({'GENDER': 'MALE','NAME':'RAM','TOTAL':602.5,'AVG':108.057777})
```
<img width="1021" height="857" alt="image" src="https://github.com/user-attachments/assets/f541c7eb-db79-4e40-8a9d-c3ce748d7816" />

```
ir = pd.read_csv('iris.csv')
ir
```
<img width="665" height="517" alt="image" src="https://github.com/user-attachments/assets/961691bb-50a3-4662-84ec-6b70055964e7" />

```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
<img width="716" height="575" alt="image" src="https://github.com/user-attachments/assets/310bebb4-99ff-483b-906a-97deff9f86ef" />

```
q1 = ir.sepal_width.quantile(0.25)
q3 = ir.sepal_width.quantile(0.75)
iqr = q3 - q1
print(iqr)
```
<img width="117" height="42" alt="image" src="https://github.com/user-attachments/assets/20b2308c-233a-4343-8b45-56a851cc8bfb" />

```
rid = ir[((ir.sepal_width<(q1-1.5*iqr)) |(ir.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']
```
<img width="258" height="268" alt="image" src="https://github.com/user-attachments/assets/02a9a853-a7c0-469a-b4a4-46938d6cb35d" />

```
delid = ir[~((ir.sepal_width<(q1-1.5*iqr)) |(ir.sepal_width>(q3+1.5*iqr)))]
delid
```
<img width="727" height="527" alt="image" src="https://github.com/user-attachments/assets/974f0ed1-a01c-48af-8a16-e93de5684349" />

```
sns.boxplot(x='sepal_width',data=delid)
```
<img width="717" height="575" alt="image" src="https://github.com/user-attachments/assets/385d6d00-add6-4f8b-b9a1-b8cb5fdcb0d5" />

```
import numpy as np
import scipy.stats as stats
z = np.abs(stats.zscore(ir['sepal_width']))
z
```
<img width="757" height="660" alt="image" src="https://github.com/user-attachments/assets/eaf09dc4-f56b-40e5-bf4b-3b770f5db8fd" />



# Result
Thus to read the given data and perform data cleaning and save the cleaned data to a file done successfully.


