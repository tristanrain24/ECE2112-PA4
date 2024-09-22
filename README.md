# Data Wrangling and Visualization
## Welcome to my repository!
### In this programming assignment, we will leverage Python's powerful libraries, Pandas and Matplotlib, to clean, organize, and visualize data effectively. Through this process, we will enhance our data analysis skills by transforming raw data into meaningful insights and visual representations.

## Overview:

Data wrangling is converting and translating raw data into a more useful format. 
On the other side, visualization converts data into visual surroundings that are easier to comprehend and study.

This assignment covers:

**Data Cleaning and Transformation** - Handling, reshaping, and mergin data to create a more desireable output.
**Data Visualization** - Creating graphs and plots to reveal pattern and trends using Matplotlib.


## Getting Started:
To utilize Pandas and Matplotlib, we can write the following code:
```
import pandas as np
```

```
import matplotlib.pyplot as plt
```
## Coding and Explanation

<p align="center"> ECE BOARD EXAM PROBLEM
</p>  

Before we start with this problem, we'll import the pandas library using the syntax ```import pandas as np```

In this porblem we are required to import a data frame that's in a form of an excel file. We use the syntax ```pd.read_excel()``` in order for us to read the data frame imported alongside our Programming Assignment file. 

Part A:  Instru = [“Name”, “GEAS”, “Electronics >70”]; where track is constant as
Instrumentation and hometown Luzon.

In this problem, we'll utilize the ```.loc()``` syntax, which is a label based syntax that will help us locate the Track and Hometown that's required in this problem.

Our code should look as the following:
```
instru = board.loc[(board['Track'] == 'Instrumentation') & (board['Hometown'] == 'Luzon') & 
        (board['Electronics'] > 70), ['Name', 'GEAS', 'Electronics']].reset_index(drop=1)
```
```board.loc[(board['Track'] == 'Instrumentation')``` locates "Instrumentation" within the column "Track"

The ```&``` adds the condition ```(board['Hometown'] == 'Luzon')```  which locates the rows which has "Luzon"

Adding another condition, ```(board['Electronics'] > 70)``` That locates the marks greater than 70 within the column "Electronics"


Running this code, displays the output as:


| Name | GEAS | Electronics |
|------|------|-------------|
| S1   | 75   | 89          |
| S8   | 64   | 81          |
| S30  | 57   | 81          |



Part B is a similar problem to part A, but this instance requires us to take the average mark of every taker.

In order to take the average mark across all subjects, we use the syntax ```df.mean()```

The complete version of this code is:

```
board['Average'] = board[['Math','Electronics', 'GEAS', 'Communication']].mean(axis=1)
```

```board['Average']``` creates another column for us to indicate the average mark of each taker.

```.mean(axis=1)``` "axis = 1" is a parameter that specifies that the mean function should be applied horizontally.

```
mindy = board.loc[(board['Gender'] == 'Female') & (board['Hometown'] == 'Mindanao') & 
        (board['Average'] >= 55), ['Name', 'Track', 'Electronics', 'Average']].reset_index(drop=1)
```
The rest of the code is similar to problem A. But with the addition of syntax ```.reset_index(drop=1)```. This syntax resets the index of the data frame and "drop=1" ensures that the original index is not added as a new column.

Our completed code should look the following:

```
board['Average'] = board[['Math','Electronics', 'GEAS', 'Communication']].mean(axis=1)

mindy = board.loc[(board['Gender'] == 'Female') & (board['Hometown'] == 'Mindanao') & 
        (board['Average'] >= 55), ['Name', 'Track', 'Electronics', 'Average']].reset_index(drop=1)
```

The output:

| Name | Track            | Electronics | Average |
|------|------------------|-------------|---------|
| S2   | Communication    | 75          | 67.25   |
| S3   | Instrumentation   | 74          | 72.75   |
| S15  | Microelectronics  | 41          | 59.00   |
| S17  | Microelectronics  | 79          | 70.50   |
| S20  | Communication     | 60          | 66.50   |


Problem 2:

Create a visualization that shows how the different features contributes to average grade. Does
chosen track in college, gender, or hometown contributes to a higher average score?

In terms of Track, Microelectronics tend to get a higher mark, followed by communications and lastly by Instrumentation. Basing on "Gender", females tend to have a higher mark in comparison to the Male takers.

Lastly, in terms of Hometown. Takers from Luzon received higher marks in comparison to Visayas, with the least being Mindanao. 
Version History:

1.1 Updated README file
