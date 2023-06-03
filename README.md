# Ex-04-Multivariate-Analysis

# AIM:
To perform Multivariate EDA on the given data set.

# Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## DATE:

GITHUB LINK:

COLAB LINK:https://colab.research.google.com/drive/1cHEEDnCEjcEnwpTP1Lu28j1pRjnw4DXp#scrollTo=MS0DUht3BP3E

# Algorithm:

## STEP 1 

Import the built libraries required to perform EDA and outlier removal.

## STEP 2 

Read the given csv file.

## STEP 3 

Convert the file into a dataframe and get information of the data.

## STEP 4 

Return the objects containing counts of unique values using (value_counts()).

## STEP 5 

Plot the counts in the form of Histogram or Bar Graph.

## STEP 6 

Use seaborn the bar graph comparison of data can be viewed.

## STEP 7 

Find the pairwise correlation of all columns in the dataframe.corr()

## STEP 8 

Save the final data set into the file.

#  CODE:

DEVELOPED BY: VISWA PRIYA G

REGISTER NUMBER: 212221220061

```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from google.colab import files
uploaded = files.upload()
df = pd.read_csv("SuperStore.csv")
df

df.info()

df.describe()

df.isnull().sum()

df['Sales'] = df["Sales"].fillna(df['Sales'].mode()[0])
df.isnull().sum()

df.dtypes

sns.scatterplot(df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Sales",data=states)
df.info()

states=df.loc[:,["Postal Code","Sales"]]
states=states.groupby(by=["Postal Code"]).sum().sort_values(by="Sales")
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("Postal Code")
plt.ylabel=("SALES")
plt.show()

states=df.loc[:,["Segment","Sales"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("Segment")
plt.ylabel=("Sales")
plt.show()

df.corr()

sns.heatmap(df.corr(),annot=True)

```

# OUTPUT:

Dataset

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/01.jpg)

Dataset information

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/02.jpg)

Data describe

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/03.jpg)

Checking and cleaning of null values

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/04.jpg)

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/05.jpg)

Data types

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/06.jpg)

Scatterplot

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/07.jpg)

Barplot

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/08.jpg)

![plot](https://github.com/viswapriyaG/Ex-04-Multivariate-Analysis/assets/131427787/9ff41518-93e4-4592-b42e-c39e50370ff9)

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/10.jpg)

Correlation coefficient interpretation

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/11.jpg)

Heatmap

![](https://github.com/Hariharan5354/Ex-04-Multivariate-Analysis/blob/main/12.jpg)

# RESULT:

Thus we have read the given data and performed the multivariate analysis with different types of plots.
