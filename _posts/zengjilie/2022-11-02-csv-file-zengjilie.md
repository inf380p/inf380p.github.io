---
layout: post
author: zengjilie
title: "Jilie's CSV Files and Reflection"
---

## Goal
I want to implement as many features as possible. But first, I need to prioritize them according to their technical difficulties, then start with the easiest, and work my way up to the hardest.

## Code (Before/After)
**After**
<iframe src="https://trinket.io/embed/python/a50b40ad2c" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


**Before**
<iframe src="https://trinket.io/embed/python3/df6a462f62" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Things I've learned

* I learned how to use python library `glob` to get all the files  within the same directory based on their extensions.

```python
import glob

csvs_list = glob.glob(r"*.csv")
```

* I learned how to use python "f-string" to print variables that are outside the quotation mark

```python
for i, filename in enumerate(csvs_list, start = 1):
    print(f"{i} - {filename}")
```

* I learned how to open a csv file using `with __ open __` keywords

```python
def get_row_dicts_list():
    # Get a list of dictionaries from CSV file
    with open(filename) as file:
        reader = csv.DictReader(file)
        row_dicts_list = list(reader)
    return row_dicts_list
```

## Setbacks
I put the `while` loop in the wrong place at first. This makes my code stuck at 
"choice 1" if I choose "option 1". It won't jump out of the for loop because the value of choice_str is fixed to "1".

```python
while True:
    if choice_str == "1":
        #some code
    elif choice_str == "2":
        #some code
    elif choice_str == "3":
        #some code
    elif choice_str == "4":
        #some code
    elif choice_str == "5":
        #some code
```

Then, I tried to put the `while` loop a little above, and it magically worked!

```python
while True:
  
  filename=interface.get_csv_filename()
  
  # Headers of the CSV are the keys of any row dictionary
  # Get the keys from the first row
  row_dicts_list = get_row_dicts_list()
  headers = row_dicts_list[0].keys()
    ...
```
