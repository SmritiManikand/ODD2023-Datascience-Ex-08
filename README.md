# Ex-08-Data-Visualization
# AIM
To Perform Data Visualization on a complex dataset and save the data to a file.

# EXPLANATION
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
## STEP 1
Read the given Data

## STEP 2
Clean the Data Set using Data Cleaning Process

## STEP 3
Apply Feature generation and selection techniques to all the features of the data set

## STEP 4
Apply data visualization techniques to identify the patterns of the data.

# CODE

```
import pandas as pd
df=pd.read_csv("/content/Superstore.csv",encoding='unicode_escape')
df.head()
import seaborn as sns
from matplotlib import pyplot as plt
plt.figure(figsize=(9,6))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
sns.lineplot(x="Category",y="Sales",data=df,marker='o')
sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)
sns.violinplot(x="Profit",data=df)
sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.pointplot(x=df["Quantity"],y=df["Discount"])
sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df)
sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')
sns.kdeplot(x="Profit", data = df,hue='Category')

plt.plot(df['Category'], df['Sales'])
plt.show()
df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)
df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()
plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()
plt.bar(df.index,df['Category'])
plt.show()
plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()
plt.boxplot(x="Sales",data=df)
plt.show()
```

# OUTPUT

## DATA VISUALIZATION USING SEABORN: 

### LINE PLOT:
<img width="265" alt="s1" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/1e310b64-6246-4b5e-8af9-b0a1a7bb1f3d">

<img width="259" alt="s2" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/115669f2-7eae-4c5e-b3eb-b57350cb444e">

<img width="256" alt="s3" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/06adcef5-1957-40b3-b4c9-ac5fc1197e85">

### SCATTER PLOT:
<img width="260" alt="s4" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/7becd8ca-0b86-41a4-a980-a6dbbfc8e7ed">

<img width="240" alt="s5" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/acd8bcd8-5f03-4465-b11b-334bfad65db1">

<img width="269" alt="s6" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/f90cfdae-bace-40af-a932-baba1529f7e7">

### BOX PLOT:
<img width="262" alt="s7" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/3f9c8e55-6821-463a-9606-e76aa3605db7">

<img width="268" alt="s8" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/20ba81f4-3535-4a77-9364-cc86fa2adf92">

### VIOLIN PLOT:
<img width="265" alt="s9" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/43464e1f-e0ff-47c2-9178-108b865a09bb">

### BAR PLOT:
<img width="290" alt="s10" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/baceea1e-3cfc-4ecd-8cc2-5407abdea431">

<img width="255" alt="s11" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/ce4216e1-2448-4bb4-8000-16fba472b25a">

<img width="257" alt="s12" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/c04902aa-27b1-44bd-b387-90018c3b9c21">

### POINT PLOT:
<img width="251" alt="s13" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/04870899-ecbd-47e5-9aaf-ba14212fceed">

### COUNT PLOT:
<img width="254" alt="s14" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/6325063b-2f45-4f0e-8f7c-79dacc72f4d9">

<img width="226" alt="s15" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/bc8a31f2-a4c5-448e-bc3e-9f54616772aa">

### HISTOGRAM:
<img width="246" alt="s16" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/0ec60f29-f19b-4ca1-85d2-ed1082103144">

### KDE PLOT:
<img width="266" alt="s17" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/196ec053-c894-48fc-8ecc-444a916cee31">

## DATA VISUALIZATION USING MATPLOTLIB:

### PLOT:
<img width="262" alt="s18" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/a2645296-391e-4cdd-81e2-253a63bf6e81">

### HEATMAP:
<img width="268" alt="s19" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/19f56eeb-f047-403a-a3fd-014352d1ce2b">

### PIECHART:
<img width="268" alt="s20" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/6a831c72-bf5b-4869-b683-576e98ac84fb">

<img width="228" alt="s21" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/ac81ea31-bf48-4375-a6d3-18e1eeea1ad8">

### HISTOGRAM:
<img width="268" alt="s22" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/910156bb-5864-4b83-ac0d-d55ea3bb798b">

### BAR GRAPH:
<img width="278" alt="s23" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/369bc111-32eb-4390-8b91-0da55193b9fe">

### SCATTER PLOT:
<img width="236" alt="s24" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/15da2ec6-f819-4b6d-b171-b3022faf0ecc">

### BOX PLOT:
<img width="251" alt="s25" src="https://github.com/SmritiManikand/ODD2023-Datascience-Ex-08/assets/113674204/a6fbac61-61a2-4ceb-8fd4-aa5894b121a8">

# RESULT
Hence, Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
