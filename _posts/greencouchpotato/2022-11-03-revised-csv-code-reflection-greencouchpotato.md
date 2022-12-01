---
layout: post
author: greencouchpotato
title: Greencouchpotato's Revised Code Reflection
---

##1st code reflection

When I first started reading through the code, I was extremely confused. I had come across new terms like dictionaries and apart from the interactive textbook's exercises, this is my first time writing (modifying) code which contained 2 CSV files.

I started with the first task which was **'#Feature: Put the interface in a while loop so that the user can do multiple things'**. I was confused with this prompt since I tried putting the 'interface.py' in a while loop which gave out the following error - "AttributeError: module 'interface' has no attribute 'py'". I tried to blindly put the .py file in a while loop without attempting to understand the logic behind this action. Later I assumed that it must've been a mistake with the task details and I put one of the CSV files in a while loop intending for the code to read and print out the number of lines in the file. Here was the code I've written:
```
filename = "ischools-clean.csv"
count = 0
fhand = open("ischools-clean.csv")
for line in fhand: 
  count = count + 1
  while (True):
    print ("This is the " + str (count) + " line in the 'ischools-clean.csv' file.")
    break
```
I intended  code to read and give out a single number, but instead the code printed out a sentence for each of the lines. So if the file had 22 lines, it printed the string sentence 25 times'. Although I could determine the number of lines from it, it wasn't an efficient way of writing code. Ultimately in the next class I realised that that wasn't the required task at all.

Understanding the question correctly this time, I read the while loop in the interface.py tab and called the below function:
```
filename = interface.get_csv_filename()
```

This command called the below function lines - 
```
def get_csv_filename():
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
  Now I understood how to call the function which contains the while loop.
  
##2nd code reflection
  
The next task that I attempted was -  **'# - Feature: Use `get_csv_filename` to let the user select a new file'**
For this task I used the input function to allow the user to enter the name of the file that they wanted to call. The good thing here was the input function provided the luxury to the user to add a whole new .csv file or tab and import it into the main.py tab to work with its data. Here is my code:
```
fname = input('Enter the file name: ')
fhand = open(fname)
count = 0
for line in fhand:
  count = count + 1
print('There were', count, 'subject lines in', fname)
```
I found this task to be simple and straightforward since I've used the input function multiple times before, especially in the turtles code. But I wanted a user to further get some meaning out of this. So I've writted the code in such a way that if a user enters the name of their desired file, the program would further mention the number of lines in the csv file and prompt if the user would like to take any further actions on it.

##3rd code reflection

The last bit of code that I would like to talk about is the following task - **'#Added the exit function to the program'**
The exit function although was simple, I encountered the following error - 'File "/tmp/sessions/52cea2d848de64de/main.py", line 29 "5" : "Exit the program"^SyntaxError: invalid syntax'. I've spent a whole night not understanding where I went wrong. I ensured to add the below 2 pieces of code to make the exit function work - 

```
  "5" : "Exit the program" 
  #the above was added in the 'menu_dict = {' list
```

and

```
elif choice_str == "5":
  print("You will now exit the program. Goodbye!")
  exit()
  #this code was added in the Loop through the list of row dictionaries section of the code.
```

I left the program where it was not understanding how there could be an error when I've written everything correctly. When I revisited it in the morning, I then realised that although python said that there was an error in line 29, it was infact in the previous line where I had forgotten to put a comma ','.
Once I added that, the code had started functioning and the error cleared up.

This is my revised code -
<iframe src="https://trinket.io/embed/python3/10e0c26f45" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

This was my original code - 
<iframe src="https://trinket.io/embed/python3/56cc977710" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

>Ruminating. Take some time to think! 

This helped me a lot. Taking a break and revisiting the code the next day helped me see with a clearer mind and made modifying the code a whole lot easier.
