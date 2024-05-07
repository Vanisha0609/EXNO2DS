# EXNO2 : EDA Analysis using Python
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
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/Vanisha0609/EXNO2DS/assets/119104009/37d66b8a-183b-44d1-a21a-a63ac0c99fc7)
```
df.info()
```
<img src="https://github.com/Vanisha0609/EXNO2DS/assets/119104009/0c33d5af-14a9-4bd8-b86e-1a23becd4288" width="300" height="280">

```
df.shape
```
![image](https://github.com/Vanisha0609/EXNO2DS/assets/119104009/5cabdea2-7e3f-40f7-bf51-a6e3511cbb2c)
```
df.set_index("PassengerId",inplace=True)
print(df.set_index)
```
<img src="https://github.com/Vanisha0609/EXNO2DS/assets/119104009/b5ceece4-dcf5-4c80-be96-520278cc4ec2" width="600" height="300">

<img src="https://github.com/Vanisha0609/EXNO2DS/assets/119104009/62ef7c48-ef95-41cf-9ddb-3e0c0c83f2a6" width="400" height="300">
```
df.nunique()
```

![image](https://github.com/Vanisha0609/EXNO2DS/assets/119104009/f243cbce-8d6b-4485-905d-aa5998da3604)
```
df["Survived"].value_counts()
```
![image](https://github.com/Vanisha0609/EXNO2DS/assets/119104009/54426581-989c-405e-8cc2-1a6425a2f4a3)

![image](https://github.com/Vanisha0609/EXNO2DS/assets/119104009/efad7363-c070-4704-8776-b74da77d04f2)
```
sns.countplot(data=df,x="Survived",color="pink")
```
<img src="https://github.com/Vanisha0609/EXNO2DS/assets/119104009/374a8d82-d2a4-44e0-ad9b-110019f68c5d" width="400" height="300">

```
df
```

![image](https://github.com/Vanisha0609/EXNO2DS/assets/119104009/be81124f-0772-43dc-82a5-d1702c54bc04)
```
df.Pclass.unique()
```

![image](https://github.com/Vanisha0609/EXNO2DS/assets/119104009/ce6e4a56-5fb4-4f50-b311-3093588d912e)

```
df.rename(columns={'sex':'Gender'},inplace=True)
df
```
<img src="https://github.com/Vanisha0609/EXNO2DS/assets/119104009/27303ebd-d00c-4764-8b77-3b87aa6e4a14" width="500" height="400">

```
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
sns.catplot(x="Sex",col='Survived',kind="count",data=df,height=5, aspect=.7,color="pink")
```
<img src="https://github.com/Vanisha0609/EXNO2DS/assets/119104009/04b75a9f-ad61-4da9-aa95-9a9d61edccf0" width="400" height="350">

```
custom={"male":"cornflowerblue","female":"lavender"}
sns.catplot(x='Survived',hue='Sex',data=df,kind='count',palette=custom)
```
<img src="https://github.com/Vanisha0609/EXNO2DS/assets/119104009/44f1046e-6033-458d-86f7-d5dcb29f4c7f" width="400" height="350">

```
df.boxplot(column='Age',by="Survived",color="red")
```
<img src="https://github.com/Vanisha0609/EXNO2DS/assets/119104009/c386b1b7-3b10-42d7-b461-fb111a831aac" width="400" height="300">

```
sns.scatterplot(x=df['Age'],y=df["Fare"],color="steelblue")
```
<img src="https://github.com/Vanisha0609/EXNO2DS/assets/119104009/69cf0d3a-e506-47bc-8007-a01c05154036" width="400" height="300">

```
import matplotlib.pyplot as plt
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=df,palette=custom)
```
<img src="https://github.com/Vanisha0609/EXNO2DS/assets/119104009/4df7b9c8-03f4-4b7b-a4c6-7e3f4708541a" width="400" height="300">

```
zenko={1:"skyblue",2:"cornflowerblue",3:"navy"}
sns.catplot(data=df,col='Survived',x='Sex',hue='Pclass',kind='count',palette=zenko)
```
<img src="https://github.com/Vanisha0609/EXNO2DS/assets/119104009/8076f5b2-6e8e-4646-9eaf-8d743f7921ce" width="400" heoght="300">

```
import seaborn as sns
corr=df.corr()
sns.heatmap(corr,annot=True)
```
<img src="https://github.com/Vanisha0609/EXNO2DS/assets/119104009/6118e549-a04b-4882-88a8-e966dc5ac3a6" width="400" height="300">

```
sns.pairplot(df)
```
<img src="https://github.com/Vanisha0609/EXNO2DS/assets/119104009/46c54cb9-783e-4de2-b7ef-7be2b297c0d8" width="500" height="350">

# RESULT
 Thus the Exploratory Data Analysis process is performed successfully on the given data using python code.
