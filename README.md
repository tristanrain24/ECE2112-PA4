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

```
      Name    GEAS	Electronics
0	S1	75	89
1	S8	64	81
2	S30	57	81
```


Version History:

1.1 Updated README file
