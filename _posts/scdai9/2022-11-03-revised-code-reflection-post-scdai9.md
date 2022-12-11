---
layout: post
author: scdai9
title: Shih-Chieh's Revised Code Reflection
---

### First attempt

Here is my first version of code for CSV Explorer.
<iframe src="https://trinket.io/embed/python/ab202afb29" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Since the configuration change on trinket, I can not directly remix my code from the course website to the trinket as usual. I found that I can create a trinket with Python 2, and I implemtented the first two features of the TODOs list. However, when I ran the program, I found that some errors poped up. It showed that there was a syntax error in my code. 

```
if interface.input_is_yes(f"File '{filename}' has {len(headers)} columns. Select which columns to print?\n", default = "y"):
  for header in headers:
    selected = interface.input_is_yes(f"Do you want {header} in simplified print view?", default = 'y')
    if selected:
      columns_to_print.append(header)
else:
  print("All columns will be printed")
  columns_to_print = headers
```

I then realized that Python2 did not support `f string`. That is what I learned from my first attempt for the CSV Explorer. The completed code from the course writing by Professor can be found here: https://trinket.io/python3/fd1d62d576 


### My second attempt
Here is the second version of my CSV Explorer.

<iframe src="https://trinket.io/embed/python3/88a8d8c5b7" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Here is the link: https://trinket.io/python3/88a8d8c5b7

In my second attempt, I tried to finish the TODOs. 
```
def get_csv_filename(filename):
  # Let user select which file to print. Default value is ischools-clean.csv. 
  
  # Get a list of dictionaries from CSV file
  with open(filename) as file:
    reader = csv.DictReader(file)
    row_dicts_list = list(reader)
  return row_dicts_list
```
I created the function to get the CSV file with the assigned file name. 

Therefore, the user can change the data file now.
```
elif choice_str == "4":
    print("Please select the filename you want to change.")
    print("1: ischools-clean.csv")
    file_selected = input("2: ischools-messy.csv")
    if file_selected == "1":
      row_dicts_list = get_csv_filename("ischools-clean.csv")
      print("You selected ischools-clean.csv")
    elif file_selected == "2":
      row_dicts_list = get_csv_filename("ischools-messy.csv")
      print("You selected ischools-messy.csv")
    else:
      print("Invalied selection")
```

I asked the user to select the file name they desired. Also, if they type a number that is not in the list, the program will tell them "Invalid Selection". 


### Overall Reflection
I found that after the Professor explained the code during the course, it was easier for me to implement the function. Therefore, I learned from my second attempt that it would be easier to work with other people's code if I could read it thoroughly and understand it first.
