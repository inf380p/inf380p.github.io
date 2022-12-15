---
layout: post
author: Stuks
title: "CSV post week 1"
---

I was struggling so I asked a friend for assistant. One issue I apparently kept running into was I was basically over complicating things, for example making the While Loop to ensure the menu doesn't end until the user adds an input. I was trying to basically reformat I think, adding a new input statement that would end the loop instead of just addinga new list to the dictonary that could be called to break the loop. I'm wondering if this is something else I've struggled with in the past, am I over complimcating things? Logic is difficult for me, it always has been, so I struggle to try and remember where everything links too and I might create more steps than nesscary. 

I was able to finish the steps for 9, 10 and 13 I think, but I messed something up. Right now when I select to browse the rows, it gives me an endless loop of "Continue (Y/n). Putting in Y just promts 'Continue' without showing any colums being printed. Typing N either does nothing, doesn't even seem to end the program. I've also gotten errors from it. Not sure what I did wrong.





<iframe src="https://trinket.io/embed/python3/e15a95b9b6" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


import csv
import random
import interface

print("Welcome to the CSV Explorer\n")

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
# (Optional)
# - Feature: Adapt program to work as well as possible with ischools-messy.csv
###########


# Set variables we'll need later
filename = "ischools-clean.csv"

# List of choices to present in main menu 
menu_dict = {
  "1" : "Browse rows of data",
  "2" : "Print specific row",
  "3" : "Select columns to print",
  "4" : "Change data file",
  "5" : "Exit CSV Explorer"
}

# Get a list of dictionaries from CSV file
with open(filename) as file:
  reader = csv.DictReader(file)
  row_dicts_list = list(reader)

# Headers of the CSV are the keys of any row dictionary
# Get the keys from the first row
headers = row_dicts_list[0].keys()
def print_columns (filename, headers):
# Let user choose which columns to print, or print them all
  columns_to_print = []
  if interface.input_is_yes(f"File '{filename}' has {len(headers)} columns. Select which columns to print?\n", default = "y"):
    for header in headers:
      return columns_to_print
      selected = interface.input_is_yes(f"Do you want {header} in simplified print view?", default = 'y')
      if selected:
        columns_to_print.append(header)
    else:
      print("All columns will be printed")
      columns_to_print = headers
  
columns_to_print = print_columns (filename, headers)

while True: 
  choice_str = interface.get_menu_choice(menu_dict)
  
  # Tell user what choice they made
  print(f"You chose {choice_str}:")
  print(menu_dict[choice_str])
  
  # Do what they asked. 
  # Note: we have to manually keep track of what choice should do what,
  # which we do by ensuring the strings we compate `choice_str` with 
  # match up to the keys in menu_dict.
  if choice_str == "1":
    # Browse rows
    # User can start from one or pick their own starting row
    if interface.input_is_yes("Start from row one?", default = 'y'):
      # First row in the list is at index 0
      first_row_int = 0
    else:
      first_row_int = interface.get_valid_row_int(row_dicts_list)
  
    # Loop through the list of row dictionaries, starting at the selected first row.
    for row in row_dicts_list[first_row_int:]:
      for key in columns_to_print:
        print(row[key])
      if interface.input_is_yes("Contine?", default = 'y'):
        continue
      else: 
        break
  elif choice_str == "2":
    # Print specific rows
    if interface.input_is_yes("Print random row?", default = 'y'):
      row = random.choice(row_dicts_list)
      
      for key in columns_to_print:
        print(row[key])
    else:
      row_int = interface.get_valid_row_int(row_dicts_list)
      row = row_dicts_list[row_int]
      
      for key in columns_to_print:
        print(row[key])
  
  elif choice_str == "3":
    columns_to_print = print_columns (filename, headers)
    
  elif choice_str == "4":
      print("""
  Our flow of control and program architecture won't let us
  change CSV files right now.
  
  To support changing data files we'd need a way to overwrite
  `row_dicts_list` and then run the program again.
  
  In the meantime, we open a specific file at the beginning.
  Users who can code can change `filename` to change what
  CSV we use.
  """)
  
  elif choice_str == "5":
      break
  
print("Goodbye")
