---
layout: post
author: simon871028
title: "Feng's Final Project and Reflection"
---

## Code and introduction

Here is my code

<iframe src="https://trinket.io/embed/python3/dadd6fb8d9" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

I plan to work on data analysis project on NBA players data from 2021-2022 season. Analyze player's efficiency and provide advanced stats through data visualization library (matplotlib).

The reason why I am doing this project is that I am such a big basketball fan, I would like to use this opportunity to gain more insights from the players' stats and help others to interpret the raw data more easily.

## Milestones
I will illustrate my approach by describing how I completed evert milestone.
- [x]Find valid datasets from either Kaggle.com or other 3rd party gathered datasets.
  1. Found 2 datasets from Kaggle.com called `nba2021.csv` and `nba2k20-full.csv`.
  2. `nba2021.csv` provides basic data for each players played for NBA in 2020-21 season.
  3. `nba2k20-full.csv` provides data such as salary, height, draft order etc for each player in 2020-21 season too.
  
- [x]Start the data cleaning/exploratory.
  
  Here is how I cleaned and merge two datasets into a single dataframe in `preprocess.py`:
  
  ```python
  def merge_n_clean(x,y,s):
    # select needed columns and merge these two dataframe by player's name
    filter = ['Player', 'Pos', 'PTS', 'TRB', 'AST', 'STL', 'BLK', 'FGA', 'FG', 'FTA',
         'FT', 'TOV']
    df = pd.merge(
      x[filter],
      y[["Player","Salary"]],
      on = 'Player'
    )
    # remove the dollar sign from salary column then turn it into interger
    df.Salary = [tmp.strip('$') for tmp in df.Salary]
    df['Salary'] = df['Salary'].astype(int)
    df = df.sort_values(by="Salary", ascending = False)
    return df
  ```
  
- [x]Think of what kind of advanced statistic results I would like to visualize and can provide meaningful insights.

  Since NBA player get paid so much, I think to do an evaluation between players **salary** and their **EFF value** on the court throughout the season would be fun.
  **EFF value** is not provided from any of the datasets that I found, so I have to calculate it myself using Python.
  That's see the definition of EFF value first : [EFF](https://en.wikipedia.org/wiki/Efficiency_(basketball))
  
  ```
  Basically it is -> (PTS + REB + AST + STL + BLK − ((FGA − FGM) + (FTA − FTM) + TOV))
  ```
  Since these stats can be found in `nba2021.csv`, I can easily calculate it using the following function and sorted the dataframe by EFF in `calc.py`:
  
  ```python
  
  def calc_EFF(df):
  
    df['EFF'] = (df['PTS'] + df['TRB'] + df['AST'] + df['STL'] + df['BLK']
    - (df['FGA'] - df['FG'] ) 
    + (df['FTA'] - df['FT'] ) 
    +df['TOV']
    )
    df = df.sort_values(by="EFF", ascending = False)
  
  return df
  ```
  
  After that, I would be able to caculate the ratio between salary and EFF for each player  in `calc.py` :
  ```python
  
  # caculate cost effective ratio -> salary / EFF and sorted the dataframe by Ratio

  def calc_ratio(df , order):
  
    df['Ratio'] = df['EFF'] / (df['Salary']/ 10000)
    if order == "ascending":
      df = df.sort_values(by="Ratio", ascending = True)[:10]
    else:
      df = df.sort_values(by="Ratio", ascending = False)[:10]
    return df  
  ```
  
  

- [x]Design and develop interface
  I used **infinite while loop** to create a control panel which can be broke by selectiing option 5
  ```python
  options ={
    "0" : "Print all Stats",
    "1" : "Top 10 Highest Salary Players",
    "2" : "Top 10 Highest EFF Players",
    "3" : "Top 10 Highest Cost-Effective Players",
    "4" : "Top 10 LEAST Cost-Effective Players",
    "5" : "Exit",
  }
  ```
  Each option provides different data query and charts.
- [x]Visualize the data
  I used `matplotlib` to visualize my data in bar charts as follows:
  ```python
  #Function to create a bar chart                
    def bar_plot(x, y, title, df):
      df.plot(kind = 'bar',
            x = x, # data for x axis
            y = y, # data for y axis
            title=title
            )
      # show the plot
  plt.show()
  ```
  And this is one of example in my code to do the visualization :
  
  ```python
    bar_plot("Player","Ratio","Top 10 LEAST Cost-Effective Players",ratio)
  ```
  
  ## Reflection
  
  It's very cool to get to utilize what we've learned from class to build up this project. While dealing with the project, I accidentally closed the tab for trinket when I almost finished it.
  Which is extremely frustrating , but I took it as a great opportunity to gain more hands on experience by code it from scratch once again. I was initially more familiar with **plotly** instead of **matplotlib**, however, trinket only supports **matplotlib** which forced me to use it. It's also something valuable to me since if it were not for the project, I wouldn’t have the chance to get to know the library and gain familiarity with it.
  
  Working on a project that suits my interest in always fun, I am glad that I get to do a project for class using the data from NBA and create meaningful insight.
  
  If I had more time, I would want to try and create a search function that enable user to search for specific stats or players. I would want to provide more advanced stats and chart as well. Maybe doing something for major leagur sports such as MLB, NFL or even college football would be fun too.
  
  Thank you Professor and all the classmates that have helped me throughout the way. I have been enjoying this class and learned a lot.
 
