---
layout: post
author: JamesAthrun
title: "JamesAthrun's CSV and Reflection"
---


## Reflection

- 1. I have learnt how to read a csv file using python. The original python code can only read the first file in the original logic. So I copied the first part of the code to the choice 4 for users to select which file they would like to choose, along with changing the column headers.
   ```
   with open(filename) as file:
      reader = csv.DictReader(file)
      row_dicts_list = list(reader)
      
    headers = row_dicts_list[0].keys()

    # Let user choose which columns to print, or print them all
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


- 2. I have learnt how to use "assert" in python and how to deal with problems in python list data structure. I have defined a new method called get_column_choice to finish the third task. 

    ```
    def get_column_choice(choices_dict, prompt_str = "Make a selection"):

      assert all([isinstance(x, str) for x in choices_dict]), "Keys to choices_dict must be strings"

      # Keys of the dict are the possible choices
      valid_choices_list = list(choices_dict.keys())
      
      print("Column Menu")
      for label, description in choices_dict.items():
        print(f"{label}: {description}")
      
      # Get a user choice
      user_choice = input(prompt_str)
      
      # Check if it's a valid choice. If it is, loop is skipped.
      while user_choice not in valid_choices_list:
        # User's choice was invalid; loop until it is
        print(f"{user_choice} is not a valid selection.")
        user_choice = input(prompt_str)

      #
      return user_choice
     ```


- 3. Since the two files have different column names, I let the system to make a judge which is the current file. After that, the column_dict will change accordingly.
    ```
    if (filename == "ischools-clean.csv"):
      column_dict = {
        "1" : "University",
        "2" : "School/Unit",
        "3" : "Location",
        "4" : "Region",
        "5" : "Membership"
      }
    else:
      column_dict = {
        "1" : "University",
        "2" : "Location",
        "3" : "Membership"
      }
    ```

- The main take-away in this homework is that I have a deep understanding of converting csv to python and the role that list & dictionary has palyed during the whole process. I have also learnt how to use "assert" to check whether the input meets the requirement or not.


## Final CSV Files

<iframe src="https://trinket.io/embed/python3/36c430b806" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Before Class CSV Files

<iframe src="https://trinket.io/embed/python3/4bc84a5b17" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
