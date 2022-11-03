---
layout: post
author: Soojin Park
title: "Soojin's revised CSV reflection"
---

## Before the first CSV file :sweat_smile:
When I first tackled this assignment, I felt overwhelmed. As someone new to coding, the concept of having multiple tabs (the csv files) and accessing all of them sounded tangible yet far from understanding this code as a whole. *How do I understand how everything works together to do what it does?* It felt like studying what human body does but I had to understand the functionality of the brain, organs, and even how they all work together for us to be who we are. After scrolling up and down on the untouched Trinket a first few times, I realized something. **That's the thing! No one completely knows how the whole system works. They study it bits by bits. ** Even doctors ~~know how our body works as a whole~~ have to specialize into certain specialty and learn that specific part of our body one by one to understand the harmony behind everything <sup> (been watching too much Grey's Anatomy, my apologies) </sup>. I started looking at each line of the code carefully and studied the code's purpose. For instance, 

```
#this calls on the function "interface.input_is_yes" and when the condition meets, it will trigger that question with y/n question. 
if interface.input_is_yes(f"File '{filename}' has {len(headers)} columns. Select which columns to print?\n", default = "y"):
```

I didn't know what "interface.input_is_yes" function did yet, but I knew what the line was trying to do, giving me reassurance that I am on the right path– taking one step forward. From there, I could go find "interface.input_is_yes" function and understand it, learning **bits by bits**. :smile:
As I repeat these two steps (I like to call it a form of a dance where you take one step forward and one step backward), I was starting to grasp what each code does. It's okay if I didn't understand how codes work together, but I at least knew how each code contributes to their assigned role. 


## Tackling the [first CSV file](https://trinket.io/python3/73616401ec) :persevere:
With the help of our classroom textbook and external readings from W3, I was able to tackle several TO-DO lists below: 

- Feature: Put the interface in a while loop so that the user can do multiple things :-)
- Feature: Create a new main menu option so that user can exit the program :-)
- Refactor: Make selecting of columns_to_print a function, and call it :-)
- Feature: Allow user to re-select which columns get printed :-)

It felt astonishing and a sense of accomplishment to be able to look at what I need to do and go straight into the section that I *thought* might involve this goal. For example, when I looked at the first two features, 

```
#if user picks 5, it skips this whole thing. If not, it goes down the list of "choice_str" to match whichever value input and continues
while choice_str != "5":
  
#individually calls the data but there's more efficient way to do this
  call_column()    

#choosing option 1 
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
      if interface.input_is_yes("Continue?", default = 'y'):
        continue
      else: 
        break
        print("Back to menu")
    choice_str = interface.get_menu_choice(menu_dict)
#user choose option 2 instead
  elif choice_str == "2":
  ```
By incorporating while loop with if and elif conditions, users are able to input different option value after one choice_str has been completed. When they pick 5, it exits out of the whole program and prints(Goodbye). I was still not able to understand how all the codes complemented each other, but I had a slow revelation of why things worked the way I did when I tweaked it. For that, I was very proud :satisfied:.


## Iterating the [second CSV file](https://trinket.io/python3/41e6af6e10) :nerd_face: (Post [professor example](https://trinket.io/python3/d230e0b321)) 
In the second file, I was able to tackle rest of the TO-DO lists, all the way until the optional part:
- Refactor: Make creating the row_dicts_list into a function, and call it :-)
- Feature: Use `get_csv_filename` to let the user select a new file :-)
- Feature: Use the selected filename to create a new `row_dicts_list` :-)
- Test: Ensure user is able to select ischools-messy.csv  :-)
- (Optional) Feature: Adapt program to work as well as possible with ischools-messy.csv

I struggled a lot trying to use "get_csv_filename" function to work and call the neccessary csv file without the Trinket breaking it or misinterpreting it. Even now I partially feel like I partially completed this function, because I had to manually enter call_column() function on certain conditions even though this function should apply as default while "get_csv_filename" applies specifically to choice_str = 4. I had to learn a new built-in function called global to tackle the issue of returning the function. 

```
#defining the function that opens readers with appropriate header for each csv file
def get_csv_filename():
  with open(filename) as file:
    reader = csv.DictReader(file)
    global row_dicts_list #global keyword allows you to modify the variable outside of the current scope
    row_dicts_list = list(reader)
    global headers 
    headers = row_dicts_list[0].keys() # Get the keys from the first row #learned that this code cannot be outside of this function or it will keep calling ischools-clean.csv headers
  
  return headers, row_dicts_list

get_csv_filename()
```

Calling global function allowed me to tackle the function (and the conditions inside) to be returned and called across the entire code when the filename was switched. However, I saw the professor solve this issue with a fewer lines of code in a more efficient manner: 

```
def get_columns_to_print():
  # Let user choose which columns to print, or print them all
  columns = []
  for header in headers:
    selected = interface.input_is_yes(f"Do you want {header} in simplified print view?", default = 'y')
    if selected:
      columns.append(header)
  return columns

columns_to_print = headers
```

Since columns_to_print function connect back to columns and headers, there was no need for additional global function and it connected the overall conditions quite nicely. Another efficient way to code can be seen by the professor when he did the while loop with added choice of 5 being the exit:

```
while True:  
  choice_str = interface.get_menu_choice(menu_dict, prompt_str = ">>>  ")
  
  # Tell user what choice they made
  print(f"You chose {choice_str}:")
  print(menu_dict[choice_str])
```

Instead of having to set a pre-set condition of choosing 5 which could hinder the flexibility of the code, this code relies on choice_str to pick from the interface.get_menu_choice as long as the condition is true. 


## Overall reflection :thought_balloon:
There was a huge emotional and intellectual progress between CSV file 1 and CSV file 2. I was able to come out the end of the assignment feeling more confident and less stressed out (still stressed out, but *much less*). Now that I understand more in-depth of how each function works, I want to spend more time learning about these functions and write them more efficiently like what our professor did. Overall, this was a success in my own ways! :partying_face: 

Thank you for reaching my reflection.
