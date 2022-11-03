---
layout: post
author: unixEnthusiaast
title: "Nikhil's CSV exercise and Reflection"
---

#Reflection:

It was an interesting week and learning from doing the CSV activity and trying to wrap my head around the functionality of it. Pyhton's identation keeps bugging me but I am managing much better than before. Working on editing an already created file with TODO requirement took some time but i was able to identify the issues needed to be fixed. I started off with the flow of the program and then went deeper into the functionality. First week was mostly focused on the layout and the flow of the program:

```

menu_dict = {
  "1" : "Browse rows of data",
  "2" : "Print specific row",
  "3" : "Select columns to print",
  "4" : "Change data file",
  "0" : "Exit"
}

```

Also the genreal while loop to create the program interface:

```

# while loop for the interface to continue unless prompted
while True:
  choice_str = interface.get_menu_choice(menu_dict)

```

Understood the need for an exit condition to create breaks in the while loop or the program gets stuck forever!

Refactoring also took time but I was able to use find and replace to help with common renames and fixes. This sped up the process by a lot. Getting the wor dictionary was the most crucial part and made the program work like a charm. I learnt a lot especially with the dictionart application and the way the interface worked.

Embedding to the first week trinket:
<iframe src="https://trinket.io/embed/python3/907224e213" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Embedding to the final trinket:
<iframe src="https://trinket.io/embed/python3/907224e213" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
