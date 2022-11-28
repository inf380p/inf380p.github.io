---
layout: post
author: jpmartinezutexas
title: "CSV reflection"
---

# CSV Reflection
The assignment was to modify a CSV file that contained information about ischools around the world. Information such as: The university, the school/unit, the locatiom, the region, and the membership status.
It reminded me of a database in SQL, in the way that we were writing code that would make sense out of a bunch of random information if you just looked at the file.
In this way, I enjoyed the challenge of the assignment. It reminded me of both a database as well as a classical 60s computer, and text games where you type in answers.

## First things first
I apologize for the late assignment, I turned this in the night it was due. I did not read "your final code should identify and fix as many of the TODOs in the comments as you can".
Emphasis on "As you can". As of 11/3/22 this project is still unfinished, I was not able to complete all the todos, but I will be returning to this and completing all of the TODOs.

## Let's get started

Unfortunately at the time of turning this in I was not able to complete all of the TODOs, however I did have most of them complete. Unfortunately, the file where I have a few more of them done, leads to bugs where it crashes on trying to browse rows of data/print specific rows. 
However, that final file is the file where you can change between data files, so that's neat, and where row/dicts/lists is a function that I was able to call. 
Here I will link in both files. 

This first file is the file post - 10/27/22.

<iframe src="https://trinket.io/embed/python3/2ec65e32a0" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe> 



This next file is my final/current code - 11/3/22

<iframe src="https://trinket.io/embed/python3/3c62b9a642" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

The To do objectives were as follows. 

```python
# X Feature: Put the interface in a while loop so that the user can do multiple things - Done
# X Feature: Create a new main menu option so that user can exit the program - done
# X Refactor: Make selecting of columns_to_print a function, and call it -option 3
# X Feature: Allow user to re-select which columns get printed
# X Test: Ensure program uses new selected columns
#
# X Refactor: Make creating the row_dicts_list into a function, and call it
# X Feature: Use `get_csv_filename` to let the user select a new file
# - Feature: Use the selected filename to create a new `row_dicts_list`
# - Test: Ensure user is able to select ischools-messy.csv - This should work...
#         (Note: program will not work in the same way; that's fine)
#
# (Optional)
# - Feature: Adapt program to work as well as possible with ischools-messy.csv
```
The X marks which I completed, but really I was not able to complete all of these on each. 

On the first code i was able to complete the top row, while the second, I worked on getting the bottom row to work. I had a lot of help from the professor in completing the top row, but I am proud to say that
I was able to to implement the while loop and the exit option by myself. I will demonstrate below through some examples. 

## Python examples

This is the first part of adding an exit solution. 
```python
# List of choices to present in main menu 
menu_dict = {
  "1" : "Browse rows of data",
  "2" : "Print specific row",
  "3" : "Select columns to print",
  "4" : "Change data file",
  "5" : "Exit program" #added
}
```
I will show the second part below. 
```python
#there is a while loop for all of the elif choices far above here, break is here to break the while loop which stops the program. 
elif choice_str == "5":
   print("""Closing program. See you later!""") #May not be the most professional sounding, but I thought I could make it a little more personal.
   break
    #At first I had break in the wrong line the first time, it would break everything instead of just after hitting 5 (exit). Just indentation issues. 
```
This was the first time I used while loops, and I referred back to the book while writing the loop. 
https://runestone.academy/ns/books/published/inf380p2022/functions/funcWithLoops.html - I found this lesson in particular helpful. 

Writing the end functionality itself came relatively easily to me, as there were 4 others to go off of, and once the while loop and break were placed, it almost writes itself. 

Next up was converting columns_to_print into a function and calling it. This one was definitely challenging. Luckily, the professor assisted us on this one, which helped me in the task of creating row_dicts_list into a function, although I wouldn't call that ready yet, as I keep encountering errors. 
Regardless, I will talk about it.

First, here is an example of defining columns_to_print as a function, with the use of get_columns_to_print

```python
def get_columns_to_print():
  columns = []
  for header in headers:
    selected = interface.input_is_yes(f"Do you want {header} in simplified print view?", default = 'y')
    if selected:
      columns.append(header)
      
      
      #much later
 elif choice_str == "3":
    #call columns_to_print here
    columns_to_print = get_columns_to_print()          
```

We first define get_columns_to print, instead of just calling it get_columns to print, because we want to use that later. the choice_str ==  "3": represents where the user selects 3 - seelect columns to print.

After completing this, I felt that I could redefine row_dicts_list in a similar fashion.

```python
def get_row_dicts_list(filename):
  with open(filename) as file:
    reader = csv.DictReader(file)
    row_dicts_list = list(reader)
    return row_dicts_list #similar to our get_columns_to_print
    
row_dicts_list = get_row_dicts_list(filename)


# Get a list of dictionaries from CSV file (This is now in the function)
#with open(filename) as file:
#  reader = csv.DictReader(file)
#  row_dicts_list = list(reader)

# Headers of the CSV are the keys of any row dictionary
# Get the keys from the first row
#def headers(): - doesn't work
headers = get_row_dicts_list(filename)
#headers = get_row_dicts_list[0].keys()       
```

I am including some of my thought process in the code, which involves a good amount of trial and error, as I was trying things, wondering "Why doesn't that work", as the trinket result gave me hints. 
I once again used get_row_dicts_list instead of just row_dicts_list, and found some success with calling it later. 

```python
  elif choice_str == "4":
    #call row_dicts_list
    filename = interface.get_csv_filename()
    row_dicts_list = get_row_dicts_list(filename)
    #add in a back functionality if possible
    #headers = get_row_dicts_list[0].keys()
    #Because in while loop, it will take you back to the main menu after you select 1 or 2.
```

In the future, I think that a "back" functionality, which just selects the current file you are on, would be very helpful. Although I couldn't complete one in time, I think it would be useful, maybe not when you only have 2 files, but imagine choosing between 10 or 20.
The user may not remember exactly what file they were on, and going "back" could tell you which you are currently on, and take you back there. It would be a good way to design for user error. It'd be especially useful if they have just accidentally hit 4, and want to just go back.

Unfortunately, with this new code making 4 work, something else broke, meaning 1 and 2. I would receieve this message when I tried to call for rows. 

Traceback (most recent call last):
  File "/tmp/sessions/e73a32ca66250137/main.py", line 95, in <module>
    print(row[key]) 
TypeError: unhashable type: 'dict'
  
I would receive this message when trying to browse rows of data, or print specific rows. I know it is related to the changes I made, but I am not sure how to fix it unfortunately.
I have found this to be much like working with a rubicks cube. 
  Although you may have one side completed, you will end up messing up that side you completed while attempting to complete the whole cube. Luckily we can save multiple files, rubicks cubes don't have the luxury.
I think I need to just make way more versions of my code, and not be afraid to mess up an entire file, just to find the answer. 
Although stopping working on this and coming back later did not provide me the answers to this problem, I did find it a helpful technique in general! Looking at code with fresh eyes always helps.
  
Overall, I am dissapointed in myself in that I was not able to complete the TODOs, but I am determined to have this file work completely. 
It is interesting and I would like to have the full functionality in one document. 
  
JP Signing off. 
  

