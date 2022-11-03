---
layout: post
author: JohnCBMeyer
title: "John's CSV Reflection"
---

# Refactoring other people's code sucks.
For me, looking at someone else's code is always an exercise in understanding
how someone else thinks, which is almost always a bit frustrating. Even when looking
at code written by someone with objectively more knowledge and experience than me,
like the professor, can lead to a lot of "Why the hell did you do it that way?"

The first thought I had when looking at the CSV code was "Why would you hard code
the file name?" The answer is obviously "Because this is an exercise in refactoring,"
but this early confusion stuck with me while working through the rest of the code.
I have come to realize that refactoring is definitely a weak point of mine, so this
helped me get some practice understanding another way of structuring a solution.

# Looping control flow gives me problems.
I managed to set up the `while` loop before we discussed it last week, but that
was mostly by luck. I just hoped that putting `while True:` at the beginning would
make everything work correctly, and it more or less did. The only thing I changed
intentionally, at least at first, was moving the final `print` statement out of 
the loop.

```python
while True:  
  choice_str = interface.get_menu_choice(menu_dict)
  
  # Tell user what choice they made
  print(f"You chose {choice_str}:")
  print(menu_dict[choice_str])
  
  # Do what they asked. 
  # Note: we have to manually keep track of what choice should do what,
  # which we do by ensuring the strings we compate `choice_str` with 
  # match up to the keys in menu_dict.
  if choice_str == "1":
    # Browse rows
    # User can start from one or pick their own starting row
    if interface.input_is_yes("Start from row one?", default = 'y'):
      # First row in the list is at index 0
      first_row_int = 0
    else:
      first_row_int = interface.get_valid_row_int(row_dicts_list)
  
    # Loop through the list of row dictionaries, starting at the selected first row.
    for row in row_dicts_list[first_row_int:]:
      for key in columns_to_print:
        print(row[key])
      if interface.input_is_yes("Contine?", default = 'y'):
        continue
      else: 
        break
  elif choice_str == "2":
    # Print specific rows
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
    columns_to_print = get_columns_to_print()
    
  elif choice_str == "4":
      filename = interface.get_csv_filename()
      row_dicts_list = get_row_dicts_list(filename)
      header = row_dicts_list[0].keys()
      
  elif choice_str == "5":
    break
  
print("Goodbye")
```

This is really the first time I've had to make a menu work with a `while` loop.
I usually just use `for` loops when I need to iterate, and in my usual work, there's
never really a need for an indefinite loop. The only other time I've tried to create
something like this was in the turtle hack assignment, and every time I implemented
the loop, the program crashed. I think the issue there was trying to use listener
functions in the `while` loop instead of explicitly looking for user input, like here.

```python
choice_str = interface.get_menu_choice(menu_dict)
```

I think I'll go back and try this kind of input instead of the screen listeners
in the turtle hack. 

# Return statements are unintuitive.
The next problem I had was with `return` statements. I'm still getting used to 
scope in Python, so I keep forgetting that assigning something in a function doesn't
assign it in the global environment. So, once I realized that a function I was
creating wasn't assigning a variable like I wanted, I realized that I needed a 
`return` statement to get the value out of the function. For example, here:

```python
# Let user choose which columns to print, or print them all
def get_columns_to_print():
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

So, I added a return statement to get the value of `columns_to_print`, like this:

```python
# Let user choose which columns to print, or print them all
def get_columns_to_print():
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
```

And I assumed that was problem solved. Until the code still wouldn't work. That's
when I finally realized that I needed to assign that value to a variable to make 
it available. 

```python
# Let user choose which columns to print, or print them all
def get_columns_to_print():
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

columns_to_print = get_columns_to_print()
```

Yeah, were I writing this from scratch, I would probably pick different variable
names to confuse myself less.

# Rerunning stuff from outside the loop.
The last problem I had was getting the code to work after changing files. I thought
everything necessary was in the `while` loop, but then I realized that some of the
key variables (like `row_dicts_list`) were getting created outside the loop. I 
thought about just including them in the loop, but that seemed a bit lazy and would
keep reassigning things like `menu_dict` every loop. I don't think it would matter
much here, but that seems like the kind of thing that could really affect performance
in bigger programs. So, I just added the functions I had created earlier after
choosing a new filename:

```python
elif choice_str == "4":
      filename = interface.get_csv_filename()
      row_dicts_list = get_row_dicts_list(filename)
      header = row_dicts_list[0].keys()
```

This got everything to work basically as expected. I didn't manage to refine the
code to work better with the messy file, but I believe I managed all of the TODO
items.

Here's the full program:
<iframe src="https://trinket.io/embed/python3/a4b9c22c1f" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

EDIT: I forgot to include that I apparently didn't save my original file. I thought I had saved it last week, but I was unable to find it anywhere. This reflection and the final code have been created mostly from my memory of the original.
