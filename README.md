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
REG NO: 212224040345
NAME : B R SWETHA NIVASINI
```
```
import pandas as pd
import pandas as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset (2).csv")
dt
```

![Screenshot 2025-04-19 074249](https://github.com/user-attachments/assets/62c101fa-19b4-4dea-8238-0f0bc46ccca3)

```
dt.info()
```

![Screenshot 2025-04-19 074334](https://github.com/user-attachments/assets/50bc84ef-36e9-484e-8e71-2ea120afc71a)

```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```

![Screenshot 2025-04-19 074415](https://github.com/user-attachments/assets/6862904e-b4df-4226-82bf-6b4b8e9c30a9)

```
dt.shape
```
![Screenshot 2025-04-19 074453](https://github.com/user-attachments/assets/e44715f9-137a-4f24-a485-b9334b50e2d8)

```
dt.nunique()
```
![Screenshot 2025-04-19 074529](https://github.com/user-attachments/assets/98083da3-a9f6-4f67-831f-6d6de60c2da9)

```
dt["Survived"].value_counts()
```

![Screenshot 2025-04-19 074612](https://github.com/user-attachments/assets/345d83c5-d7d3-48a0-a777-a83866fd5cef)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```

![Screenshot 2025-04-19 074656](https://github.com/user-attachments/assets/c4e125c1-9f6d-4529-9d45-19ae1ba09514)

```
sns.countplot(data=dt,x ="Survived")
```

![Screenshot 2025-04-19 074742](https://github.com/user-attachments/assets/4476529a-8e82-456d-b66e-5a4e437c1fe9)

```
dt
```
![Screenshot 2025-04-19 074836](https://github.com/user-attachments/assets/796916f1-a2c2-497e-aab7-416cb25d364a)

```
dt.Pclass.unique()
```
![Screenshot 2025-04-19 074916](https://github.com/user-attachments/assets/b8d77f25-b7ef-4dfe-bff2-dc08a064bb2f)

```
dt.rename(columns={'Sex':'Gender'},inplace=True)
sns.catplot(x="Gender", col="Survived", kind="count", data=dt, height=5, aspect=0.7)
```

![Screenshot 2025-04-19 075006](https://github.com/user-attachments/assets/3e2e2685-bda0-40ea-8620-7931260b61ed)

```
sns.catplot(x='Survived', hue="Gender", data=dt, kind="count")
```
![Screenshot 2025-04-19 075045](https://github.com/user-attachments/assets/e92e59a1-2ec0-4b55-9a33-dceef6182ad5)

```
dt.boxplot(column="Age" ,by="Survived")
```
![Screenshot 2025-04-19 075137](https://github.com/user-attachments/assets/076113ff-866f-4505-ae78-8cef1ec1743b)

```
sns.scatterplot(x=dt["Age"] , y=dt["Fare"])
```
![Screenshot 2025-04-19 075217](https://github.com/user-attachments/assets/be189d26-0502-4e66-8e32-2708220c13e6)

```
fig, ax1 =  plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1, x='Pclass', y='Age' ,hue='Gender', data=dt)
```
![Screenshot 2025-04-19 075253](https://github.com/user-attachments/assets/5b7261db-3a8d-434d-8699-e53572ae187e)

```
sns.catplot(data=dt, col= "Survived", x= "Gender" , hue= "Pclass", kind= "count")
```
![Screenshot 2025-04-19 075340](https://github.com/user-attachments/assets/0baecf30-447a-48c9-99d7-8ae1f7ef8e83)

```
numerical_features = dt.select_dtypes(include=['number'])
corr = numerical_features.corr()
sns.heatmap(corr, annot=True)
```

![Screenshot 2025-04-19 075415](https://github.com/user-attachments/assets/7439a813-0d59-49a6-a7be-220dce197b83)

```
sns.pairplot(dt)
```
![Screenshot 2025-04-19 075557](https://github.com/user-attachments/assets/10b080bb-76f7-43ae-a652-9328293ad179)
![Screenshot 2025-04-19 075721](https://github.com/user-attachments/assets/1f12f7b1-9cf8-47fb-b829-45b585671ed2)
![Screenshot 2025-04-19 075802](https://github.com/user-attachments/assets/edbdd515-d095-4880-b779-2467c285bd9a)

























































































































# RESULT
Thus from the given data set Exploratory Data Analysis has successfully performed.
