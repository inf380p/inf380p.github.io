---
layout: post
author: hannahmoutran
title: "Hannah Moutran's Final Project Update"
---
My project is a data analysis program, and is using a CSV file that I got from Data World.  The file contains *New York Times* bestseller information from 2011-2018.  

I am mostly sticking to what I had initially planned for this project.  From the CSV file, I cut out all columns except for author, title, publisher, and number of weeks on the list.  Initially, I had planned to separate into fiction and nonfiction, but then I realized that this list only contains fiction.  The list was 2,249 rows, but I cut it down to 379 by excluding all books with less than three weeks on the list.  In the original file, 0 signified 1 week, 1 signified 2 weeks, etc.  I thought that might be confusing to users, so I added 1 to all of those values.  

One big thing that changed is that when I started it was by using the CSV module (unfortunately I forgot to keep that code, but I changed my mind fairly quickly).  I decided on pandas basically because anytime I was searching for help online, they were using pandas.  I just think if it’s that widely used for data, I need to use this project to learn about it.  It is easier and can do cool things, but it’s not easy, and I have already spent a lot of time on this.  Still, I think I need to have these skills, so it’s time well spent.  

So far, I have the Main Menu created, and an idea of what each choice could potentially do.  I also have the CSV file in the trinket, and a file called backing.py where I have some supporting code.  I’m using my notes from the textbook, google searching, and also old Trinkets that we did during this class.  I’ve found that the best thing is to search Google for examples, it’s much easier to understand and see how things work by looking at how someone writes the code in practice.  

Here’s the menu, based on the CSV file assignment: 
```python
menu_dict = {
  "1" : "Choose columns to print",
  # show headers, allow the user to choose columns, make this callable.   
  "2" : "Choose specific rows",
  #only rows with a certain number or more on the bestseller list for instance 
  "3" : "Sort by specific column",
  #the user may want to sort by author
  "4" : "Graph it",
  #integrate some kind of visual 
  "5" : "Give me a book to read",
  "6" : "Erase choices and start over again",
  "7" : "Exit"
  #ideally, every choice made during this process would apply to whatever other choices the user made.  So, if they want to choose different columns, for example, they would have to start over.
}
```

I will adjust that over time, I’m sure.  It isn’t cleaned up and nice yet but at the bottom of the trinket, I have some code written that I will use to execute choices 1 and 2:

```python
#menu 1 print specific columns, no index 
print("Select specific columns:")
print(df[['Author','Publisher']].to_string(index=False))

#menu 1 displaying the list of column names to user
print('List of column names : ',list(df.columns))
print(df)   

#menu option 2: select rows based off of conditions - first condition that weeks on list is greater than 9
new_df = df[df['Weeks_on_List']>9]
print (new_df[['Author','Publisher', 'Weeks_on_List']].to_string(index=False))
```
I’m sure I will have roadblocks, but right now everything is okay.  My stretch goals are to create a graphic and to have the user input build on itself until they choose to start over.  I think everything is doable, though I don’t know how to do it now.  I already consider some of these things as negotiable depending upon if I can get to them, so I’ll be flexible and change the plan if I need to.  

Here’s a copy of the trinket as it exists now: 

<iframe src="https://trinket.io/embed/python3/4d4d432650" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
	
##Added after class: 
###These were my initial milestones: 
 - Download and clean up csv file 
 - Create dictionary with keys
 - Create Menu that asks for user input, allows for an exit function 
 - Add functionality to menu, making conditionals that will guide the output 
 - Make functions for the menu choices 
 
 ###Here's new list of milestones based off of what I still have left to do:  
 -  create menu functionality for the options 1 and 2 using the code I already have  
 -  figure out how to sort by a column
 -  figure out how to create graphs (stretch)
 -  write code for recommending a random book 
 -  figure out how to keep the user's choices building on one another until they request a clean slate 
 -  possibly look into scraping data using Python (mega-stretch, but maybe)
