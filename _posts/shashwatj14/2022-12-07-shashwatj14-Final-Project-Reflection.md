---
layout: post
author: shashwatj14
title: Shashwat's Final Project and Final Reflection
---

# Exploratory Data Analysis on a Cricket Player's Dataset 

Trinket: <iframe src="https://trinket.io/embed/python3/c03f1b308e" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

As a student in the 'Intro to Programming' course at my grad school, I was excited to apply the skills I had learned in class to a real-world dataset. I chose to analyze the performance of Indian cricket star Virat Kohli, using the powerful libraries pandas and matplotlib in Python. In this reflection, I will describe my approach to the project, discuss any challenges I faced, and provide some insight into the insights I was able to glean from the data.

### A bit about Cricket if you're new to it...
But before diving into the analysis, it's important to provide some context for those who may not be familiar with the sport of cricket. Cricket is a bat-and-ball game played between two teams of eleven players each. The teams take turns to bat and bowl, with the team batting trying to score as many runs as possible and the team bowling trying to restrict the opposition from scoring runs and dismiss them. The game is played on a circular field called a cricket ground, which is divided into a series of areas known as pitches. The central area of the cricket ground is called the pitch, which is where the two teams play. The team that is batting tries to score runs by hitting the ball with their bat and running between the wickets, which are a set of three stumps and two bails. The team that is bowling tries to prevent the opposition from scoring runs and dismiss them by getting the ball to hit the stumps and dislodge the bails. There are various ways in which a batsman can be dismissed, such as being bowled, caught, stumped, or run out. The game is divided into several periods called innings, with each team taking a turn to bat and bowl. The team that scores the most runs in the allotted number of innings is declared the winner.

### Why did I choose this project idea?
I've been following Viral Kohli since his first cricket match in 2011, and he's a true game changer. For this project, I wanted to do something that has always piqued my interest because I believe that analyzing a dataset from a field of interest makes the entire task much more interesting. The goal of this project is to evaluate his performance. I got this dataset from Kaggle in the form of a csv file, which contains statistics demonstrating his performance on the pitch. My dataset includes the following features:

* Runs: Runs in the match
* BF: Balls faced in the match
* 4s: number of 4s in a match
* 6s: number of 6s in a match
* SR: Strike Rate in the match
* Pos: Batting Position in the match
* Dismissal: How Virat Kohli got out in the match
* Inns: 1st and 2nd innings
* Opposition: Who was the opponent of India
* Ground: Venue of the match
* Start Date: Date of the match

I wanted to delve deep into his performance and uncover some intriguing insights, such as which opponents he prefers to play against, his preferred batting positions, how he gets out, and how frequently he remains not out and several other things. 

I started my code by importing all of the necessary libraries, such as pandas, matplotlib, and pandas, as well as custom modules that I created while trying to answer these questions. I set the index_col parameter to zero while writing the csv file into a data frame to ensure that pandas does not create an unnamed index column in my data frame (which it usually does). In addition, I used the pandas head method to display the top five rows in my dataset and the pandas shape method to display the total number of rows and columns in my dataset.

```
import pandas as pd
import numpy as np
from plots import *
from utility import *
import matplotlib.pyplot as plt
```

I also created and displayed a data dictionary for the user so as to give them a clear understanding of all features in my dataset:
```
data_dict = {
    "Runs": "Runs in the match",
    "BF": "Balls faced in the match",
    "4s": "Number of 4s in a match",
    "6s": "Number of 6s in a match",
    "SR": "Strike Rate in the match",
    "Pos": "Batting Position in the match",
    "Dismissal": "How Virat Kohli got out in the match",
    "Inns": "1st and 2nd innings",
    "Opposition": "Who was the opponent of India",
    "Ground": "Venue of the match",
    "Start Date": "Date of the match"
}
```

Then, I wanted to make my code more interactive and allow the user to browse the dataset. To begin, I ask the user if they want to see any specific rows and columns. If they say yes, my program will ask them to specify which rows and columns they want and will display the desired data accordingly. Also, before they do this, I let them look at the data dictionary and see the corresponding indices of all columns so that they can properly enter which columns they want to see. If they say no, I'll display the entire dataset and proceed with my data analysis.
```
# Check the user's response
if display_specific == "y":
  get_data_subset(data)
  
else:
  # If the user doesn't want to display specific rows and columns, display the entire DataFrame
  print(data)
```

Then, using matplotlib's subplots method, I created a figure with space for 9 plots. I also used some additional matplotlib methods to ensure that my overall figure is clean and that my plots do not overlap. For example, I used the set_size_inches method to set the sizes of my figures to 13x16 inches, and the subplots_adjust method to add a horizontal space of 0.6 between the figures.
```
fig, ax = plt.subplots(ncols = 1, nrows = 9)
fig.set_size_inches(13, 16)
# Use the fig.subplots_adjust() method to add some spacing between the subplots
fig.subplots_adjust(hspace = 0.6)
```

I'd like to go over a few concepts from this course and explain how I applied those concepts to this project:

* Interactive interface - Gave the user a chance to select which rows and column they would like to see in the dataset 
* External data files - I dealt with a csv file; loaded it into a data frame and conducted data analysis on the same 
* Dictionaries - I used dictionary to create a dataset data dictionary, and I also used it in a map function to map batting order values in my dataset to their corresponding string values.
* Lists - I used it several times in my code. For example, I used it in a for loop to append values to a list, which I then used to return a value at the end of the function.
* Custom Functions - For each type of visualization, I created a custom function, so that anyone who wants to create a plot can do so by simply passing the appropriate parameters to the function.
* Map functions - I have used map functions at various instances in my code. For example, I used it during type conversion from string to int. 
* Custom Modules - I created two custom modules.
** utility.py - A collection of custom functions that provide some extended functionality to the main python file.
** plots.py - Contains custom functions for various plots that have been used in main.py to perform data analysis.
* For loops - I used it to iterate through the entire dataframe to check for null values.
* Conditional statements (If - else) - I used if-else statements in a custom function to check for null values in my dataset.
* F strings - I really like the functionality provided by f strings within print statements. They make it incredibly simple for us to embed expressions inside string literals with minimal syntax. I used it in the same custom function I mentioned in the previous use case.
* Additional string functionalities (\n, comments, etc.) - I used new line characters and comments extensively throughout my code. They were extremely helpful in making my code more readable and understandable.

Below, I will detail down the visualizations that I created, how I did what I did and the corresponding insights that I got from them:

The dataset contained information from Virat Kohli's matches between August 18, 2008, and January 22, 2017. So I started by looking at his total runs scored and calculating an average over the same time period. In Python, I used the sum() and mean() functions to accomplish this. This led to my first realization that he had a good total and a very good average of nearly 47 runs, indicating how good and consistent Kohli is as a player.

Then I looked at the trend of runs scored by him between August and January and discovered that he scored a century in many of the innings he played. This was accomplished by writing a custom function in the plots module that used matplotlib's plot() function to generate a scatter plot.
Here's a snippet of the scatter plot custom function that I created: 
```
def scatter_plot(x, y, title, axes):
  axes.scatter(x = x, y = y)
  axes.set_title(title)
```

Then I wanted to look into the number of matches he played at various batting positions and the number of runs he scored at those positions. This was accomplished by making two plots, one for each problem. To analyze the number of matches he played at various batting positions, I created a pie chart and discovered that he batted at number 3 during the majority of his matches (nearly 70%). However, he scored a lot of runs at the number 2 position, indicating how good he can be at that position. To conduct my analysis, I wrote a function to draw a pie chart (using matplotlib's pie method) and called it in the main file. I also had to use the groupby() method in pandas to group the whole data according to the position feature and aggregated it by sum.
Here's a snippet of the pie chart custom function that I created: 
```
def pie_chart(values, labels, title, axes):

  # Use the axes.pie() method to create a pie chart
  axes.pie(values)
  axes.legend(labels, title = 'values', loc = "best")
  axes.axis('equal') # Equal aspect ratio ensures that pie is drawn as a circle.
  axes.set_in_layout('tight_layout')
  # Add a title to the pie chart
  axes.set_title(title)
```

Then, using a bar chart custom function that I created in the plots module, I looked at the number of centuries scored by Virat Kohli while batting in the first and second innings. With the appropriate parameters, this function used matplotlib's bar method. I discovered that the majority of the centuries were scored while batting in the second innings using this plot. This led me to believe that Virat Kohli enjoys chasing scores.
Here's a snippet of the bar plot custom function that I created: 
```
def bar_plot(x, y, color, title, axes):
  axes.bar(x, y, color = color)
  axes.set_title(title)
 ```
 I also added a custom function that would go on to generate value labels at the top of the bars 
 
 ```
#The function below helps a user in adding text labels to the top of the bars in bar charts 
def display_text(labels, values, ax):
  for xi, yi in zip(labels, values):
      ax.text(xi, yi, yi, ha = "center", va = "bottom")
```

Now I wanted to look into his dismissals to see how he gets out most of the time. I accomplished this using a pie chart and the same custom function that I used in one of the previous sections. This analysis led me to an insight that most of the time, Virat Kohli gets out by getting caught by the fielder or the keeper.


Now I wanted to look at which teams Virat Kohli scored the most runs against. Using a bar chart, I discovered that Virat Kohli prefers to bat against Sri Lanka, Bangladesh, New Zealand, and South Africa. I also looked at how many centuries he had against different teams and discovered that he had the most against New Zealand.


Finally, I'll discuss scatter plots with trend lines, which were the final plots I created. I wanted to investigate the relationship between his runs scored and fours and sixes hit. I wrote a custom function to plot a scatter plot and used it for both of the above-mentioned use cases. I discovered that his fours have a linear relationship with his overall runs scored, but his sixes do not have a strong linear relationship, indicating that he prefers to score most of his runs through fours rather than sixes.
Here's a snippet of the custom function that would generate a scatter plot with a linear trend line: 
```
def scatter_plot_with_trend(x, y, title, axes):
  axes.scatter(x = x, y = y)
  m, b = np.polyfit(x, y, 1)
  axes.plot(x, m*x + b, '-') 
  axes.set_title(title)
```

Now, as I was conducting all of this analysis, I was essentially adding all of these plots as subplots to my main figure, and now that I was finished, it was time to plot the entire figure incorporating all plots. As a result, I finally used matplotlib's show method to display my main figure, which included all of the plots.
```
plt.show()
```

To conclude, that's how I analyzed Virat Kohli's performance with Python. Analyzing a player's performance is one of the Data Science use cases in sports analytics that I hope to pursue. I hope you enjoyed going through this reflection, reading about how I coded this project and the insights I gained from it.
