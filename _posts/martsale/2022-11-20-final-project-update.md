---
layout: post
author: martsale
title: "Alexis's Final Project Progress Check In"
---

# State of My Final Project
My work on my final project is going slower than I would like, but that's ok because that's how learning happens. I've been tackling bite-sized features of my program over the course of a few days to not burn out on creating it. Right now, I'm still trying to parse out my data without calling on the csv module. 

## What I did this week
### I can import data and sift through the data to create dictionaries 
In this code, the data gets pulled into the program. The data is split into lines using a `for` loop. I then break the lines apart into dictionaries based on the place in the list and append the word into the dictionary. I can then change what dictionary is being printed manually in the code right now. For example, printing `genre` will list out all the genres in data.
<iframe src="https://trinket.io/embed/python3/7b2b8233ba" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

### The program can (kind of) read line-by-line
I've been working through line-by-line reading. The following code will take the user line-by-line. The text needs formatting though.
<iframe src="https://trinket.io/embed/python3/63f0c3dc55" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
I worked on a smoother way to read line by line that's a little less awkward feeling. It doesn't work yet but it's part of the process.
<iframe src="https://trinket.io/embed/python3/3673a2ac21" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Features left
I need to rework the line-by-line feature to run more smooth and efficiently. Here a few notes that I've left myself in the code in how I think this could work:
```
# current thought process:
# break up manually by line
# append each line to line list
# call on line list by number variable incrementing by 1
# split that line
# print so it's readable
# repeat
```
I also need to pull in a data visualization component still as well as get all of the features running together in the menu. If I can't get the line-by-line to run soon, I'm going to explore bringing the csv module in. 

## Housekeeping left
I need to organize my code comments a bit better and delete out old code I'm not using. I also have a habit of using camel case, and need to ensure that I'm using snake case for my function and variable names. 

## Apirational Goals
Right now, I think filtering might be beyond my abilites with the time that I have left. Even if I take that out, the user can browse music, be randomly suggested music, and visualize the submissions.
