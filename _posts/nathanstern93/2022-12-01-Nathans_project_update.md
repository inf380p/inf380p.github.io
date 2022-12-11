---
layout: post
author: nathanstern93
title: "Nathan's Project Update"
---
For my project, I will be making a sortable dashboard of statistics for the best nba players of all time. I found a dataset on kaggle that has all statistics of all NBA players, sorted by season, in NBA history. This presents some issues. For one - the csv file is too large to put into trinket on its own. As a result, I have to read the csv of only the columns that apply to the top 75 players. For this part, I have to do brute force, and make a comma seperated list of espn top 75 players, put it into a list, and select from the csv any rows that contain the text of these players. This should make for a manageable data frame for trinket to be able to handle. Next, I have to choose the columns of the stats that I want to include. Now, this data set contains each players individual seasons as its own column, so I will need to collapse and sum by player name and career statistics. 

import pandas as pd
import numpy as np
import csv
import random

#will add list of top 75 NBA players from ESPN
#top_75 = {}

#read csv into df by only selecting top 75 players
df = pd.read_csv("Advanced.csv")
#df = df[df['player'].str.contains(top_75)]

#subset df for only the important statistics
#df=df[df['player','player_id' 'g', ...]

#collapse and sum seasons to get players career statistics
df.groupby(["player", "player_id"]).sum()
