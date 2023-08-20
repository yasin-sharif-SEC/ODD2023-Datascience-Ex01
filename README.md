# Ex-01_DS_Data_Cleansing


## AIM
To read the given data and perform data cleaning and save the cleaned data to a file. 

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect, incompleted, irrelevant, duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file

# CODE
```python
import pandas as pd

# Cleaning the file Data_set.csv
df1=pd.read_csv('Data_set.csv')
print('Data_set file before cleaning:')
df1.info()
df1.isnull().sum()
df1=df1.dropna(subset='show_name')
df=df1.dropna(subset='current_overall_rank')
df1['aired_on']=df1['aired_on'].fillna(df1['aired_on'].mode()[0])
df1['original_network']=df1['original_network'].fillna(df1['original_network'].mode()[0])
df1['rating']=df1['rating'].fillna(df1['rating'].mean())
df1['watchers']=df1['watchers'].fillna(df1['watchers'].median())

# data is cleaned
print('Data_set file after cleaning:')
df1.isnull().sum()

# Cleaning the file Loan_data.csv
df2=pd.read_csv('Loan_data.csv')
print('\nLoan_data file before cleaning:')
df2.info()
df2.isnull().sum()
df2=df2.dropna(subset='LoanAmount')
df2['Gender']=df2['Gender'].fillna(df2['Gender'].mode()[0])
df2['Dependents']=df2['Dependents'].fillna(df2['Dependents'].mode()[0])
df2['Self_Employed']=df2['Self_Employed'].fillna(df2['Self_Employed'].mode()[0])
df2['Loan_Amount_Term']=df2['Loan_Amount_Term'].fillna(df2['Loan_Amount_Term'].mode()[0])
df2['Credit_History']=df2['Credit_History'].fillna(df2['Credit_History'].mode()[0])

# data is cleaned
print('Loan_data file after cleaning:')
df2.isnull().sum()
```

# OUTPUT
## Data_set.csv file info
![01](https://github.com/yasin-sharif/ODD2023-Datascience-Ex01/assets/105559022/c72221db-db75-491f-906f-df68e2d36b6d)
## Data_set.csv duplicate data count
![02](https://github.com/yasin-sharif/ODD2023-Datascience-Ex01/assets/105559022/7eb8166b-9bd6-47a3-b100-082a3f7a414d)
## Data_set.csv after cleaning
![03](https://github.com/yasin-sharif/ODD2023-Datascience-Ex01/assets/105559022/316c305d-6ba2-4df8-b779-88f0a48cf416)
## Loan_data.csv file info
![04](https://github.com/yasin-sharif/ODD2023-Datascience-Ex01/assets/105559022/b33b8b19-1c41-489c-b488-9a0580aa4984)
## Loan_data.csv duplicate data count
![05](https://github.com/yasin-sharif/ODD2023-Datascience-Ex01/assets/105559022/81e3c5a5-fffd-490c-a7f1-4d361b1aa5bd)
## Loan_data.csv after cleaning
![06](https://github.com/yasin-sharif/ODD2023-Datascience-Ex01/assets/105559022/10c1c78e-5253-4e96-a153-b1192b8b796c)

# RESULT
Thus, the given data is read, cleansed and the cleaned data is saved into the file. 







