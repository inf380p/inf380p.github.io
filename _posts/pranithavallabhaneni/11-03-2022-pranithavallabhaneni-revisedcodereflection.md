---
layout: post
author: pranithavallabhaneni
title : "Pranitha's revised code reflection"
---
To begin, I tried to attempt the professor's **todo** tasks list one after the other. I started with putting the interface in a while loop.
Usually program will only run once. But here, to run it multiple times I have given a **while of true** function as shown below to get the
continuous loop.

```
while (True):
  choice_str = interface.get_menu_choice(menu_dict)
  # Tell user what choice they made
  print("You chose {choice_str}:")
  print(menu_dict[choice_str])
  ```
  The next task I undertook is to create a new menu option so that user can exit program. So if a user wants to exit the program, at any point of time, I have added an **exit** function. I remember professor mentioning in the class that we can use exit function in the running program
  to exit from the flow.
  Although straightforward, I realised that it is important to sequence and closing commands in the correct way so that my print statement gets executed before the program is exited. Here is the bit in my program where I have used this exit function.
  
  ```
  elif choice_str == "5":
    print("Goodbye")
    exit()
```

Another task I wanted to reflect on is the 'selection of columns_to_print' a function and then call it. After reading this task I remembered my turtle program where I gave directions
to the turtle to move forward, backward and then repeated the process in the initial classes. But in the later classes instead of repeating same thing, I placed all my code lines under one
**def** function. When that function is called, it executes the entire procedure. I followed the same methodology here. Unfortunately, I got the following error - 
'expected functionality is unable to print because "Columns_to_print" is already used somewhere in the program and it was assigned only to use once in the program".
So when I tried to call the function, new values couldn't be overriden. Then I started debugging my code by placing it in the print statement, then I got another error - 'columns_to_print is 
out of the scope of function'. The first thing that came into my mind is I have to first clear the existing function which is meant for a one time use only.
Then I added the following function - **columns.print.clear** . Now when I ran the program I didn't get any error this time *yayyy!!* . After multiple iterations and encountering different types of errors
each time, I tried and tried and tried and finally got it!! You can see a part of my code below:

```
columns_to_print = []
def cols_to_print():
  columns_to_print.clear()
if interface.input_is_yes(f"File '{filename}' has {len(headers)} columns. Select which columns to print?\n", default = "y"):
  for header in headers:
    selected = interface.input_is_yes(f"Do you want {header} in simplified print view?", default = 'y')
    if selected:
      columns_to_print.append(header)
else:
  print("All columns will be printed")
  columns_to_print = headers
```

I have also written the code that allows the user to re-select which columns to print and I've also created 'row_dicts_list' into a function and called it.
You can see my final code in the below embedded link.

<iframe src="https://trinket.io/embed/python3/dcb0022fc6" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

As mentioned in the 'starting problem solving tool kit' by professor, I examined my code, read it back to mydelf, and checked that it said what I meant to say.
It took me a lot of time to get this final output without any errors. The textbook helped me a lot during this program.

**Practice is key!**

