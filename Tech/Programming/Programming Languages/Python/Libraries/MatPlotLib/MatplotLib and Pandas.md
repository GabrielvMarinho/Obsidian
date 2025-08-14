Here's a [[Python]] [[Data Science]] guide using [[Pandas]] and [[MatPlotLib]].


## Imports and getting the dataset

```
#Importing thing
import pandas as pd
import matplotlib.pyplot as plt

from google.colab import drive
import numpy as np

#connecting with the drive
drive.mount("/content/drive")

#creating the table based on the path file in the drive
tabela = pd.read_csv("/content/drive/MyDrive/Colab Notebooks/Arquivos/sales_data_sample.csv", encoding="latin1")

#simple way to print the dataset
display(tabela)

#creates the DataFrame
#will be important later
df = pd.DataFrame(tabela)

```


## Displaying charts

We can display graphs simply by giving two values:

```
plt.NAME_OF_THE_GRAPH(df['MONTH_ID'], df['QUANTITYORDERED'])
```

This is for when we want a [[Pandas]] Series to be displayed:

```
plt.NAME_OF_THE_GRAPH(year_counts.index, year_counts.values)
```

show every 1 to 1:
```
#creates a rotation of 45 degrees to not overwrite anything
plt.xticks(year_counts.index+1)
```
+1 because index starts at 0

rotate the label:
```
plt.xticks(rotation=45)
```
## Counting Things

```
year_counts = df["Released_Year"].value_counts().sort_index()
```

## Conditions
### Conditions Simple:

To create simples conditions: 

```
#changes all the values of released_year to a numeric value sinc its a string
df["Released_Year"] = pd.to_numeric(df["Released_Year"], errors="coerce")

#creates a new dataFrame based on a condition
filtered_df = df[df["Released_Year"] > 2000]

year_counts = filtered_df["Released_Year"].value_counts().sort_index()

```

### Conditions based on other columns:

Let's create more complicated conditions, such as the top 10 best rated directors:

```
top_directors = df.groupby("Director")["IMDB_Rating"].mean().sort_values(ascending=False).head(10)
```

.mean() - calculates the mean of ("IMDB_Rating") for each ("Director")
.sort_values() - sort the values in Ascedant by default
asceding - False - show that needs to sort the values in Descendant
.head() - gets the first 10 rows

This graph created is weird because it show the graph from 0 to 10 and the interval of the means is very small, showing no real details.

Let's change the y axis interval to 1 for example

```
plt.ylim(7, 10)
```

.ylim - sets the range of the y axis

## Manipulating datasets

### Changing data

If for example we need to round every number in a DataFrama, we can:

```
df_rounded = df.round(2)
```

### Adding columns

We can add rows very easily based on existing columns

```

df['date'] = pd.to_datetime(df['date'])

df["year"] = df['date'].dt.year

```

this will create a new row called "year"


## Types of graphs

bar - Bar Chart
scatter - Dispersion Chart
plot - Line Chart