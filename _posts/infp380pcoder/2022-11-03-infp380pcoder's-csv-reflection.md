---
layout: post
author: inf380pcoder
title: "Infp380pcoder's CSV 1 and 2 reflection" 
---


This week's assignment was a challenge for me. I still don’t feel like I quite grasp all of the concepts that were in explored in the assignment, but it has become a little more clear after spending more time going through it. I began by attempting to parse through the code and make sense of it. I read through each part of the program, with the comments, and tried to familiarize myself with the program and what each of the components was trying to accomplish. There were a few times, however, that I got overwhelmed and had to utilize the retreat method, coming back to look at the problem with fresh eyes. 

I think the biggest hurtle initially was in trying to understand what the prompts were asking for and then how to execute them correctly. I understood how to add in another choice so that the user could exit the program. I recalled from previous assignments how to give the user multiple input options, such as  giving the user a fifth option `”5” : "Exit"` under `menu_dict =` and I figured out that adding the following code gives the user the option to exit the menu:

```python
elif choice_str == "5":
    print("Goodbye")
 ```
 
After adding in the loop, I realized that it was important to put the `break` after the `print(“Goodbye”)` line because the program needs some way to break out of the loop because, as I found out, if you try to add `break` outside of a loop it results in a syntax error. 

It helped to break down the steps one by one to keep them from being so overwhelming. I still had some trouble coming up with a method for getting the other prompts to work, though. Seeing some of the ways that the issues were approached through the demo in class helped me to better understand the concepts that I struggled with. I rewatched the video after class to further help with reviewing the concepts. I also looked through the textbook chapter on dictionaries. I had come across that term a bit in another class, but I wasn’t well-versed in how dictionaries function. Having some additional information as to how they work, as ordered and changeable data types, was also helpful.  

Adding the `while True` statement made more sense to me after rewatching the class video. It would make sense that you wouldn’t need to loop through earlier parts of the program. This was actually an easier fix than what I was thinking. This approach makes the program more streamlined by allowing the user to go right to the menu. It is also made the `break` function clearer to me because its breaking out of the loop that you have created with the `while` statement. 

Also, refactoring the `def get_columns_to_print` function also became clearer while seeing it live-coded. I had trouble figuring out how to get this to work because I added in `return columns_to_print` and called  `get_columns_to_print()`, but I didn’t assign it, which resulted in an error message there. It made more sense that `columns to print = get columns to print`.  But also, as shown during class, setting it to `columns_to_print = headers` creates a less clunky user interface was really helpful.

```python
def get_columns_to_print():
  # Let user choose which columns to print, or print them all
  columns = []

  for header in headers:
    selected = interface.input_is_yes(f"Do you want {header} in simplified print view?", default = 'y')
    if selected:
      columns.append(header)
    
  return columns
  
columns_to_print = headers
```

I didn’t think to change the code to `columns_to_print = headers` but it showed how much clearer it makes the program from a user perspective. Adding `columns_to_print = get_columns_to_print()` to `elif choice_str == "3":` also made much more sense after going through the steps above. This was another lightbulb moment that helped to clarify how to allow the user to choose which columns get printed. 


I’m still having trouble figuring out how to execute the last prompts in the assignment. I didn’t get far beyond what we discussed in class. Turning `row_dicts_list` into a function, and using the selected filename to create a new `row_dicts_list` are still fuzzy. This is something similar to what was done in the examples which I rewatched, trying to make sense of the steps, but I’m still a bit stuck. And for using `get_csv_filename` to let the user select a new file, I understand that it would be something that you would need to change within the interface.py tab. In main.py, the filename is set to `ischools-clean.csv`. You would need to change the input function to allow the user to choose which csv file they want to use, but I don’t fully grasp how to make that happen sucessfully. It’s probably a simple fix, and once I see how it’s done it will feel obvious, but right now I’m struggling to conceptualize how to input that in the code. I think I may just need to take a break from looking at the assignment and revisit it later. I’ve looked at it for the last week and haven’t made much progress on coming up with workable solutions, but maybe doing further review, and revisiting the assignment after a break will help to solve some of the issues presented. 

**CSV 1 Program**
<iframe src="https://trinket.io/embed/python3/e2a5983c2a" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
<br />
<br />

**CSV 2 Program**
<iframe src="https://trinket.io/embed/python3/4a15d272c1" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
