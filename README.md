# Ex-09-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

## Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


## CODE and OUTPUT
```
DEVELOPED BY:KAVINESH M
REGISTER NO:212222230064

```
```
import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
```
```
df=sns.load_dataset('tips')
print(df)
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex-09/assets/118904526/e4d2f4c3-89d9-432e-8bfb-473937f27777)

```
df.isnull().sum()
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex-09/assets/118904526/2269fca5-da04-4ba0-b863-1e9792703a6d)

```
plt.figure(figsize=(5,5))
plt.title("Data with outliers")
df.boxplot()
plt.show()
```

![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex-09/assets/118904526/06f891a0-e1d7-4b02-8580-5b9e6f1b9ab7)

```
plt.figure(figsize=(5,5))
cols=['size','tip','total_bill']
Q1=df[cols].quantile(0.25)
Q3=df[cols].quantile(0.75)
iqr=Q3-Q1
df=df[~(((df[cols]<Q1-1.5*iqr)|(df[cols]>Q3+1.5*iqr))).any(axis=1)]
plt.title("Dataset after removing outliers")
df.boxplot()
plt.show()
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex-09/assets/118904526/96f0eddf-02c8-46fc-b0cb-7b7002a1ca6f)

```
sns.barplot(x=df['day'],y=df['total_bill'],hue=df['day'])
plt.legend(loc='center')
plt.title("Highest Total Amount by the day of the week")
plt.show()
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex-09/assets/118904526/26de21b5-065d-41a3-87b2-77a7707131ba)

```
sns.boxplot(x=df['smoker'],y=df['tip'],hue=df['smoker'])
plt.title("Average tip amount given by smokers and non-smokers")
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex-09/assets/118904526/5232d74a-0190-41ea-9d29-15e64616bcc7)
```
sns.boxplot(x='day',y='total_bill',hue='smoker',data=df,linewidth=2,width=0.6,boxprops={'facecolor':'lightblue','edgecolor':'darkblue'},whiskerprops={'color':'black','linestyle':"--","linewidth":1.5},capprops={'color':'black','linestyle':"--","linewidth":1.5})
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex-09/assets/118904526/f09d0f86-f064-4977-a49d-2dc49608621c)

```
df["tip_percent"]=df["tip"]/df["total_bill"]
sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex-09/assets/118904526/7d3efe53-692f-4c6a-be37-93a445759f0e)

```
sns.boxplot(x=df['sex'],y=df['tip'],hue=df['sex'])
plt.title("Tips based on gender")
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex-09/assets/118904526/8baec03c-7944-495b-8a92-b3d67bd16bd2)

```
sns.scatterplot(x=df['day'],y=df['total_bill'],hue=df['day'])
plt.legend(loc='best')
plt.title('Total bill amount by day of the week')
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex-09/assets/118904526/55741cc8-49a9-42a7-9910-bd5fc9b8978e)

```
sns.histplot(data=df,x="total_bill",hue="time",element="step",stat="density")
plt.title("Distribution of Total Bill amounts by time of the day")
plt.show()
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex-09/assets/118904526/0b362a50-379a-49c1-a1e4-bea4eae64d6c)

```
sns.barplot(x=df['size'],y=df['total_bill'],hue=df['size'])
plt.title("Average Total Bill amount by dining party size")
plt.show()
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex-09/assets/118904526/7eab024c-db9e-4f3e-b71d-03427801d9af)

```
sns.boxplot(x="day",y="tip",data=df)
plt.title("Tip amount by day of the week")
plt.show()
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex-09/assets/118904526/7e1a3b90-41a0-4ffb-926e-d3164a81d76d)

```
sns.violinplot(x="time",y="tip",data=df)
plt.title("Tip amount by time of day")
plt.show()
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex-09/assets/118904526/3f004468-6e15-4ac9-b999-72988138997e)

```
sns.scatterplot(x="total_bill",y="tip",data=df)
plt.title("Correlation between tip amount and total bill amount")
plt.show()
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex-09/assets/118904526/5e41c8a8-296a-4a29-a6be-dbf944efd0e8)

## RESULT
Thus,data visulaization on a complex dataset is successfully executed.
