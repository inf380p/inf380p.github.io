---
layout: post
author: Prakash-sa
title: "Prakash-sa's CSV Files and Reflection"
---


## Reflection

- **I learn to use the CSV files with the python code. I combined all the knowledge that I learned from the classes like dictionary, function, import code from different file to simplfy it, write neat and understandable code.**


- I utilized my understanding of writing code in different file and import it to make it more understandable and systamatic. I have coded the get_valid_col_int in the interface.py by understanding the function get_valid_row_int.
   ```
   def get_vaild_col_int(cols_list):
      """
      Gets a valid index given a `col_list`.
      Note: return value will be a list index, so the first col is index 0.
      """
      # Find highest col number
      maxcol_int = len(cols_list)

      while True:
        print(f"Enter a col number from 1 to {maxcol_int}")
        try:
          col_int = int(input("Col to view:    "))
        except:
          print("Please enter an integer")
          continue # User must start over

        if col_int < 1 or col_int > maxcol_int:
          print("Not a valid col number")
          continue # Prompt will repeat the requirments

        col_index = col_int - 1
        return col_index

     ```
   
   
- I used the knowledge of reading the csv file from get_row_dicts_list() function to implement the Select columns to print menu. The base of the function is the same as get_row_dics_list, I have just modified the function whether we want to print it for random column or for selected columns.

    ```
    def get_row_dicts_list():
      with open(filename) as file:
        reader = csv.DictReader(file)
        row_dicts_list = list(reader)
      return row_dicts_list
     ```


- I have encountered the problem of calling the variable before declaration during the assignment completion. I forgot to declare the columns list in the func_columns_to_print function and declared it elsewhere. After going through the code I realized that I have to declared it in the function as a local variable and return it.
    ```
    def func_columns_to_print():
      # Let user choose which columns to print, or print them all
      columns=[]
      if interface.input_is_yes(f"File '{filename}' has {len(headers)} columns. Select which columns to print?\n", default = "y"):
        for header in headers:
          selected = interface.input_is_yes(f"Do you want {header} in simplified print view?", default = 'y')
          if selected:
            columns.append(header)
      else:
        print("All columns will be printed")
        columns = headers

      return columns
    ```


- _** I have learned a alot from this challenge, face many bugs and solved it. I got good hands on experience on the functions, dictionary and third party library like CSV, random.**_

## Final CSV Files

<iframe src="https://trinket.io/embed/python3/fcb3dd4af5" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Before Class CSV Files

<iframe src="https://trinket.io/embed/python3/df6a462f62" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
