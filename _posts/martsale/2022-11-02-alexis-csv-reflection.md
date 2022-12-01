---
layout: post
author: martsale
title: "Alexis's CSV reflection"
---

# CSV Reflection

## Getting started is the hardest part...

Pretty consistently throughout this class, taking the first step to get started has been the hardest part. While I can rationalize that just attempting **something** is better than staring into oblivion for hours, it's still really difficult to take the first step. In this assignment's case, reading all of the "to-do's" was overwhelming me. 

Once I got out of my head, I built in the exit condition because that felt like an easy win to getting the ball rolling on the assignment. Next, I started at the beginning of the list and worked my way down.


## A few challenge areas

I immediately got stuck on the `while` loop. I realized that this could be made as an indefinite loop because I called the exit condition using `break`, but I struggled with defining the while loop to be indefinite. I was searching for values in the code to set it to. After reading the python documentation and reviewing some of the Runestone chapters, I set the loop to `while 1 < 2` to see what happens, and that condition ran successfully. Looking back, I definitely was overthinking how to create an indefinite loop.

Another area that I got stuck on was passing the value of a function into the rest of the code. Even though I put "columns to print" into a function, I was struggling to get it out of the function. After using `print()` to determine what the value was and what was being read, I was able to add `columns_to_print = columns_to_print_func()`, letting this value into the rest of the code.  

My week 1 code is below:
<iframe src="https://trinket.io/embed/python3/f12026706b" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe> 


## Revisiting the code

After coming back to the code this week, I realized that I had misinterpreted part of the instructions. While I technically completed all of the requests in the "to-dos", I had not put the capabilities into the while loop choice. Instead, every time the loop ran, the user had to set it up again.
```
while 1 < 2:
  columns_to_print = columns_to_print_func()
  choice_str = interface.get_menu_choice(menu_dict)
```
I initially switched `columns_to_print = columns_to_print_func()` and `filename = interface.get_csv_filename()` into their respective menu items. However, I got an error that this did not exist to be called first. So I have this code duplicated before the while loop as setup and in the while loop. 

Another challenge I faced was that in the code, `filename` was switching in this line: `if interface.input_is_yes(f"File '{filename}' has {len(headers)} columns. Select which columns to print?\n", default = "y"):`, but the number of columns still reflected whatever file the user chose in setup. After carefully tracing how the functions interact with each other and adding a `print()` statement, I realized that I was getting the csv name, but not importing it or determining the new headers. After including the following code in choice 4, the program ran as expected.
```
filename = interface.get_csv_filename()
import_csv_function()
row_dicts_list = import_csv_function()
headers = row_dicts_list[0].keys()
```

Here is my final week 2 code:
<iframe src="https://trinket.io/embed/python3/f2323d56f7" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Going forward 

The next step I would take in refactoring this code is trying to include
```
filename = interface.get_csv_filename()
import_csv_function()
row_dicts_list = import_csv_function()
headers = row_dicts_list[0].keys()
```
only once in the code instead of at the start and in the while loop. I also would move forward to write a function that would clean up the `schools-messy.csv` file. 


## My best debugging skills for me, so far

So far, I've found that `print()` has been my best tool to understand what python is doing. Taking the time to trace variables and functions call back through the code has also been really valuable. I find that when I explain the code out loud, I can better understand what is happening and what I want to happen.
