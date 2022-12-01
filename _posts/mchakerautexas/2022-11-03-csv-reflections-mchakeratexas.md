---
layout: post
author: mchakerautexas
title: "Mufaddal's csv reflections"
---

## First Reflection
Last week's assignment was probably the most interesting task I have had to to in this class and it surprised me because it wasn't even about Turtle! Just simple text and data processing. The challenges I came accross and the learning curve I went through while attempting to knock off TODO list items in the code got me engrossed and I didn't realize as time passed!

The first challenge I came accross was the feeling of being overwhelmed, looking at such a large codebase to begin with. The interface.py file had a lot of functionality, and it got very confusing for me. But I gave it a lot of time and made sure to understand how the functions called from the main file worked. This helped my understanding of the code base.

Then, I finally started on the todo tasks. The first task about the interactive menu had me confused(once again!). I did not clearly understand the requirements and had to research online a bit about it. I soon found tons of examples of text based or command line applications that do this all the time. The easiest way to do it was to put everything in a while loop with a True condition (so that it runs forever). This is also called an infinite loop. My code looked something like this:
```python
while True:
	# code
	# menu options
	if (<some condition to exit the loop>):
		break
```

This translated to the following code in my initial submission:
```python
while True:
  choice_str = interface.get_menu_choice(menu_dict)
  
  # Tell user what choice they made
  print(f"You chose {choice_str}:")
  print(menu_dict[choice_str])
  .
  .
  .
  elif choice_str == "0":
    break # if the menu option 0 is selected we exit the loop hence stopping the application.
```

Next, the refactoring tasks like putting columns to print into a function came pretty intuitively to me. I love the concept of wrapping code blocks into functions and parameterizing them, so I got through that one pretty quickly.

Whats interesting is although the next todo task: `Allow user to re-select which columns get printed` seemed quite challenging to me before I did the refactoring, but once I had the refactored function, everything clicked together and I could easily finish this task.

Another issue I faced was about creating a function to return `row_dicts_list` . The code that already existed in the file was such that it was reading a csv file, creating the `row_dicts_list` and also setting the headers variable. If it had just updated row_dicts_list I could easily just return it, but it was changing headers as well!? I was stuck on how to make the function communicate back the caller the new value of headers. This is when I came accross the concept of multiple return values. Apparently python allows you to return not just one, but as many return values as you like. Using this new knowledge, I came up with the following:

```python
def get_row_dicts_list_and_headers(filename):
  # Get a list of dictionaries from CSV file
  with open(filename) as file:
    reader = csv.DictReader(file)
    row_dicts_list = list(reader)
  # Headers of the CSV are the keys of any row dictionary
  # Get the keys from the first row
  headers = row_dicts_list[0].keys()
  
  return row_dicts_list, headers #returning multiple values
```
Having learned(struggled) a lot, I was able to finish all the TODO tasks except for the optional one, before the class.

<iframe src="https://trinket.io/embed/python3/30a73e3c33" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Expanded Reflection
After and during the class, I was trying to crack the problem of making the messy csv file readable. When I opened ischool-messy.csv, my brain could not make sense of anything. It did not follow the comma separated format that a csv file should follow, so I immediately got thinking, if I can't understand what it is if I expect it to follow a certain syntax, so can't the computer! I just needed to do some processing on the file to make sure that it adheres to this format. My plan was to make sure each line represents a row of data, with as many values separated by comma as the ones specified in the first line (header).

So I got to work, and realized that there is a pattern (even in the messiness(?)). There are some unnecessary new lines, each data cell is encapsulated in quotation marks, and I just have to join everything together(ignoring the new lines), but make sure to not interrupt the correct new lines(the ones that separate rows of data). 

I finally came up with the following:

<iframe src="https://trinket.io/embed/python3/e0e2c97927" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
