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
```python
import pandas as pd
import numpy as np
data = pd.read_csv("/content/SAMPLEIDS.csv")
```

## Output
<img width="682" height="581" alt="image" src="https://github.com/user-attachments/assets/8ef3a92c-0538-4df1-a862-63c75339d088" />

```python
data.head(4)
```

## Output
<img width="658" height="137" alt="image" src="https://github.com/user-attachments/assets/ad083600-013e-427c-a78a-46641347ff64" />

```python
data.tail(7)
```

## Output
<img width="677" height="217" alt="image" src="https://github.com/user-attachments/assets/4657113c-a842-4dcb-b15c-b654966c7626" />

```python
data.isnull()
```

## Output
<img width="560" height="587" alt="image" src="https://github.com/user-attachments/assets/d055dd3c-6999-4e45-ad12-8fca0b4425f2" />

```python
data.notnull()
```
## Output
<img width="536" height="587" alt="image" src="https://github.com/user-attachments/assets/b33ce0d5-6390-48c2-b538-3822c751eb47" />

```python
data.isnull().sum()
```
## Output
<img width="118" height="374" alt="image" src="https://github.com/user-attachments/assets/8209f5a2-d14b-40c2-8f0c-24e7de394c16" />

```python
data.isnull().any()
```
## Output
<img width="124" height="378" alt="image" src="https://github.com/user-attachments/assets/c3551be8-acac-45a5-9a30-b5dd95ac83db" />

```python
data.dropna(axis=1)
```
## Output
<img width="199" height="585" alt="image" src="https://github.com/user-attachments/assets/b60d9cf9-d187-4c3b-8b3d-685f6fc6aa6a" />

```python
data.dropna(axis=0)
```
## Output
<img width="679" height="376" alt="image" src="https://github.com/user-attachments/assets/608d5cf6-2127-4e04-96ba-a1f48f43dfe0" />

```python
data.fillna(0)
```
## Output
<img width="675" height="584" alt="image" src="https://github.com/user-attachments/assets/a77c96cd-40a5-4dd4-a5ca-1cf07c2c3d7d" />

```python
data.fillna(method="ffill")
```
## Output
<img width="675" height="576" alt="image" src="https://github.com/user-attachments/assets/f6c6031f-46da-4d80-be2c-3dce15fd7c2c" />

```python
data.bfill()
```
## Output
<img width="680" height="581" alt="image" src="https://github.com/user-attachments/assets/b78ea053-d515-4732-97cf-0183eeb45e3b" />

```python
data.fillna({'REGNO':0, 'NAME':'PRAVEEN'})
```
## Output
<img width="679" height="578" alt="image" src="https://github.com/user-attachments/assets/c3e164ca-d968-4905-84b4-96bea85b4651" />

```python
 ir=pd.read_csv("/content/iris.csv")
 ir
```
## Output
<img width="442" height="315" alt="image" src="https://github.com/user-attachments/assets/07f790bf-b505-453c-ac39-defbac1298b5" />

```python
ir.describe()
```
## Output
<img width="398" height="243" alt="image" src="https://github.com/user-attachments/assets/90b30b84-beb0-441e-970a-eee2dd22e624" />

```python
import seaborn as sns
sns.boxplot(x="sepal_width",data=ir)
```
## Output
<img width="450" height="380" alt="image" src="https://github.com/user-attachments/assets/9f01cd59-c441-479d-b7e7-8710b4f7bc34" />

```python
q1=ir.sepal_width.quantile(0.25)
q3=ir.sepal_width.quantile(0.75)
iqr=q3-q1
print(iqr)
```
## Output
<img width="116" height="164" alt="image" src="https://github.com/user-attachments/assets/45f1a717-acd4-4f2f-b909-8f7fb01c665e" />

```python
 rid=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
 rid
```
## Output
<img width="446" height="343" alt="image" src="https://github.com/user-attachments/assets/61a35c04-7453-4f34-a18a-698a19c0e13d" />

```python
rid=ir[((ir.sepal_width>(q1-1.5*iqr))&(ir.sepal_width<(q3+1.5*iqr)))]
rid['sepal_width']
```
## Output
<img width="131" height="377" alt="image" src="https://github.com/user-attachments/assets/6b77bdc6-4ba6-492c-806a-22755649de13" />

```python
 import numpy as np
 import scipy.stats as stats
 z=np.abs(stats.zscore(ir.sepal_width))
 z
```
## Output
<img width="481" height="446" alt="image" src="https://github.com/user-attachments/assets/b4670f95-e1d8-4686-a5ee-34b1ee9d7571" />

# Result
Thus, the programs are executed successfully.
