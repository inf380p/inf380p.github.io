---
layout: post
author: scdai9
title: "Shih-Chieh's final project update"
---

### Introduction

I will do a data analysis project. Currently, I am playing an NBA Fantasy game, and I want to use Python to do data analysis so that it can help me to make some decisions.

### Progress
I tried to process the CSV file with the package`Pandas`. It is a widely used package in the Data Science community. Therefore, there are a lot of tutorials and discussions I can reference for how to use this package. 

```
import pandas as pd

df = pd.read_csv('nba_stats_2022-2023.csv')
print(df.head(10))
```


I think my next move will be implement all the functions in this program.
### Roadblocks
The file from the website (https://www.nbastuffer.com/)is in xlsx format. Therefore, I have to convert it to CSV manually. I found that when I read the file it did not show as expected. I will try to fix the issue.

### Revised Milestones
- [x]  Find Dataset
- [x]  Plan the interface (i.e. menu)
- [ ]  Data Preprocessing
- [ ]  Analysis Methods (Z-score)
- [ ]  Add help function (New milestore)
- [ ]  Data Visualization
### My Trinket Code
<iframe src="https://trinket.io/embed/python3/8c7e552b5c" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
