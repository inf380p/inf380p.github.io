---
layout: post
author: hannahmoutran
title: "Hannah's Final Project: NYT Bestsellers"
---

## Introduction
I chose to do a data project because I thought that would be the most useful to me in the future.  I initially started this project thinking that I would use the CSV module to process data.  I followed that path for maybe two days, and then I switched to Pandas.  I decided to switch because as I was searching for answers to questions that I had, I kept coming across people using Pandas.  It became clear to me that Pandas is a great library and that it is also widely used to manipulate data.  I just decided that, practically speaking, it would be good for me to learn how to use it.  It gave me a leg up in some ways, but I also had to learn a whole new thing on my own, because we didn’t cover Pandas in the class or the book.  In the end, I am super happy with the program and with all that I have learned from doing it. It was a good next step.  

My program uses a dataset of *New York Times* bestsellers from data.world.  It’s a CSV file created by Michael Tauberg.  You can find it here: https://data.world/typhon/new-york-times-bestsellers-from-2011-to-2018.  I cleaned it up a bit before putting it in my Trinket.  I removed a bunch of columns that had links to book reviews, dates that were confusing, and so on.  I also did some data cleanup.  For example, there were a bunch of books that said ‘0’ in the weeks on the list column.  They were actually on the list for 1 week, so I corrected that.  I also for most of the time that I was creating this program was using a shortened list, but just two days ago I changed it for the full version.  It doesn’t seem to have significantly impacted the speed of the program.  I did have to adjust the code slightly to accommodate printing such a large dataset, though.  

##### Before I get into the code, I’ll just put the Trinket here.  It should explain by itself what it does (or I've done something wrong).  
## Final Project NYT bestsellers: 

<iframe src="https://trinket.io/embed/python3/300a8033ea" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Workflow 
I started this program using the menu code from the CSV Trinket we worked on in class:
<iframe src="https://trinket.io/embed/python3/8f70e6beb2" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Once I had the menu up and running, then it was creating a data file, figuring out what libraries I was going to use, and going through the menu choices one by one.  Everything built on itself, and problems became features over time.  I ended up adding two more menu options just last week, one is to perform a couple of basic calculations that I think the user might find interesting, and the other is a ‘help’ page.  My method was to tackle each menu option as thoroughly as possible before moving on.  I did a lot of research while doing this.  I often read through a bunch of articles on a topic and ended up directly using the advice of just one or two of them.   

Occasionally I got good advice from my husband, though I purposefully kept him at a distance.  I was trying to create a list of the books from the CSV file so that I could pull a random choice from there.  I was having some issue with it and complaining and he asked why I couldn’t just make the column directly into a list.  I looked that up, found a how to guide, and went with that.  After seeing my pie chart, which was a bit of a mess, he also found and sent to me a Stack Overflow page on how to do an ‘others’ category in a pie chart.  I adapted that for my program, and also used the slice and copy method from there for the author bar graph.  

I have at the bottom of this post a list of the resources that I directly used.  There are many more that I read through but didn’t directly adapt the code examples for my program.  One big thing that I took out of this whole experience is to write ‘examples’ after any other search terms to get the most helpful results.  Sometimes I also just had to step away.  I had occasional flashes of insight after giving some space to the project, for example when I set all of the variables so that whether the user chooses options or not, something will print.  I’m sure it’s messy in comparison with what a professional would do, but it does work. 

Once I had everything up and running, then I went back and moved menu choices around so that the menu flowed better.  I also filled out the introduction that I had written for the user, and wrote up the help page (Menu choice 9). 

## Code Specifics
#### Setup:
At the beginning, I had a problem with the rows.  Not all of the rows of the dataframe were printing.  I had to set a max number of rows, using this code: ```pd.options.display.max_rows = 4000```.  Initially, I set that at 400, but changed it to 4,000 when I switched to the larger file.  There were two other display options that I had to use in order for the full dataframe to print:  ```pd.options.display.width=None``` allows for all the columns to print, and ```pd.options.display.max_colwidth = 25``` sets the column width, so that each column is wide enough to display its information. 

All of that setting up code is here: 
```python
pd.options.display.max_rows = 4000
pd.options.display.max_colwidth = 25
pd.options.display.width=None
```
I also found this handy bit of code in the pandos docs: ```pd.describe_option()```, which is how I ended up finding this: ```display.max_colwidth```.

Now, I’ll just run through the menu choices, in the same way that I did for the project itself.  

#### First menu choice:
I chose to allow the user to select columns by name. Looking back, it might have been better to use the drop method for this, to make it a bit less busy.  Regardless, here’s the code I used, selecting the columns based off of user input: 

```python
column_choices = input("\nThese are the column headers.\nIf there is a column you would like to exclude from your dataset, type in the corresponding number:\n1: Publisher\n2: Author\n3: Title\n4: Weeks on List\n5: none")
if column_choices == "1": 
      selected_columns = ['Author','Title','Weeks_on_List']
selected_df = original_df[selected_columns]
```
#### Second menu choice:
This allows the user to select rows based off of input.  This time, I took the input, turned it into a variable, and then only kept the rows in the ‘Weeks_on_List’ column that were greater than or equal to that variable as an integer.  I found a great resource with a video for this (Geeks for Geeks, linked below).  They called it “selecting rows based on conditions.”
Here’s the code:

```python 
row_choices = input("\nNow you can choose if you only want to see bestsellers that were on the list for a specific number of weeks.\nFor example:\nFor 10 weeks or more, enter 10\nFor 15 weeks or more, enter 15\nFor 25 weeks or more, enter 25")
selected_rows = int(row_choices)
selected_df = selected_df[selected_df['Weeks_on_List']>=selected_rows]
```
#### Third menu choice:
This allows the user to sort the columns based off of their input.  I used the ascending parameter only for the weeks on the list, because otherwise, the larger numbers would be at the bottom.  Conversely, for the names, it’s better in my opinion to start with ‘a’ at the top and go down to ‘z’.  

```python
df_sorted = df_sorted.sort_values(by ='Weeks_on_List', ascending=False )
```
#### Fourth menu choice: 
This is for the user to print the data.  Initially, I had the program set up to do this for every menu choice, but it seemed better to let the user choose when they wanted to see it.  So, I went back and replaced the ```print(df)``` calls with the following: 

```python
print("\nYour new data will show the following columns:\n"+str(selected_columns)) #menu choice 1
print ("\nYou chose: books that have been on the bestseller list for "+(row_choices)+" weeks or more.”) #menu choice 2
print ("You chose: "+ (sortcolumn)) # menu choice 3
```
The print function is: 
```python
def print_on_screen (): 
  print (df_sorted)
```
For all of these user input menu choices, as well, I had else statements at the end in case they entered something that isn’t a choice.  For example, in menu choice 4, the else statement is: 

```python
else: 
   print ("Sorry, that wasn't one of the choices.  Here's the unsorted data.  If you want to sort by a column, try again!")
 ```
#### Fifth menu choice:
I wanted to reset everything, so I just copied all the beginning variables into that slot.  I had to have all of these set so that even when the user chooses nothing, everything still works.  So, if they go to menu option 2 and choose rows without ever choosing columns, for example, there is still a value to put into  ```original_df[selected_columns]```.   Same thing with rows-if the user chooses nothing, the value equals 1 and will include all the rows.  Likewise, as you can see above, the print function always uses the variable df_sorted, even if the user doesn’t sort by anything.  

```python
 #reset
selected_columns=['Publisher', 'Author','Title','Weeks_on_List']
selected_rows = 1
selected_sort = "None"
selected_df = original_df
df_sorted = selected_df
```
#### Sixth menu choice:
As mentioned above, I made a column from the user’s altered dataframe into a list, and then picked a random choice from there:
 
```python 
titles_list = selected_df["Title"].values.tolist()
print("\nNYT bestseller to try:")
print(random.choice(titles_list))
print("Enjoy!")
```

#### Seventh menu choice:
This calculates the mean and median of the weeks on the list from the original dataframe.  I rounded it to make it a bit prettier.  
 
```python
meanweeks = original_df["Weeks_on_List"].mean()
meanweeksround = round (meanweeks)
medianweeks = original_df["Weeks_on_List"].median()
medianweeksround = round(medianweeks)
print ("\nThe average number of weeks on this list for a book is " + str(meanweeksround) + ".\n")
print ("\nThe median of the number of weeks on this list is " + str(medianweeksround) + ".\n")
    
```
#### Eighth menu choice: 
This is the graphs.  They were complicated, and I’ve put a bunch of the resources I used at the bottom of this post.  I found a great article on how to make an others category for a pie chart, so that helped a lot but it took while to adapt it.  I spent a long time trying things out and seeing if they worked.  There is still a small issue in that the first graph stops the while loop completely, and the second one doesn’t print the menu underneath the graph.  I added some text before the user chooses which graph they want that will hopefully make that less confusing.  
Here's the text that prints before the user input text: 
```python
print("\nBefore you choose a graph, we wanted to let you know that when you see a graph, the 'Main Menu' may not pop up again afterwards.  Sorry for this inconvenience, we will be working on it soon! If you don't see the main menu after viewing one of the graphs, please hit 'Run' at the top of the screen to restart the program.")
```
Here’s the code for the first graph: 
```
df2 = original_df.groupby(['Publisher']).sum().sort_values('Weeks_on_List', ascending = False).reset_index()
#making a copy of the df that uses a slice of the original df 
topten_df = df2[:15].copy()
#making a new row that adds all the publishers after the top ten into one 
new_row = pd.DataFrame(data = {'Publisher' : ['Others'],
'Weeks_on_List' : [df2['Weeks_on_List'][15:].sum()]})
#putting them together 
toptenandothers_df = pd.concat([topten_df, new_row])
#making the graph
toptenandothers_df.plot(kind = 'pie', y='Weeks_on_List', ylabel = '', labels = toptenandothers_df['Publisher'])
#a parameter that I found and thought was cool but took out for a cleaner look: autopct='%1.1f%%'
plt.title('Most Successful Publishers')
plt.legend('', frameon=False)
plt.figure(figsize=(115,115))
plt.show()
```
The second graph is similar in some ways, but I took out the others category and just decided to go with the slice and copy method for the top ten authors.  I had to create a new dataframe from the author name and the value counts, I have the resource that guided me on that at the bottom of the post.  I also did a lot of formatting research and tweaking on this one, resources below as well.  Here’s the code: 

```python
#Author bar graph
#making the value_counts into a dataframe with reset_index
author_occurs_df = (original_df['Author'].value_counts()).reset_index()
#creating the column names
author_occurs_df.columns = ['Author', 'Times_on_List']
topten_author_df = author_occurs_df[:10].copy()
c = ['orange', 'pink', 'blue', 'green', 'purple', 'black','grey','red', 'cyan', 'yellow']
topten_author_df.plot.bar(x = 'Author',y = 'Times_on_List', color = c)
plt.ylabel('Number of books on list')
plt.title('Most Successful Authors')
plt.rcParams['figure.figsize'] = (16.0, 16.0)
plt.xticks(rotation=30, horizontalalignment="center")
plt.tight_layout()
plt.legend('', frameon=False)
plt.show()
```
#### Ninth and Tenth menu choices: 
These are just a help page and an exit from the program.  There’s also an ‘else’ statement at the very end to catch anything that people might input outside of the menu choices.  
   
## How I would continue to improve this program over time 
There are still a couple of things that bother me.  I made variables and did a lot of setting and resetting them to accommodate for changes that the user made or didn’t make to the dataframe.  To be honest, at this point I just don’t want to mess things up or get too distracted by the problem because it’s working well and the due date is almost here.  However, I did do some reading on global variables (https://www.w3schools.com/python/python_variables_global.asp) and I think learning more about that and cleaning things up would be a good improvement for the program.   

The other big thing is that after a graph displays, the while loop is broken and the user doesn’t see the menu again.  I did write the user a note so that they don’t get confused, but I would like to find a solution for that problem.  

Moving on to things that aren’t problems, but would be great to add: more graph options (examples here: https://pandas.pydata.org/docs/user_guide/visualization.html).  Also, a word cloud of the titles would be really fun (https://thecleverprogrammer.com/2021/11/11/word-cloud-from-a-pandas-dataframe-in-python/).  


## Next Steps 
My next steps are going to be learning to scrape data on my own and getting myself set up to code with an IDE.  To begin, I’m setting myself a goal of working on scraping data over the break.  There are, from what I can see, three ways that I could start.  One is to scrape *New York Times* data using their API.  Another is to scrape data through Pandas.  The last is to use a module called Scrapy.  The plan is to try all of them and see which works the best for me in terms of efficacy, ease of use, etc.  Getting set up for coding on my computer and experimenting a bit is another good next step for me.  I have the language and the framework, now I need to know the software.  I think Python skills, being able to use Pandas, and knowing how to scrape data, taken all together, is a pretty powerful set of skills to bring to the future work that I will do, so it’s the worth the time that it takes to learn it all.
  
## Conclusion 
I want to say how satisfied I feel with how far I’ve come in my coding abilities.  I had almost no coding experience when I started this class.  Just before beginning to write this pull request, I was testing the program again and noticed a problem with the printing.  I went back to the code, found what I guessed was the issue, changed it, tested it, saved it, and the problem was solved.  I can do that now.  It has been a consistent progression over the course of the semester.  I definitely don’t know everything, and I probably won’t ever learn everything, but I have a basic vocabulary and understand a chunk of the logic.  That makes it possible for me to learn on my own, because I can research.  I learned so much over the course of doing this final project, just from reading online and teaching myself, trying things out and seeing what worked.  I pulled information from the book, the class, my notes, previous projects we’ve done, blog posts, and Stack Exchange in the course of working on this.  I won’t say that I have fluidity, it takes time and research for me to code.  However, I’m really proud of this program and I’m feeling good about what I have learned and my ability to cobble things together and create a working program.    

## Resources
###### Basics to start with: 
https://www.w3schools.com/python/pandas/default.asp
https://pandas.pydata.org/docs/user_guide/10min.html
https://www.geeksforgeeks.org/python-pandas-dataframe/
###### Basics of starting a pandas dataframe from a CSV file: 
https://www.w3schools.com/python/pandas/pandas_csv.asp
###### Display settings for the dataframe: 
https://stackoverflow.com/questions/15455722/is-there-a-max-size-max-no-of-columns-max-rows;https://pandas.pydata.org/pandas-docs/stable/user_guide/options.html; https://www.skytowner.com/explore/displaying_full_non_truncated_dataframe_values_in_pandas; https://stackoverflow.com/questions/11707586/how-do-i-expand-the-output-display-to-see-more-columns-of-a-pandas-dataframe. 
###### Pandas df column to list: 
https://sparkbyexamples.com/pandas/conver-pandas-column-to-list/
###### Selecting only certain columns: 
https://www.statology.org/pandas-select-multiple-columns/
###### Selecting rows based on conditions: 
https://www.geeksforgeeks.org/selecting-rows-in-pandas-dataframe-based-on-conditions/?ref=lbp
###### Sorting columns: 
https://thispointer.com/pandas-sort-rows-or-columns-in-dataframe-based-on-values-using-dataframe-sort_values/
###### Rounding numbers in python different ways: 
https://kodify.net/python/math/round-integers/
###### Calculating average and median from a column in pandas: 
https://sparkbyexamples.com/pandas/pandas-get-column-average-mean/; https://erikrood.com/Python_References/pandas_column_average_median_final.html
Graphs resources: 
###### Pie graph with others row: 
https://stackoverflow.com/questions/48587997/matplotlib-pie-graph-with-all-other-categories
###### Value_counts and how to convert them into a dataframe (for the bar graph): 
https://cmdlinetips.com/2020/08/pandas-value_counts-how-to-get-frequency-counts-of-variables-in-a-dataframe/
###### Adding column names to a newly created dataframe: 
https://www.geeksforgeeks.org/add-column-names-to-dataframe-in-pandas/
###### Rotating the labels: 
https://www.shanelynn.ie/bar-plots-in-python-using-pandas-dataframes/
###### plt.tight_layout() saved the day! 
https://stackoverflow.com/questions/62605103/how-to-increase-space-between-bar-and-increase-bar-width-in-matplotlib
###### Colors for bar chart: 
https://matplotlib.org/2.0.1/api/colors_api.html
###### General how to plot a dataframe: 
https://www.geeksforgeeks.org/how-to-plot-a-dataframe-using-pandas/
https://www.geeksforgeeks.org/how-to-create-a-histogram-from-pandas-dataframe/
https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.hist.html
https://dataindependent.com/pandas/pandas-bar-plot-dataframe-plot-bar/
https://www.shanelynn.ie/bar-plots-in-python-using-pandas-dataframes/
###### Adding a percentage to pie chart - didn’t end up using, but still cool: 
https://kontext.tech/article/402/pandas-dataframe-plot-pie-chart
###### Removing a legend from a pie chart: 
https://www.statology.org/remove-legend-matplotlib/
