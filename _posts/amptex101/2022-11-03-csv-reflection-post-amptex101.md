---
layout: post
author: amptex101
title: "AP's CSV code and reflection!"
---

##1st code reflection

### The original assignment asks for us to complete the following to-dos: 

###########
# TODOS
# - Feature: Put the interface in a while loop so that the user can do multiple things
# - Feature: Create a new main menu option so that user can exit the program
# - Refactor: Make selecting of columns_to_print a function, and call it
# - Feature: Allow user to re-select which columns get printed
# - Test: Ensure program uses new selected columns
#
# - Refactor: Make creating the row_dicts_list into a function, and call it
# - Feature: Use `get_csv_filename` to let the user select a new file
# - Feature: Use the selected filename to create a new `row_dicts_list`
# - Test: Ensure user is able to select ischools-messy.csv 
#         (Note: program will not work in the same way; that's fine)
#
###########

###I'd like to talk about the second feature found in the todos -- it asks that we "create a new main menu option so that the user can exit the program. This requires us to edit the code to include a fifth option:

```
menu_dict = {
  "1" : "Browse rows of data",
  "2" : "Print specific row",
  "3" : "Select columns to print",
  "4" : "Change data file",
  "5" : "Exit"
}
```
###I did that first, because it seemed easy. Definitely a lightbulb moment! (Not many of those in this assignment for me.) And it was with using dictionaries, which is a relatively new concept for the class. 
###Then I proceeded to actually create the new menu option by adding this code: 

```
elif choice_str == "5":
  print("Goodbye")
  break
```

###I forgot about needing to include the "break" line of code at first. Also, a random aside -- why are we coding in both main.py and interface.py?I tried to find documentation online that explained this but came up empty. 

###The trinket for the 1st part of the assignment/what I've described above is below: 
<iframe src="https://trinket.io/embed/python3/38da3f7329" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


##2nc code reflection


###I did not find the rest of this assignment easy at all. The textbook is pretty easy to follow, but I didn't think it prepared me for the task of actually writing code to modify csv files. With Professor Houser's work in class, the code completed can be found here: 

<iframe src="https://trinket.io/embed/python3/fd1d62d576" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>



  
