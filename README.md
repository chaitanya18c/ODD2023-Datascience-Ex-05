# Ex:05 Feature Generation

## AIM
To read the given data and perform Feature Generation process and save the data to a file. 

# Explanation
<B>Feature Generation </B>(also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
 

# ALGORITHM
### STEP 1
Read the given Data.
### STEP 2
Clean the Data Set using Data Cleaning Process.
### STEP 3
Apply Feature Generation techniques to all the feature of the data set.
### STEP 4
Save the data to the file.


# CODE
```
Developed by: CHAITANYA P S
Register number : 212222230024
```
## Data.csv:
```python
import pandas as pd
df1 = pd.read_csv("data.csv")
df.head()

df['Ord_1'].unique()

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot','Very Hot']
en= OrdinalEncoder(categories = [climate])
df['Ord_1']=en.fit_transform(df[["Ord_1"]])
df.head()

df['Ord_2'].unique()
cl = ['High School','Diploma','Bachelors','Masters','PhD']
en= OrdinalEncoder(categories = [cl])
df['Ord_2']=en.fit_transform(df[["Ord_2"]])
df.head()

le = LabelEncoder()
df['City'] = le.fit_transform(df[["City"]])
df.head()

from category_encoders import BinaryEncoder
be= BinaryEncoder()
data= be.fit_transform(df['bin_1'])
df= pd.concat([df,data],axis=1)
df.head()

from category_encoders import BinaryEncoder
be = BinaryEncoder()
data1 = be.fit_transform(df['bin_2'])
df= pd.concat([df1,data1],axis=1)
df  
```
## Encoding data:
```python
import pandas as pd
df=pd.read_csv('Encoding Data.csv')
df.head()

df['ord_2'].unique()

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot']
en= OrdinalEncoder(categories = [climate])
df['ord_2']=en.fit_transform(df[["ord_2"]])
df

le = LabelEncoder()
df['Nom_0'] = le.fit_transform(df[["nom_0"]])
df  

from category_encoders import BinaryEncoder
be = BinaryEncoder()
data = be.fit_transform(df['bin_1'])
df = pd.concat([df,data],axis=1)
df

be = BinaryEncoder()
data = be.fit_transform(df['bin_2'])
df = pd.concat([df,data],axis=1)
df
```
## BMI.csv:
```python
import pandas as pd
df2 = pd.read_csv("/content/bmi.csv")
df2.head()

be = BinaryEncoder()
data2 = be.fit_transform(df2['Gender'])
df2  = pd.concat([df2,data2],axis=1)
df2

df2 = pd.get_dummies(df2, prefix=['Index'] ,columns=['Index'])
df2
```

## OUTPUT
## (i) Data.csv
- Initial data:<br>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/ddebf336-fb4a-45f8-ae2f-105cde4306d1" height=150 width=350>

- Unique data:<br>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/63bedcca-5098-46cb-a4ee-b9f30e46e0f8">

- Original Encoder:<br>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/a1d8f594-138d-40ca-8bd6-34fc61aea169" height=150 width=350>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/82ba85de-0a39-45ba-9320-625cdfef09e5" height=150 width=350>

- Label Encoder:<br>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/b9d90f43-9965-4308-b874-93ed47a9f086" height=150 width=350>

- Binary Encoder:<br>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/f909b514-5252-48f4-8777-d64923f523fd" height=150 width=350>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/911205b9-1133-4d12-9f23-76ae4986ab8d" height=150 width=350>

## (ii) Encoding data.csv
- Initial data:<br>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/7f18f90e-2783-4c94-9812-4b00cddffa55" height=150 width=250>

- Unique data:<br>Dummies
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/5ec8f4f4-3487-49ba-8ab1-56b9d7be57ea">

- Original Encoder:<br>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/23fb20b3-83e9-4610-84c9-68f48151b5a7" height=350 width=250>

- Label Encoder:<br>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/6d06a2dd-b136-491b-9bed-c84028d1f14d" height=350 width=250>

- Binary Encoder:<br>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/4ba2a8ba-cb12-46f2-b74b-39d2393c7d0e" height=250 width=250>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/195af4af-0fc1-49d9-a110-466a673c2acf" height=250 width=250>

## (iii) BMI.csv
- Initial data:<br>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/47624b9f-afbf-413a-a481-080fe2b7614b" height=250 width=300>

- Binary Encoder:<br>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/3e9dddb0-5201-4bec-9938-7a7ac5bebd74" height=250 width=350>

- Dummies:<br>
<img src="https://github.com/Janarthanan2/ODD2023-Datascience-Ex-05/assets/119393515/9b98e8fe-d3d1-4256-a3ec-2721994bda27" height=350 width=550>


## Result:
Thus the Feature Generation and Feature Scaling process is applied to the given data set.
