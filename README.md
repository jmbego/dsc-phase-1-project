## title

###       EXPLORATORY DATA ANALYSIS TO GENERATE INSIGHTS FOR MICROSOFT COMPANY  


###    1.  BUSINESS PROBLEM

Microsoft sees all the big companies creating original video content and they want to get in on the fun. They have decided to create a new movie studio, but they don’t know anything about creating movies. You are charged with exploring what types of films are currently doing the best at the box office. You must then translate those findings into actionable insights that the head of Microsoft's new movie studio can use to help decide what type of films to create.

####  2. DATA UNDERSTANDING 

The following task is quite intuisive and recquiers a well analysed data of a rather different movie store. to basically determine how they perfom in the same field, how they interact- best genres, how they rate , the prices they use and how they sale within particular time frames. The analysis there for entails a well worked through csv files, sql files with relevant data to help depict the companies next step.

This next cell is importing of the recquired python libraries that aids in objective completion 

#### Importing libraries 
 
```python
  import pandas as pd
  import numpy as np
  import matplotlib as plt
  import matplotlib.pyplot as plt

```
#### 4. Dowloading datasets

##### The cell below is coded to retrieve the data used from the storage location. 

##### Pandas makes creates a DataFrame that is explorable  rather than comma sep' values and here r converts a normal string to a raw string:

```python

df1 = pd.read_csv(r"C:\Users\John Mbego\Documents\DS_PROJECTS\dsc-phase-1-project-v2-4\zippedData\tmdb.movies.csv.gz")
df2 = pd.read_csv(r"C:\Users\John Mbego\Documents\DS_PROJECTS\dsc-phase-1-project-v2-4\zippedData\bom.movie_gross.csv.gz")
df3 = pd.read_csv(r"C:\Users\John Mbego\Documents\DS_PROJECTS\dsc-phase-1-project-v2-4\zippedData\tn.movie_budgets.csv.gz")
df4 = pd.read_csv(r"C:\Users\John Mbego\Documents\DS_PROJECTS\dsc-phase-1-project-v2-4\zippedData\rt.movie_info.tsv.gz",sep='\t')

```
###   4. Data preparation

##### droping empty valued cells

##### The empty cells in some columns are replaced or dropped , duplicates dropped .'NaN' a csv commoner and always brings errors with the analysis phase , during prepation they are removed or filled depending on the data type  or statistical analysis 

check index. ipynb

###  Cleaning

#### a dataset can have as many data as it can hold. during analysis some are however irrelevant and needs to be cleaned to suit the projects specific objectives. 


```python
popularity_df1 = df1.drop(['Unnamed: 0','original_title','release_date',],axis=1)

```
#### gross_df2 is introduced to be the new data frame from the df2. It is a cleaned version dataframe with certain columns of df2 set to numeric 


```python
df2["domestic_gross"] = pd.to_numeric(df2["domestic_gross"],errors='coerce')
df2["foreign_gross"] = pd.to_numeric(df2["foreign_gross"],errors='coerce')
gross_df2 = df2.drop(["studio","year"], axis=1)

```
#### the below cell has a new column introduced , it is named total_gross and its the total of both domestic_gross and foreign_gross a movie produced 

```python
gross_df2['total_gross']=gross_df2['domestic_gross']+gross_df2['foreign_gross']

```

#### the production_budget as seen in the df3 data has dollar sign and is comma seperated , for the numeric analysis they are blockers an the beloow code cleans them out

```python

df3['production_budget'] = df3['production_budget'].str.replace('$','')
df3['production_budget'] = df3['production_budget'].str.replace(',','')


budgets_df3 = df3.drop(['release_date','domestic_gross','worldwide_gross'],axis=1)

genres_df4 = df4.drop(['director','dvd_date','studio','rating','writer','currency','theater_date'],axis=1)

```

### 5. ANALYSIS

####   CONCATENATING 

The above cells under dowloading of the data have three imported csv files that each contain information on columns that are quite necessary for our exploration , ie df1 (data frame 1 ) has movies together with popularity but misses the gross. df4 data frame also contains the genres needed for  at analysis ,Concatenating the data therefore ensures all the deriverables are merge for better conclusions.
Instead of the merge and join function the best way rather, this analysis uses concat built in function. append is way soon getting outdated but it can on be used. 

movie_concat is introduced to hold the gross_df2 and budgets_df3


check imdex.ipynb

### VISUALIZATION

Shows a bar plot of the most profitable movies that have been made , this helps to know the type of movies that can be invested in based on the returns they produce . its all about profits in the blueprints.
##### A plot of top ten movies against profits



### CONCLUSION


the data sets have been analysed and the company can use it to determine the best type of movies that are rated and profitable enough, some are most rated but do not quite fall in the top profitable .