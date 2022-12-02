---
layout: post
author: iLiekatz
title: "CSV File Reflection"
---

Here is my program after week one: <iframe src="https://trinket.io/embed/python3/43e24c2c15" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
Here is my final program after week two: <iframe src="https://trinket.io/embed/python3/769d1e0410" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

My program from my last focused reflection ended up not working, and I had to spend a lot of time figuring out why and how to fix it. I put in a lot of work on my own, and got super excited when I had a finished program of what I intended to do! That excitement from that program had me on fire in a way coming into this CSV program. 
## Week One
### Challenge # 1 
Trying to familiarize myself with the program for the first time
When I first opened the program and began trying to understand it I had a challenging time working through what was already written. During week one it had me feeling a little defeated. I didn’t know where to start. My attention kept going to the comment block of to-do’s, but without a solid understanding of the code I had a hard time focusing on next steps.
It was comforting to hear the professor talk about how that is an expected challenge. In class when we spent time live coding the CSV program, the way Elliot walked through the code to understand it really helped me. Next time I am given code that was not written by me like this, I think I will have a little bit easier of a time understanding it because of the method and tips he took to become acquainted with this current program. 
### Successes Week One
#### Todo #1
Putting the interface in a while loop
The first question I asked myself for this to do is what could I possibly want to do multiple times. What stuck out to me was the main menu, and I thought that would be something I would like to be able to come back to. 
Next I needed to understand how to write the while loop. I knew where the while loop needed to be, above this code block:
```
choice_str = interface.get_menu_choice(menu_dict)
print(f"You chose {choice_str}:")
print(menu_dict[choice_str])
```
Then I thought about what all the while loop needed to contain. Everything below the code block is elif statements, and I know that this is exactly what I want looped through. I also know that I need a way to leave this while loop or else it will be infinite. So I determined that this is how I will end the while loop:
```  
    elif choice_str == "5":
    	    break 

print("Goodbye")
```
In class Elliot highlighted the small nuance of moving the `print(“Goodbye”)` above the break. I thought that was a better flow for a user of the program so I made that change to my final code. 
#### Todo #2
Add an Exit in Main Menu
I did not realize that the main menu was a dictionary and not something we had covered in class yet. Looking more closely I see the {}, but when I had my first go with this to do, I thought it was a list. Only when Elliot highlighted that we had no exposure to this yet did I realize I missed something during my first week of working with this program. Luckily this didn’t hinder me in accomplishing todo #2 easily.
### Challenge #2 Week One
#### Todo #3 
I was not successful in accomplishing this todo before class. Only after our live coding session was I able to make progress with it. My main struggles thus far have been with refactoring. I can know how to define functions and call them. However, taking code that works well and finding a new way to write it is not something that I can logically wrap my head around right now. I found myself going in nonsensical circles with this to do, and ultimately left this as my code for week 1:
```
def columns_to_print():

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
During class I was happy to see that I had the right idea of where to define the function. Refactoring is something I will have to continue to work at understanding.
## In Class Live Coding Session
#### Todo #4 and 5
For these todo’s I followed along with Elliot in class. It was really helpful for me to hear the thought process going through these tasks, and approaches to solving them. It helped me feel better prepared for the remaining 4 tasks to come in week two. 

## Week Two
### Challenge #3
#### Todo # 6
Once again I found myself completely stuck on how to proceed with the refactoring of the code. Like the week before, I found myself going in circles which made it hard to document my process. It was a lot of trial and error, with little understanding of what I was trying to accomplish.

### Successes
#### To do # 7,8, and 9
When I first read todo 7, I misread it. It asks to use the `get_csv_filename` to select a new file after running the program, but the way I interpreted it was to allow the user to select a file from the start. I adjusted the variable filename to allow for this. What was `filename = "ischools-clean.csv"` changed to `filename = get_csv_filename()`

After successfully running the program for the ischool-messy.csv I realized that I could not select a new file to run. Thats when I realized that we had a Main Menu option to allow for this. I wasn’t sure if I needed to write new code here. So as my first trial I copied this code from above and pasted it into the 4th menu choice code
```
elif choice_str == “4”:
    filename = get_csv_filename()
    with open(filename) as file:
        reader = csv.DictReader(file)
        row_dicts_list = list(reader)
```
And it worked!

For the last todo’s I feel like I stumbled my way through without fully understanding what I needed to do and why. It was some lucky trial and error that happened to work, but looking at it the final product I do understand why it works. 

My biggest takeaway from this assignment was that I need to spend more time on refactoring, especially on code that was not written by me. 
