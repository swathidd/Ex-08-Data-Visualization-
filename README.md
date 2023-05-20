# Ex-07-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

# Explanation
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


# CODE
```
import pandas as pd

df=pd.read_csv('/content/Superstore.csv',encoding='windows-1252')

df.head()

df.isnull().sum()

import seaborn as sns

sns.boxplot(data=df)

import seaborn as sns

import matplotlib.pyplot as plt

sns.barplot(y=df['Sales'], x=df['Segment'])

plt.title("Highest Sales of the segment")

plt.show()

sns.barplot(y=df['Profit'], x=df['City'])

plt.title("Highest Profit based on the city")

plt.show()

sns.barplot(x=df['Ship Mode'],y=df['Profit'])

plt.title("Profitable ship")

plt.show()

sns.barplot(x=df['Region'],y=df['Sales'])

plt.title("Sales of product based on region")

plt.show()

sns.lineplot(x=df['Sales'], y=df['Profit'])

plt.title("Relation between Sales and Profit")

plt.show()

grouped_data = df.groupby('Segment')[['Sales', 'Profit']].mean()

fig, ax = plt.subplots()

ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')

ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')

ax.set_xlabel('Segment')

ax.set_ylabel('Value')

ax.legend()

plt.title("Sales and Profit based on Segment")

plt.show()

grouped_data = df.groupby('City')[['Sales', 'Profit']].mean()

fig, ax = plt.subplots()

ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')

ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')

ax.set_xlabel('City')

ax.set_ylabel('Value')

ax.legend()

plt.title("Sales and Profit based on City")

plt.show()

grouped_data = df.groupby('State')[['Sales', 'Profit']].mean()

fig, ax = plt.subplots()

ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')

ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')

ax.set_xlabel('State')

ax.set_ylabel('Value')

ax.legend()

plt.title("Sales and Profit based on States")

plt.show()

grouped_data = df.groupby(['Segment', 'Ship Mode'])[['Sales', 'Profit']].mean()

pivot_data = grouped_data.reset_index().pivot(index='Segment', columns='Ship Mode', values=['Sales', 'Profit'])

fig, ax = plt.subplots()

pivot_data.plot(kind='bar', ax=ax)

ax.set_xlabel('Segment')

ax.set_ylabel('Value')

plt.legend(title='Ship Mode')

plt.legend(loc="best")

plt.title("Sales and Profit based on Segment and Ship mode")

plt.show()

grouped_data = df.groupby(['Segment', 'Ship Mode','Region'])[['Sales', 'Profit']].mean()

pivot_data = grouped_data.reset_index().pivot(index=['Segment', 'Ship Mode'], columns='Region', values=['Sales', 'Profit'])

sns.set_style("whitegrid")

sns.set_palette("Set1")

pivot_data.plot(kind='bar', stacked=True, figsize=(8, 5))

plt.legend(title='Region')

plt.legend(loc='best')

plt.title("Sales and Profit based on Segment,Ship mode and Region")

plt.show()
```

# OUPUT
![image](https://github.com/swathidd/Ex-08-Data-Visualization-/assets/121300272/fd6619d4-082e-4853-b35d-191afb8102a3)

![image](https://github.com/swathidd/Ex-08-Data-Visualization-/assets/121300272/f2c0468a-176b-4e9e-953c-4f1e9cb83a37)

![image](https://github.com/swathidd/Ex-08-Data-Visualization-/assets/121300272/0ddd4514-ed1b-451d-aa7b-64f5d78838c5)

![image](https://github.com/swathidd/Ex-08-Data-Visualization-/assets/121300272/0061cfaf-1d13-4998-be2b-6a3a2a25f401)

![image](https://github.com/swathidd/Ex-08-Data-Visualization-/assets/121300272/afea128f-5c59-42b1-beeb-a7aaf3037282)

![image](https://github.com/swathidd/Ex-08-Data-Visualization-/assets/121300272/9e49ac82-b263-461c-bf8e-56925bf0a874)

![image](https://github.com/swathidd/Ex-08-Data-Visualization-/assets/121300272/2a63b6ff-fb8b-47f0-9998-a9256cba6b82)

![image](https://github.com/swathidd/Ex-08-Data-Visualization-/assets/121300272/37cc01ff-fefe-4a57-af4e-b85c5bcfd303)

![image](https://github.com/swathidd/Ex-08-Data-Visualization-/assets/121300272/459ddb8b-5e25-4e0b-81e7-90bd2f9b74d3)

![image](https://github.com/swathidd/Ex-08-Data-Visualization-/assets/121300272/199aa355-d971-49ed-a423-6e4888535ecf)

![image](https://github.com/swathidd/Ex-08-Data-Visualization-/assets/121300272/ddd45ddb-2852-4860-a9dc-a4b37ae154c0)

![image](https://github.com/swathidd/Ex-08-Data-Visualization-/assets/121300272/0d364783-27d6-4398-ab05-5c6fe09f2d66)

RESULT

Thus Data Visualization was performed on the given dataset and the results were displayed successfully.




