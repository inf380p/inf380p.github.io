---
layout: post
author: Eros11on
title: "Zheng Zhong's CSV Files and Reflection"
---


## Reflection
- **It was very interesting to work with the CSV files. I did encounter many difficulties while writing it. However,I learned a lot of useful knowledge when I  solved these problems.** 🤩🤩🤩

1. First, I have a better understanding of dictionariy in Python. From the following code, I learned that a Python dictionary is a mutable container model that can store objects of any type. A dictionary is composed of a series of key-value pairs. And we can get key or values form its key-value pair.
   ```
   headers = row_dicts_list[0].keys()
   ```
   
   
2. Second, in the process of creating the `row_dicts_list` into a function, I made a mistake. I just created the function and didn't call it. So I had to call the `get_row_dicts_list` function again in the following functions where the `row_dicts_list` is needed. It made the whole process very troublesome. To simplify it, I defined a new variable to store the return value of the `get_row_dicts_list` function so that I don't have to call the function again and again.
    ```
    def get_row_dicts_list():
      with open(filename) as file:
        reader = csv.DictReader(file)
        row_dicts_list = list(reader)
      return row_dicts_list
    row_dicts_list = get_row_dicts_list()
     ```


3. Third, I think the most difficult part of the whole CSV files is printing column. I want to achieve the same function as the row. Output a random column and output a specified column. So I had to rewrite the `row_dicts_list` to read the columns. The specific code is as follows.

    ```
    elif choice_str == "3":
      columns_to_print = get_columns_to_print()
      if interface.input_is_yes("Print random col?", default = 'y'):
        col = random.choice(columns_to_print) # get the random title of column
        with open(filename) as file:
          reader = csv.DictReader(file) 
          column = [row[col] for row in reader] # read random column from csv file
        print(column)
      else:
        col_int = interface.get_vaild_col_int(columns_to_print) # recall the function `get_vaild_col_int` from interface and get the range of column
        col = columns_to_print[col_int] # get the specific title of column
        with open(filename) as file:
          reader = csv.DictReader(file) 
          column = [row[col] for row in reader] # read specific column from csv file
        print(column)
    ```
    
       


- _**I think this program is a big challenge for me and I had a better understanding of the concept of function and dictionary. 💪💪💪**_

## Final CSV Files

<iframe src="https://trinket.io/embed/python3/1ea52f2473" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Before Class CSV Files

<iframe src="https://trinket.io/embed/python3/46ae419357" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
<div align=center><img width=300 hight=300 src="https://www.utexas.edu/sites/all/themes/utexas/img/general/logo.svg"/></div>
