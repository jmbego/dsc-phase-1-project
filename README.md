###       EXPLORATORY DATA ANALYSIS TO GENERATE INSIGHTS FOR MICROSOFT COMPANY  



#### BUSINESS PROBLEM

#####       Microsoft sees all the big companies creating original video content and they want to get in on the fun. They have decided to create a new  movie studio, but they don’t know anything about creating movies. You are charged with exploring what types of films are currently doing the best at the box office. 
#### You must then therefore translate those findings into actionable insights that the head of Microsoft's new movie studio can use to help decide what type of films to create.
####  1. DATA UNDERSTANDING 

##### The following task is quite intuitive and requires a well analyzed data of a rather different movie store. to basically determine how they perform in the same field, how they interact- best genres, how they rate , the prices they use and how they sale within particular time frames. The analysis there for entails a well worked through csv files, sql files with relevant data to help depict the companies next step.

##### This next cell is importing of the recquired python libraries that aids in objective completion 

### Importing libraries 
 
#### Python libraries include pandas,numpy,matplotlib
##### Python’s standard library is very extensive, offering a wide range of facilities as indicated by the long table of contents listed below. The library contains built-in modules (written in C) that provide access to system functionality such as file I/O that would otherwise be inaccessible to Python programmers, as well as modules written in Python that provide standardized solutions for many problems that occur in everyday programming. Some of these modules are explicitly designed to encourage and enhance the portability of Python programs by abstracting away platform-specifics into platform-neutral APIs. Ref ,https://docs.python.org/3/library/index.html

```python
import pandas as pd
import numpy as np
import matplotlib as plt
import matplotlib.pyplot as plt

```
#### 1.0 Dowloading datasets


##### The following project uses data from various files of different types , to use the data we have to load them to our working platform as shown below . The project picks on 4 csv files , and uses panda library to load them to a data frame Concatenating is used later on to merge specifics 


##### The cell below is coded to retrieve the data used from the storage location. 

##### Pandas makes creates a DataFrame that is explorable  rather than comma sep' values and here r converts a normal string to a raw string:

```python

df1 = pd.read_csv(r"C:\Users\John Mbego\Documents\DS_PROJECTS\dsc-phase-1-project-v2-4\zippedData\tmdb.movies.csv.gz")
df2 = pd.read_csv(r"C:\Users\John Mbego\Documents\DS_PROJECTS\dsc-phase-1-project-v2-4\zippedData\bom.movie_gross.csv.gz")
df3 = pd.read_csv(r"C:\Users\John Mbego\Documents\DS_PROJECTS\dsc-phase-1-project-v2-4\zippedData\tn.movie_budgets.csv.gz")
df4 = pd.read_csv(r"C:\Users\John Mbego\Documents\DS_PROJECTS\dsc-phase-1-project-v2-4\zippedData\rt.movie_info.tsv.gz",sep='\t')
```
## Data preparation
##### 1. droping empty valued cells

##### The empty cells in some columns are replaced or dropped , duplicates dropped .'NaN' a csv commoner and always brings errors with the analysis phase , during prepation they are removed or filled depending on the data type  or statistical analysis 
  
check index file

### 2. Cleaning

#### a dataset can have as many data as it can hold. during analysis some are however irrelevant and needs to be cleaned to suit the projects specific objectives. 

### ANALYSIS

#### Data analysis here involves using various libraries and tools to explore, manipulate, and extract insights from datasets. Python provides several powerful libraries for data analysis, including pandas, NumPy, Matplotlib, Seaborn, and SciPy. Here we use pandas to analyse through the dataframe

#### 1.  CONCATENATING 

##### The above cells under dowloading of the data have three imported csv files that each contain information on columns that are quite necessary for our exploration , ie df1 (data frame 1 ) has movies together with popularity but misses the gross. df4 data frame also contains the genres needed for  at analysis ,Concatenating the data therefore ensures all the deriverables are merge for better conclusions.
##### Instead of the merge and join function the best way rather, this analysis uses concat built in function. append is way soon getting outdated but it can on be used. 


### VISUALIZATION

#### Visualization in Python refers to the process of creating graphical representations of data to gain insights, identify patterns, and communicate findings effectively

#### The cell here in the index file shows a bar plot of the most profitable movies that have been made , this helps to know the type of movies that can be invested in based on the returns they produce . its all about profits in the blueprints.
##### A plot of top ten movies against profits


### CONCLUSION
#### the data sets downloaded have been analyzed and the company therefore can use it to determine the best type of movies that are rated and profitable enough, some are most rated however do not quite fall in the top profitable movies. 
 .