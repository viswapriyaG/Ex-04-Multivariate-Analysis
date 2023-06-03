# Ex-04-Multivariate-Analysis

# AIM:
To perform Multivariate EDA on the given data set.

# Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## DATE:

GITHUB LINK:https://github.com/viswapriyaG/Ex-04-Multivariate-Analysis.git

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

![mul](https://github.com/viswapriyaG/Ex-04-Multivariate-Analysis/assets/131427787/c01b2d65-8edf-428a-98b2-a4d39527eb6e)


Dataset information

![mul 3](https://github.com/viswapriyaG/Ex-04-Multivariate-Analysis/assets/131427787/47056652-4a7f-43b4-b2fd-28c5c5737f2e)


Data describe

![mul 4](https://github.com/viswapriyaG/Ex-04-Multivariate-Analysis/assets/131427787/b302a6a6-4b3f-4c36-a6fe-64c0b7457169)


Checking and cleaning of null values

![mul 5](https://github.com/viswapriyaG/Ex-04-Multivariate-Analysis/assets/131427787/ec817304-9597-460a-a459-18c88a92c337)

![mul 7](https://github.com/viswapriyaG/Ex-04-Multivariate-Analysis/assets/131427787/d5f1d884-f81d-479e-8bd7-706d9cc61948)


Data types

![mul 6](https://github.com/viswapriyaG/Ex-04-Multivariate-Analysis/assets/131427787/0462c572-f867-4026-b35f-cd8e0e2cac9b)

Scatterplot

![mul 8](https://github.com/viswapriyaG/Ex-04-Multivariate-Analysis/assets/131427787/3107aba9-ac4a-4af5-8d01-992a6d4c9891)

Barplot

![mul 9](https://github.com/viswapriyaG/Ex-04-Multivariate-Analysis/assets/131427787/44c43a4b-0512-4006-a1eb-5ae45bc653bd)

![plot](https://github.com/viswapriyaG/Ex-04-Multivariate-Analysis/assets/131427787/7f61b65a-3ce1-424a-80cb-8347a6b2ae8c)

![mul 10](https://github.com/viswapriyaG/Ex-04-Multivariate-Analysis/assets/131427787/934ab9bd-a79e-4fed-8620-232f19c7f082)

![mul 12](https://github.com/viswapriyaG/Ex-04-Multivariate-Analysis/assets/131427787/6d0c2f4f-79a2-4320-b4f8-e09104498639)


Correlation coefficient interpretation

![mul 11](https://github.com/viswapriyaG/Ex-04-Multivariate-Analysis/assets/131427787/f58f4246-07d8-409d-a5b4-08dc00aadaa8)

Heatmap

![mul 13](https://github.com/viswapriyaG/Ex-04-Multivariate-Analysis/assets/131427787/1c79eb74-50a6-46bd-99f9-eb04e947a4e6)


# RESULT:

Thus we have read the given data and performed the multivariate analysis with different types of plots.
