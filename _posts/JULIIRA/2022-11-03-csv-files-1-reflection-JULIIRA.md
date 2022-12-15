---
layout: post
author: JULIIRA
title: "CSV files 1 Reflection"
---

While I was working on this code, I noticed the progress I had made so far and was proud of myself. 
I am finally getting the hang of loops, indentations and functions. However, I still have room for improvement as I faced
the following issues in the first code:


<iframe src="https://trinket.io/embed/python3/56c2ee200d" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Most of the issues were so simple that when I finally found the solution, I had to take a break to cope. Here are some of the major
issues I faced:

```
row_dicts_lists(reader)

```
On line 20, I got NameError because I put lists instead of list 
and then I had more issues with line 20 again because I forgot to put list after row_dicts.

Another issue I faced was:

```

print("You chose {choice_str}:")

```
When I figured out the solution, I got very angry and sat down for a few minutes to calm down. 
The solution was so simple and all I had to do was include a f before you chose.

Here's another issue I had regarding indentation:

```

elif choice_str == "2":

```

I keep getting SyntaxError: Invalid syntax for this line of code and for the life of me, I couldn't understand why
until I googled it and found another way to solve this issue. The online forum suggests putting a # on each line of code until I
found the root of problem and then I realized that I had to indent all of the choice_str conditional statements properly, otherwise
I wouldn't be able to run the code. It literally took me two days to fix this issue and it's kind of embarrassing, haha. 
But this very frustrating situation taught me the importance of indentation and how to fix this issue quickly each time I faced it. 

Now, I will go over my lightbulb moments. This is my second code and the revision of CSV files 1: 


<iframe src="https://trinket.io/embed/python3/a8c22f1d7a" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


Because I wasted so much time trying to figure out how to solve the elif choice_str issues, I was only able to complete three items on
the To-Do list and even then, I'm not sure if I did it properly (yikes!). I was able to put the interface in a loop and create a new menu
that allows user to exit the code. 

This code allows user to exit the code and to stop the code from running:

```
menu_dict = {
  "1" : "Browse rows of data",
  "2" : "Print specific row",
  "3" : "Select columns to print",
  "4" : "Change data file", 
  "5" : "Exit"
}

elif choice_str == "5":
    print("Goodbye")
    break

```

Also, I almost succeeded in changing the file data,
but I couldn't get the file data from ischools-messy.csv to show up when users did change the files. I couldn't figure it out in time. 

```

elif choice_str == "4":
    get_csv_filename()
    
    with open(filename) as file:
      reader = csv.DictReader(file)

def get_csv_filename():
  """
  Prints a list of CSVs visible to Python and returns the filename string
  the user selects from the list.
  """
  new_filename_str = ""
  csvs_list = glob.glob(r"*.csv")
  while new_filename_str not in csvs_list:
    print("Available CSV files:")
    for i, filename in enumerate(csvs_list, start = 1):
      print(f"{i} - {filename}")

    try:
      filenum = int(input(f"Enter a number between 1 and {i}:   "))
      new_filename_str = csvs_list[filenum-1]
      print("Chosen CSV file:",new_filename_str, end="\n\n")
    except:
      print("Try again.")
  return new_filename_str

```

To make this part of the code work, I had to import glob and include the function of get_csv_filename.
 
At one point, I created the function and was able to get users to select their columns but I think as I was working on other parts
of the code, I did something to take that option away (I'm still unsure of what I did). 

```
def print_columns() : 
  columns_to_print = []
  if interface.input_is_yes(f"File '{filename}' has {len(headers)} columns. Select which columns to print?\n", default = "y"):
    for header in headers:
      selected = interface.input_is_yes(f"Do you want {header} in simplified print view?", default = 'y')
      if selected:
        columns_to_print.append(header)
  else:
    print("All columns will be printed")
    columns_to_print = headers
  
  return columns_to_print

columns_to_print = print_columns()

```
I was able to create a loop for this code too (thanks to last week's lecture):

```
while True:
  choice_str = interface.get_menu_choice(menu_dict, prompt_str = ">>>")
    
  print(f"You chose {choice_str}:")
  print(menu_dict[choice_str])
      
  if choice_str == "1":
    if interface.input_is_yes("Start from row one?", default = 'n'):
      first_row_int = 0
    else:
      first_row_int = interface.get_valid_row_int(row_dicts_list)
 
    for row in row_dicts_list[first_row_int:]:
      for key in columns_to_print:
        print(row[key])
      if interface.input_is_yes("Contine?", default = 'y'):
        continue
      else: 
        break
  elif choice_str == "2":
    if interface.input_is_yes("Print random row?", default = 'y'):
      row = random.choice(row_dicts_list)
      
      for key in columns_to_print:
        print(row[key])
    else:
      row_int = interface.get_valid_row_int(row_dicts_list)
      row = row_dicts_list[row_int]
      
      for key in columns_to_print:
        print(row[key])
  elif choice_str == "3":
      columns_to_print = print_columns()
  elif choice_str == "4":
    get_csv_filename()
    
    with open(filename) as file:
      reader = csv.DictReader(file)

  elif choice_str == "5":
    print("Goodbye")
    break
  ```
  I learned a lot from this exercise and I am confident that I will do better in the next one.
