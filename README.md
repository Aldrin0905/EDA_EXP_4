# EDA_EXP_4   Titanic Survival Analysis using Univariate Analysis

# NAME: ALDRIN.S
# REGISTER NO:212223240005

**Aim**

To perform univariate analysis on the Titanic dataset to understand the distribution and characteristics of individual variables (such as Age, Sex, Pclass, Fare, and Survived) and to draw insights about passengers and their survival patterns.


**Algorithm**

**1)Import Libraries:**

Load the required Python libraries (pandas, numpy, matplotlib, seaborn).

**2)Load the Dataset:**

Read the Titanic dataset from available sources (e.g., seaborn’s built-in Titanic dataset or a CSV file).

**3)Data Inspection:**

View the first few rows using head().

Get dataset summary using info() and describe().

**4)Handle Missing Data:**
Identify missing values using isnull().sum() and handle them appropriately (e.g., fill or drop).

**5)Univariate Analysis:**
Perform univariate analysis for each variable:

**Categorical Variables: (e.g., Sex, Pclass, Survived, Embarked)**
Use frequency tables and count plots.

**Numerical Variables: (e.g., Age, Fare)**
Use histograms, box plots, and summary statistics.

**6)Interpretation:**
Analyze distributions, central tendencies, and spread.
Identify patterns (e.g., more passengers in 3rd class, survival differences by gender).


**Program**

**Name : T.KAVINAJAI
Reg No.:212223100020**

**#Write your code here**

```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=sns.load_dataset("Titanic")
print("The first 5 rows are :")
df.head()
df.shape
df.isnull().sum()
df.info()
df.describe()
print(df['sex'].value_counts())
survived_percentage=df['survived'].value_counts(normalize=True)*100
dead=round(survived_percentage[0],3)
alive=round(survived_percentage[1],3)
print(f"Alive : {alive}")
print(f"Dead : {dead}")
df['pclass'].value_counts()
df['embarked'].value_counts()
df['deck'].value_counts(sort=True)
sns.histplot(df['age'],bins=30,kde=True,color='black')
print(f"mean : {df['age'].mean()}")
print(f"Median : {df['age'].median()}")
print(f"Range : {max(df['age']-min(df['age']))}")
sns.boxplot(df['fare'])
plt.grid(True)
sns.histplot(df['fare'],bins=30,kde=True,color='black')
Mean=df['fare'].mean()
Median=df['fare'].median()
print(f"Mean : {Mean}")
print(f"Median : {Median}")
if Mean > Median:
    print("Its positively skewed.")
else:
    print("Its negatively skewed.")
```

**Output**
<img width="1264" height="295" alt="image" src="https://github.com/user-attachments/assets/29dc0462-28c2-43ee-8388-39fbfb5dca9b" />
<img width="1174" height="576" alt="image" src="https://github.com/user-attachments/assets/b699f1d6-8d38-4f96-9bdb-445586ce7c91" />
<img width="939" height="573" alt="image" src="https://github.com/user-attachments/assets/6702d414-c236-49cb-b9d5-f42b549f0754" />
<img width="1189" height="624" alt="image" src="https://github.com/user-attachments/assets/21d4a99d-8f4f-4a94-a9f6-d0d930387200" />
<img width="1118" height="616" alt="image" src="https://github.com/user-attachments/assets/f563a43f-7ea7-4910-88a9-dc32f7a87a84" />
<img width="1117" height="560" alt="image" src="https://github.com/user-attachments/assets/1b7ce0b2-d656-439d-8fcf-5e8f093a4f3f" />
<img width="971" height="747" alt="image" src="https://github.com/user-attachments/assets/af161529-e86b-4c46-9b5f-4e84b81c9a5e" />
<img width="1110" height="884" alt="image" src="https://github.com/user-attachments/assets/d701b2ce-ab51-4f29-8fb6-40ff215453ef" />
<img width="564" height="301" alt="image" src="https://github.com/user-attachments/assets/da4dfca2-0d50-40e0-8fc6-311a75816baa" />


**Result**
From the univariate analysis:

Majority of passengers were male and in 3rd class.

Around 38% survived, majority being females and higher-class passengers.

Age is right-skewed with most passengers aged 20–40 years.

Fare distribution shows a few high outliers for 1st class passengers.

Thus, univariate analysis helps understand the distribution and spread of each individual feature in the Titanic dataset before moving to bivariate or multivariate analysis.

Visualization:
Plot appropriate charts for each variable using Matplotlib/Seaborn.
