---
layout: post
author: emmtm
title: "Emmtm's CSV Reflection"
---

Program week 1: <iframe src="https://trinket.io/embed/python3/3c206917e4" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Program week 2: <iframe src="https://trinket.io/embed/python3/1a566442cd" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Upon my first pass attempting to complete the to-dos in the CSV code assignment I was completely and totally lost. This was my first time having to read, comprehend, and work with code that I myself didn’t write, and at first I found it frustrating. While my original instinct was to jump right in and start coding I realized pretty quickly that this strategy was not going to get me very far, and instead decided to focus my energy for the first week of the assignment on building my code comprehension skills. I spent a lot of time re-reading the code, moving around from the main.py to the interface to help myself understand why the code was working in the way that it was. Doing this helped me to understand the naming conventions in the code, recognize the patterns, and identify concepts I would need to become familiar with if I wanted to complete the assignment. Concepts such as dictionaries and files were new to me, so I went back and read chapters in the book that related to these things, especially looking at the functions module to help me with the refactoring portion of the assignment. 

I was still pretty lost, even after doing this, but I had a better idea of what types of questions to search for on help boards and where in the book would be helpful to reference once I started working on the to-dos. The first week, I was only able to figure out one of the to-dos- adding an exit option to the menu. Even though I didn’t fully understand dictionaries, I was able to see patterns in the ways they are set up and then called by reading through the code, which helped me be successful in this task. Here, I saw that each number corresponded with an option, so I just added a fifth item into the menu_dict: 

```
menu_dict = {
  "1" : "Browse rows of data",
  "2" : "Print specific row",
  "3" : "Select columns to print",
  "4" : "Change data file",
  "5": "Exit Program"
}

```

Then I followed the pattern seen in the code that calls the choice strings related to the dictionary, learning along the way that calling functions from the interface required the format interface.function. This was a bit confusing to me as I have pulled functions from modules before without using this format, but I realized it was at least familiar to me from the ways we pull turtle functions out of the turtle program. The resulting code for the to-do was this:

```
  elif choice_str == "5":
    #exit program
    if interface.input_is_yes("Would you like to stay in the program?", default = 'y'):
      choice_str = interface.get_menu_choice(menu_dict)
    
      print(f"You chose {choice_str}:")
      print(menu_dict[choice_str])
  
    else:
      print("Goodbye")
      exit()

```

By following the pattern set by the other choice strings I was able to not only give the user the option to quit, but also made it so the program would redirect them back to the main menu to choose a different option if they decided not to close the program.

I felt a little defeated by this project coming into class with only 1 task complete, but it seemed like a lot of my classmates were in the same boat and the lecture really helped. Once I knew the whole point of the assignment was to learn how to read and work with other people's code as a way to simulate potential real world situations we may be in as programmers, I felt more motivated to really understand it and grow as a programmer. After we were helped through some of the to-dos in class, I was able to figure out all of them except for one. 

I was having trouble getting the program to be able to choose between files, and found myself in a spot for a long time where I could call get.csv.filename, but the choice the user made was not saved as the file being pulled from when selecting any of the other options. The to-do I was not able to figure out was making row_dicts_list into a function, and was running into issues putting the header = definition into the function as even if I called it later, other parts of the code that needed the header definition were unable to read it. Instead of getting hung up on that part, I decided to try and figure out a different way to override row_dicts_list to allow users to choose between the two files. While refactoring is something that still hasn’t clicked for me, I just collected my questions and then continued to push myself to find a different, creative way to get the same results. 

What I ended up doing to allow for users to switch between files was create a list of both of the filenames, called “filename”, and then added a boolean “for” above the with statement that would open the file. So before, the code looked like this:

```
with open(filename) as file:
  reader = csv.DictReader(file)
  row_dicts_list = list(reader)
```

With file being defined as the single filename given- “ischools-clean.csv”. By setting file equal to interface.get_csv_filename, I was then able to use my for statement to help the program read both files, give the user the option to choose which one, and then because the reader was set equal to csv.DictReader(file), the row_dicts_list would then be overridden each time the user chose one of the files- thus displaying the rest of the menu options correctly in relation to the user input. I left the function call () off of the interface function so that it would not be called until the user asked for it in menu option 4. The final code looked like this:

```
file = interface.get_csv_filename
for filename in filenames:
  with open (filename) as file:
    reader = csv.DictReader(file)
    row_dicts_list = list(reader)
```

Then I simply called the function in menu option 4 like this:

```
file = interface.get_csv_filename()

```

The program then worked exactly how I wanted it to! I didn’t figure it all out on my own, I consulted a lot of help boards and forums about opening and parsing multiple files at a time using python and .csv. I think the exercise made me a much more persevering programmer, and I’m glad that we were able to get some help in the lecture without us going through the whole assignment. As frustrating as it was, I really wanted to figure out how to read and work with this code so I could become better, and while I didn’t have any massive lightbulb moments, I think the time and energy I spent into not only understanding it, but figuring out what I didn’t understand and how I could use what I did understand to still finish the program was a very valuable experience for me as a programmer. 
