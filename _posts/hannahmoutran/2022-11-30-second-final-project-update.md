---
layout: post
author: hannahmoutran
title: "Hannah Moutran's Second Final Project Update!"
---

## Done: 
- download and clean up CSV file 
- create dictionary with keys 
- create menu with different options for user 
- make conditionals that will guide output from user choices 
- create functions 
- create functionality for menu choices: 1,2,3,4,5,7,8
- figure out how to sort by a column 
- figure out how to create graphs
- write code for recommending a random book 
- figure out how to keep user’s choices saved 

## To do: 
- menu choice 6: start the user with a clean slate 
- add another menu choice: help
- add an explanation of the program at the beginning

## May do:
- improve graphing/perhaps add more graph choices 
- make the saving of the user’s data better.  Right now it’s probably messier than it needs to be  
- clean up the code in general, try to make it more sleek 
- test program with longer version of csv file, maybe switch

## Separate but related: 
- make code talk 
- write pull request, at least 1500 words 

My project is going well.  There’s some stuff that I still have to do, as you can see above, but I feel really good about how much I have gotten done. There are definitely things that were never on my official to do list, but that I realized were important while testing.  For example, I made a new menu choice for printing, and stopped printing the dataset every time the user made a choice.  Now the program just tells them what they've chosen, but doesn't print the whole thing until they choose the print option. Some things on my list were much easier than I thought they would be, for example the random book choice and graphing the data.  Visualizing capability is built into Pandas, and it’s also easy to do the random choice function once you know how to convert a column into a list.  

Here’s the code for the bar graph I have right now: 

```python
selected_df.plot(kind = 'barh',
        x = 'Publisher',
        y = 'Weeks_on_List',
        color = 'blue')
    plt.title('Publishers Marks')
    plt.show()
```
As you can see, it’s fairly simple.  All of the information on how to do it is in the pandas documentation, but I also got some help from reading many, many blog posts about what the different options were (https://www.geeksforgeeks.org/how-to-plot-a-dataframe-using-pandas/ was particularly helpful).  I saw a lot of interesting stuff that I haven't used, so I may do (see list above) more with the graphing capability of the program.  

Making a column into a list was as simple as this: 
```python
titles_list = selected_df["Title"].values.tolist()
```
I found out how to do that here: https://sparkbyexamples.com/pandas/conver-pandas-column-to-list/

Once I had the list, then I could just do this:
```python
print(random.choice(titles_list))
```

Some of the things I have on my to do list are very concrete, and others are very open-ended.  That’s purposeful.  I’ve dedicated a lot of time and I’ve learned a lot already.  At the same time, I don’t think there’s really an end to what I can learn and how I can improve the program.   I’ll just continue until I’m satisfied enough with it, and then call it a day.  

Here’s the Trinket: 
<iframe src="https://trinket.io/embed/python3/de1cca0efc" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

