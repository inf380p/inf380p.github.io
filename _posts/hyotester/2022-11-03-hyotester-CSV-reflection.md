---
layout: post
author: hyotest
title: "Hyo's CSV exercise and Reflection"
---

# CSV Reflection


## A most challenge parts for first week:
During two week’s assignment was the most challenge tasks in this class!The first challenge I came accross was overwhelmed since the todo tasks 
for the interactive menu required many functionalities such as infinite loop and interface.

Specifically, I was confused on the `while` loop. To create while loop the program interface:

```
filename = interface.get_csv_filename()
```

```
# while loop for the interface to continue unless prompted
while True:
  choice_str = interface.get_menu_choice(menu_dict)
```
Also ,I focused on the layout creating row_dicts_list:

```
menu_dict = {
  "1" : "Browse rows of data",
  "2" : "Print specific row",
  "3" : "Select columns to print",
  "4" : "Change data file",
  "0" : "Exit"
}
```

Embedding to the first CSV trinket:

<iframe src="https://trinket.io/embed/python3/6898d670d1" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


## A most challenge parts for second week:

I wanted to provide more option using the pattern established by the other choice strings. To enter or exit in the previous version, user need to enter 0, 
but I changed number as 7 be able to enter or exit in my code. Therefore, I use If else statements (decision making statements) to execute a block of statement on specific conditions. 

```
 elif choice_str == "7":
    break
```


Embedding to the final CSV trinket:

<iframe src="https://trinket.io/embed/python3/87042aac17" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Fucntions that I'm still confusing..

I tried to expand row_dicts_lists from 1 to 20 , but I've stocked with error. Further assignment or fianl project, I will try to write my thorough notes/ process first and then
write code to be more effective reflections.

