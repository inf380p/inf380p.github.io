---
layout: post
author: hannahmoutran
title: "CSV Files Hannah Moutran"
---

#CSV Files 1 Reflection

Working with CSV files seems very difficult to me, and at the end of the assignment, I still don’t feel a sense of comfort with the subject matter.  It did help to read through everything carefully, including the other modules, and to pull from other exercises we have done.  There were also most definitely things I just had to look up, for instance the `.keys` method, which if I understand it correctly will pull the headers of a dictionary into a list.  Still, this whole exercise was very frustrating at times.  It took me time to figure out what I was meant to do, and then it took a long time to figure what was broken once I had done it.  For example, making `get_row_dicts_list` into a function seemed to throw a wrench into the whole program.  

Originally, I had it like this: 
```python
row_dicts_list = []
def get_row_dicts_list(filename):
  with open(filename) as file:
    reader = csv.DictReader(file)
    row_dicts_list = list(reader)
```
The problem with that was, `row_dicts_list` was used as a variable in various places in the rest of the code, so I had to first off create a `return` for the function, and then actually create the variable using the function.  

```python

def get_row_dicts_list(filename):
  with open(filename) as file:
    reader = csv.DictReader(file)
    row_dicts_list = list(reader)
    return row_dicts_list

row_dicts_list = get_row_dicts_list(filename)
```
A similar thing happened when I changed `elif choice_str == “4”:` so that it would take `get_csv_filename` from the interface module to let the user change the file.  It was written already, just had to make sure that it is pulled in from the other module, using the old Clicky Turtlehack code for an example.  Should be easy?  No, because then the `row_dicts_list` variable had to be updated with the `get_row_dicts_list` function using the new filename, the `headers` had to be re-created based off of that, and the `columns_to_print` also had to be re-drawn.  

In the end, it looked like this: 

```python
elif choice_str == "4":
      filename=get_csv_filename()
      row_dicts_list = get_row_dicts_list(filename)
      headers = row_dicts_list[0].keys()
      columns_to_print = get_columns_to_print()
```

What are the lessons?  Perhaps to make sure that you understand something before you change it.  To me, this code reads as complicated, but I know that it must get much, much more so, which would make it harder to keep track of what you’ve changed and where it might have gone wrong.  I did use `print` a couple of times to try to help me figure things out, and carefully read through error messages.  At the end, I’ve gotten things checked off the list, but I still feel like I need more work on data processing.  

The Trinkets from before and after class are below.  

Final CSV Files 1 Trinket: <iframe src="https://trinket.io/embed/python3/8f70e6beb2" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Before Class CSV Files 1 Trinket: <iframe src="https://trinket.io/embed/python3/56c8f4befb" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
