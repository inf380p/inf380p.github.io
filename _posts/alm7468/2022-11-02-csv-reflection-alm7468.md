---
layout: post
author: alm7468
title: "April's CSV Exercise Reflection"
---
## Round 1
I had a mixed level of success during my first attempt at editing the csv code. Something that ended up causing issues was that I did not complete the tasks in order. Instead, I approached the tasks that I felt I could accomplish and as a result it complicated other tasks. I will explain my approach or thought process for each task during Round 1, then I will try starting over with the code we edited together in class to see if I can apply the functioning bits of code from Round 1.
> Feature: Put the interface in a while loop so that the user can do multiple things.

I'm so glad that Elliott clarified that interface was a general term here and not interface.py because I spent a while looking through the module for a place to add a loop. I ended up skipping this step while noting:
I’m not 100% sure what the goal here is but I think we want to be able to enter multiple menu prompt numbers in one input attempt. I went to interface.py, found `get_menu_choice()`. But I’m not sure where in the function a while loop would be helpful? 
During Class: Elliott added `while True:` on main.py which applies to everything after the user makes a choice.

>Feature: Create a new main menu option so that user can exit the program

Added ```"5" : "Exit program"``` to `menu_dict`
Added ```elif choice_str == “5”:``` above `print(“Goodbye”)`
Then I asked myself: Does it really exit though? Must be in loop to use break or exit.
During Class: Indeed, it did need to be in a loop, which was covered in the first task that I had skipped. Elliott added `break` in class. So choice 5 code now reads:
```python
  elif choice_str == "5":
    print("Goodbye")
    break
```

> Refactor: Make selecting of columns_to_print a function, and call it

On `main.py` I set the column related chunk of code as `column_choice()` function and tabbed it over for proper alignment. Then I called it in the response to choice_str == “3”.
```python
# Let user choose which columns to print, or print them all
def column_choice():
# Headers of the CSV are the keys of any row dictionary
# Get the keys from the first row
  headers = row_dicts_list[0].keys()
  columns_to_print = []
  if interface.input_is_yes(f"File '{filename}' has {len(headers)} columns. Select which columns to print?\n", default = "y"):
    for header in headers:
      selected = interface.input_is_yes(f"Do you want {header} in simplified print view?", default = 'y')
      if selected:
        columns_to_print.append(header)
  else:
    print("All columns will be printed")
    columns_to_print = headers
```
During class we made changes to this code, the result is much cleaner (_see code below_). We pulled the header definition out of the `column_choice()` function as well. This change allows code side the function to access the definition.
```python
# Let user choose which columns to print, or print them all
def column_choice():
  columns= []
  for header in headers:
    selected = interface.input_is_yes(f"Do you want {header} in simplified print view?", default = 'y')
    if selected:
      columns.append(header)
      
  return columns

columns_to_print = headers
```

> Feature: Allow user to re-select which columns get printed

I felt like I did not completely understand when this would be executed? at anytime? was it a segway back to the Main Menu? I did not attempt this.

> Test: Ensure program uses new selected columns

An after-step to above. I would just test this by running the code, choosing one column, then entering a new number and seeing if I got an error, wrong information, or the correct result.

> Refactor: Make creating the row_dicts_list into a function, and call it

I skipped to: Use the selected filename to create a new `row_dicts_list` and that portion is discussed later.

> Feature: Use `get_csv_filename` to let the user select a new file

I commented out the defaulted filename and wrote a user input request for the filename then named it `new_filename_str` so that the file remains accessible by exsiting code which uses the name `new_filename_str`. (_see code below_)
```python
#filename = "ischools-clean.csv"
csv_name = input("Enter the file name you would like to open:")
new_filename_str = str(csv_name)
```
 I specified how to handle an invalid user input which will reroute to `get_csv_filename()` in interface.py. The user would then be presented with a menu of available csv files:
```python
# if csv_name is invalid produce list of options
if csv_name != "ischools-clean.csv" and "ischools-messy.csv":
  interface.get_csv_filename()
# if file is valid continue
else:
  pass
 ```
 This change caused problems, the program reverted to the user input as a string even after `interface.get_csv_filename()` was executed which returns a new `new_filename_str`.

> Feature: Use the selected filename to create a new `row_dicts_list`

I created a function called `row_dicts_list()` and applied it to the existing code that opened a file, read it, and produced a row list. I thought that if I changed the object to be opened, to the new term `new_filename_str` that this would create the desired function. I was very wrong and still don't know exactly what needs to happen. The `row_dicts_list()` code produces this error: 
`with open(new_filename_str) as file:`
`NameError: name 'new_filename_str' is not defined`
```python
#turn row_dicts_list into a function
def row_dicts_list():
  #Get a list of dictionaries from CSV file
  with open(new_filename_str) as file:
    reader = csv.DictReader(file)
    row_dicts_list = list(reader)
  return row_dicts_list
  ```
 If I create a function to get the user input, can I return `new_filename_str` to use later?
 answer: it doesn't make a impact on the errors.
  

> Test: Ensure user is able to select ischools-messy.csv (Note: program will not work in the same way; that's fine)

When my code was less edited/broken, I was able to open both files through user input (_a temporary success_)
# Round 1 End Point (it's busted)
<iframe src="https://trinket.io/embed/python3/b479bb9e3f" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Round 2
I have been tinkering with the code as I have been writing this reflection, no big break throughs, however, I have been learning through by eliminating the unsuccessful routes. There is a lot of what-if moments that generally end in an error, and then I look into why the error occured. Because there are differences bewteen the Trinket above, and my starting point today, here is Round 2 starting point Trinket.
<iframe src="https://trinket.io/embed/python3/61b8356ad6" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

I'm just constantly running into issues around defning `row_dicts_list` and `new_filename_str`
I'm going to try to create a `row_dicts_list` starting with a copy of Elliott's code from class and see if I have better luck since this version will be less processed.
Update: No progress. There is something about defining and calling functions that I am not doing correctly.
I am getting the same errors even without using user input for file choice.
```python
def get_row_dicts_list():
  with open(filename) as file:
    reader = csv.DictReader(file)
    row_dicts_list = list(reader)
  return row_dicts_list
  
get_row_dicts_list()
```
I thought the above code says, open the file, read it, create a list from that reading, call it `row_dicts_list`, and then remember what that list is so I can use it later. I even tried confirming that `row_dicts_list` is a list by setting it equal to [] at the beginning of the function, nothing changed. I got this error:
`Traceback (most recent call last):`
  `File "/tmp/sessions/e283df6c23eae167/main.py", line 49, in <module>`
    `headers = row_dicts_list[0].keys()`
`NameError: name 'row_dicts_list' is not defined.` 
`Did you mean: 'get_row_dicts_list'?`

I'll have to be done for today because I've spent hours on this with no actual progress.
# (next day)
Ok it's my last oppurtunity to give this a shot.  
After playing around a bit, I feel like I just don't know how to take invalid user input, navigate to interface.py and then return the new file name to main.py. I bet I'm over thinking it but that's where I am getting stuck.\nI'm going to comment out the user input part for now.  
After looking at the formatting of the columns section we edited in class, I am going to try to match the last line with `row_dicts_list = get_row_dicts_list()`  
While testing each menu option, I noticed I had not asked the columns to print as a response to Menu choice 3, I tried adding it but it's just printing the headers. I just copy pasted (sue me.) everything from the `get_row_list()` and changed the term row out for column. I'm running into the same issue in main.py where I struggle to use information from interface.py in main.py.

# Round 2 code
<iframe src="https://trinket.io/embed/python3/61b8356ad6" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>






