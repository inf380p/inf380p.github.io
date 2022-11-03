# THE ORIGINAL CODE

In this assignment, we were given a code that presented information on different ischools around the world, and were to add a list of features to the given code over a period of two weeks:

- Feature: Put the interface in a while loop so that the user can do multiple things
- Feature: Create a new main menu option so that user can exit the program
- Refactor: Make selecting of `columns_to_print` a function, and call it
- Feature: Allow user to re-select which columns get printed
- Refactor: Make creating the `row_dicts_list` into a function, and call it
- Feature: Use `get_csv_filename` to let the user select a new file
- Feature: Use the selected filename to create a new `row_dicts_list`
- Optional Feature: Adapt program to work as well as possible with ischools-messy.csv

This task felt, admittedly, daunting at first. There was a main body of code, multiple imported .csv files, and an extra `interface.py` module utilized. In order to combat the initial dread of an overwhelming task, however, I was impressed to find that I instinctively knew to break the code up into smaller, more digestible chunks.

I started by reading through the code carefully, noting commentary left by the original programmer and trying to follow their line of thought in conversation with terms I *did* know. For example, when scrolling through, I noticed that the list of menu options given with `menu_dict =` correlated a set of `if` and `elif` statements, which caused the code to behave differently depending on what option the user chose. I had trouble understanding how `menu_dict=` worked, but I felt comfortable with `if` and `elif` statements.

Original code:

<iframe src="https://trinket.io/embed/python3/df21823a45" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

# PROBLEM SOLVING (WEEK 1)

After reading through the code and attached interface.py and .csv files, I tackled the list of todos in the order of what I felt most comfortable with, rather than the order in which they were listed. Here’s how I tackled them:

### Create a new menu option so that user can exit the program

For this feature, I figured I could add a fifth option to the main menu, and started with visually adding that fifth option *before* bullheading my way through actually making it work. Here’s the new menu:

```
menu_dict = {
  "1" : "Browse rows of data",
  "2" : "Print specific row",
  "3" : "Select columns to print",
  "4" : "Change data file",
  "5" : "Exit"
}
``` 
Since I knew that each menu option corresponded to an `if` or `elif` statement beneath, I knew I could add on another `elif` statement to allow the user to exit. 

I mimicked:

```
if choice_str == "1":
…
```

And wrote:

```
elif choice_str == "5":
  print("")
```

This simply printed a blank space if the user chose the ` "5" : "Exit"` option, and then allowed the program to skip forward to the final line, `print("\nGoodbye")`.

### Put the interface in a while loop so that the user can do multiple things

This task felt more like deciding *where* a `while` loop fit best, rather than *how* to implement it. After testing several locations to implement a `while True:` loop, I realized that I preferred it above `choice_str = interface.get_menu_choice(menu_dict)`, because it brought the user back to the main menu if they were done utilizing an option they had originally chosen. For example, if the user chose to browse rows of data (option 1), but chose not to continue at any given point, the `while True:` loop allowed them to return to the main menu and choose a different option, such as printing specific rows (option 2). This created a slight problem when the user chose the `"5" : "Exit"` option, which I solved in week two (see below).

### Let the user select a new file

For this feature, rather than create a function, I chose to create a new menu that allowed the user to choose which `filename` variable was being opened. Since I was still figuring out how .csv files worked, I decided to mimic the syntax used for the main menu. I created a new variable called `menu_data` that allowed the user to decide which file they wanted to open, and then set the `filename` variable to whichever file they chose:

```
menu_data = input("1 : Select ischool clean data\n2 : Select ischool messy data\nMake a selection")

if menu_data == "1":
  filename = "ischools-clean.csv"
else:
  filename = "ischools-messy.csv"
```
I then kept the file-opening mechanism from the original code, but since the `filename` variable was dependent on user input, `with open(filename) as file:` now opened either `"ischools-clean.csv"` or `"ischools-messy.csv"`:

```
with open(filename) as file:
  reader = csv.DictReader(file)
  row_dicts_list = list(reader)
```
### Make selecting of columns_to_print and row_dicts_list functions

This is where I started to really struggle. My idea was to try to define a function called `columns_to_print()` that asked for an input and then printed columns based on user input. Here’s the original code I tried to write, asking for an input and testing if that input would print an example line:

```
 def columns_to_print():
column_input = input("Type which columns you'd like to print, then press enter:\nA : University\nB : School\nC : Location\nD : Region\nE : Membership")

if column_input == "A":
print("Hello")
elif column_input == "B":
print("B")
elif column_input == "C":
print("C")
elif column_input == "D":
print("D")
elif column_input == "E":
print("E")

columns_to_print_list = [University,School,Location,Region,Membership]
```

I wasn’t able to get anything to print from this feeble attempt, and you can tell from my notes to myself:

```
> lines 64-66 are the problem lines rn … how do I print something the user chose so that they can have the option to revisit later?

> make a while statement here that allows people to continue selecting until they exit??
```

At one point, I tried retreating back to the safe space of creating another menu option for columns, because I knew I had figured out menu options in the first place. I actually tried generating a new .csv file by *manually organizing the data into horizontal strips of columns* under `ischools-clean.csv`, rather than rows. I stopped when I realized that I had spent an hour copy-pasting data and that this behavior completely defeated the purpose of coding in the first place.

** A funny symptom of testing this later was my row selection showing that there were 53 rows to select from, and any row I selected above 25 was nonsensical. Simply deleting the data I had tried to organize solved this problem later, however!

My failures to solve the column and row issues weren’t a complete waste of time, however. It helped me realize that I wanted users to be able to reselect which columns they chose in my final product, likely using a `while` loop, which provided insight that informed later decisions.

Code after week one:

<iframe src="https://trinket.io/embed/python3/34f72e5067" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

# A SECOND TRY (WEEK 2)

During the second week, I used my time implementing knowledge from that week’s class, cleaning up my first week’s code, and debugging small issues related to the original to-do list.

### Put the interface in a while loop so that the user can do multiple things

When putting the interface into a `while True:` loop, there was a problem. If the user chose option 5, “exit,” from the main menu, it brought them back to the main menu rather than simply allowing them to exit the program. This resulted in a repetition of the main menu no matter how many times the user tried to exit, creating a slight softlock. To solve this, I realized that I could replace:

```
  elif choice_str == "5":
    print("")
```
With:

```
  elif choice_str == "5":
    break
```
It was a simple solution, but it allowed the loop to break and the program to print its goodbye statement.

### Make selecting of columns_to_print a function, and call it

The in-class demonstration of creating a function to print columns was particularly enlightening. I had already thought through defining a function similar to `get_columns_to_print():` that went through the header options, but originally was trying to create menu options rather than use code already built in. Instead, I followed the example of using:

```
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
I was proud of myself when in-class I remembered to call the function after our code didn’t work, because I always forget to call the function when coding on my own!

After refactoring and simplifying `columns_to_print` to `columns`, we ended up with:

```
# lets user choose which columns to print
def get_columns_to_print():
  columns = []
  if interface.input_is_yes(f"File '{filename}' has {len(headers)} columns. Select which columns to print?\n", default = "y"):
    for header in headers:
      selected = interface.input_is_yes(f"Do you want {header} in simplified print view?", default = 'y')
      if selected:
        columns.append(header)
  
  else:
    print("All columns will be printed")
    columns = headers
    
  return columns
    
columns = get_columns_to_print()
```
I had a few error messages still, and made the mistake of going through the rest of the code and changing all `columns_to_print` to `columns`. This generated an error, because the `columns` variable was also being used in the main menu `2: Print specific row`. I fixed this, by changing the original:

```
    for row in row_dicts_list[first_row_int:]:
      for key in columns_to_print:
        print(row[key])
      if interface.input_is_yes("Contine?", default = 'y'):
        continue
      else: 
        break
```
To:
```
    for row in row_dicts_list[first_row_int:]:
      for key in headers:
        print(row[key])
      if interface.input_is_yes("Continue?", default = 'y'):
        continue
      else: 
        break
```
This generated another problem: if the user went back and re-choose from the main menu, since `columns_to_print` was already defined at the beginning of the code, it was not included in the `while True` loop. I changed my code back to `for key in columns` instead of `for key in headers` and added `get_columns_to_print()` under the menu option. Finally, I realized that I needed to reset my option under `elif choice_str == ‘3’:` from `get_columns_to_print()` to `columns = get_columns_to_print()`.

** I also had a funny moment when testing this where I couldn’t figure out why my code wasn’t working … see above in week one!

### Allow user to re-select which columns get printed

This was easy after defining `get_columns_to_print()`! All I had to do was call it under `3: Select columns to print`:

```
  elif choice_str == "3":

    get_columns_to_print()

```

Since we are still under an umbrella `while True:` loop, the column choice can now be executed multiple times until the entire program is exited.

### Make creating the row_dicts_list into a function, and call it

I interpreted this task as trying to figure out how to let users change filenames whenever `choice_str == “4”`, and approached it by mimicking choice options refactored earlier in the code. I essentially made `choice_str == “4”` function as a soft `break`, and recreated the filename retrieval from earlier. I think functionally, I solved the issue of allowing a user to rechoose a file, but I did not solve the actual problem of creating a function. In the future, I need to practice refactoring, because I made several attempts of `def get_row_dicts_list():` which broke under ischools-messy.csv.

Code after week two:

<iframe src="https://trinket.io/embed/python3/3428428f9a" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

# CONCLUDING THOUGHTS

I tried to clean up my code while writing it (for example, I changed `print("Goodbye")` at the end to `print("\nGoodbye")`, to make the output have an extra space and be more readable), but it was still sloppy by the time I finished week two of coding. I spent some time at the end fully cleaning up my code, trying to ensure best usability and readability for both users and coders. This said, I realize that code is always a snapshot of where it is currently at---there are always ways to improve!

Looking forward, I would love to experiment with getting the code to function better with ischools-messy.csv. Some ideas I have for implementing this feature is creating code that recognizes certain buzz words as falling into certain categories of each type of data, and sorts said data automatically into something more searchable.

As a side thought, this assignment actually happened to coincide with a coding breakthrough in another class. In my database management course, we began using MySQL, and I was successfully able to sort out a blunder in SQL, a brand new language I had never used before, by juxtaposing basic SQL syntax with the problem-solving skills I had learned with Python. While the fix for my SQL issue was simple, the feeling of victory was unfathomable. I felt validated as a beginner coder, and was able to use that small victory to ground me when I was feeling stuck on my CSV files!

Clean code:

<iframe src="https://trinket.io/embed/python3/166e96c182" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
