—
layout: post
author: rabouti
title: CSV Reflection
—



## Some Context

In my reflection, I am going to be extremely candid and write as though I am having a conversation with you in order to convey my level of awareness. My ways of thinking are very random and chaotic, so trying to write out my creative process in an organized and articulate fashion has definitely been challenging. However, doing so has pushed me to think in new and more functional ways regarding reflecting on writing/making changes to code. 

At first, I found this assignment confusing and overwhelming, but I took it very seriously and saw it as an opportunity to strengthen my comprehension of lists, strings, files, writing functions, and looking at code that I did not write then adding to it and making changes. I started early, and I consulted my friend who is a software engineer to help me work through the to-dos I was having trouble with and to talk about code in general. I consulted him because I knew I could sit with him for as long as I needed and ask all of even the “silliest” of questions about code. 

This assignment gave me a new perspective on how to use Python, for up until this point I have used to assignments as a creative outlet - while this assignment heavy on data analytics and pulling data (new territory for me and my current level of fluency in Python). 

## Problem Solving that works for me

The problem solving method that has not failed me thus far is “The 4 Rs” - reading, running, ruminating, and retreating. The first method I utilized to attack this assignment was reading the provided code to gain a thorough understanding of the expectations. Next, I ran the code before I made my changes to get a sense of what the program does when it runs and what needs to be changed. In the past on our assignments, I’ve spent too much time ruminating, and for this assignment I tried to balance the time I spent ruminating by running the code as I made changes. For example, the first feature on the to-do list (“put the interface in a while loops so that the user can do multiple things”), at the time, was overwhelming to me so I skipped it and continued with the rest of the to-dos. By skipping the first feature that I requested changes and continuing with the rest of the to-dos, resulted in a Syntax Error. I realized it was because I needed to make the first change “put the interface in a while loop so that the user can do multiple things.” After doing so, the Syntax Error was resolved. 

I was confused on where the while loop needed to be in the program until further examining the code and realizing in order to allow the user to “do multiple things” the while loop would need to be strategically placed in the program where the code allows the user to make choices/interact. For putting a while loops anywhere else in the program would not provide the user with the same level of autonomy with the interface and ability to “do multiple things.”

Below I have provided the while loop I wrote that allows the “user to do multiple things” (I’m proud of it and wanted to share).

```
while choice_str != 5:
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
      for key in printing_columns:
        print(row[key])
      if interface.input_is_yes("Continue?", default = 'y'):
        continue
      else: 
        break
  elif choice_str == "2":
    # Print specific rows
    if interface.input_is_yes("Print random row?", default = 'y'):
      row = random.choice(row_dicts_list)
      
      for key in printing_columns:
        print(row[key])
    else:
      row_int = interface.get_valid_row_int(row_dicts_list)
      row = row_dicts_list[row_int]
      
      for key in printing_columns:
        print(row[key])
  
  elif choice_str == "3":
    print("""
Choice 3
  """)
    
    printing_columns = columns_to_print() 
    choice_str = interface.get_menu_choice(menu_dict)
  elif choice_str == "4":
    print("""
    Choice 4
    """)
    
    file = interface.get_csv_filename()
    filename = file
    with open(filename) as file:
      reader = csv.DictReader(file)
      row_dicts_list = create_rows_dicts_list(reader)
    choice_str = interface.get_menu_choice(menu_dict)
  
  elif choice_str == "5":
      print("""
  bye
  """)
```


## Lightbulb

One lightbulb that turned on for me while working on this assignment was when I realized you wanted us to make “columns_to_print” a function so we could use it multiple times in the program. Below I have provided the function I wrote for “columns_to_print.”

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
  
  return columns_to_print
  
printing_columns = columns_to_print()
choice_str = interface.get_menu_choice(menu_dict)
```

## Still Fuzzy for me

Something that is still fuzzy for me is utilizing empty strings (“”). I’m unclear on when and why you’re supposed to use empty strings. In order to resolve my fuzziness surrounding this issue, I’m going to refer to the textbook chapter on strings. 

Since I finished this assignment last week and was able to effectively tackle all of the to-dos, the differences in each of my embedded trinkets are slight but I still took the time to make my second program more efficient, organized, effective, and clean. 

###### First

<iframe src="https://trinket.io/embed/python3/464a915e52" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


###### Second

<iframe src="https://trinket.io/embed/python3/41b1394483" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


## Final Thoughts

I can humbly admit that I still have a lot to learn and improve upon when it comes to writing reflections, and I’m excited to enhance my abilities to write about my creative process regarding my unique programs. This assignment strengthened my understanding of files and how to write code that allows you to pull data from files, and providing the user with more autonomy while using an interface. 

Additionally, for future assignments, I am going to take more advantage of retreating (the fourth R) because I understand that allowing my work to incubate is crucial in order to turn over work that reflects my best effort and abilities. For incubation allows me to resolve issues with a fresh perspective and break free of my previous rumination spiraling. 

Moreover, in order to enhance my reflections and how they read, I am going to take more thorough notes while writing my programs. To write more effective reflections, I am going to review and strengthen my level of familiarity and comfortability with the vocabulary, for precision of language will significantly improve my reflections. 
