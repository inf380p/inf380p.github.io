---
layout: post
author: shashwatj14
title: "Shashwat's CSV and Reflection"
---

#Reflection:

My first attempt at completing all of the CSV Code assignment's to-dos made me realize one thing: I've learned a lot in the last few weeks. Although it took me some time to figure out all of the tasks in the assignment, the level of ease with which I was able to complete it was significantly higher than the previous ones. After a bit of struggle, I learned some new things with my first attempt:

Python 2 was used for my initial attempt, and I later learned that it doesn't allow f strings. Sincerely, Python's support for f strings intrigues me greatly, and I think it greatly simplifies the way we display our outputs. Therefore, I made the decision to transition to Python 3, and I eventually created a solution in Python 3.

Reading through the code enabled me to identify similarities in how the menu_dict dictionary was created and then used, which enabled me to complete this work. Since I could see that each number in this case represented an option, I simply added a fifth choice to the menu dict.
```
menu_dict = {
  "1" : "Browse rows of data",
  "2" : "Print specific row",
  "3" : "Select columns to print",
  "4" : "Change data file",
  "9" : "Exit"
}

```

Code refactoring and the impact it can have are among the new things I learned. I used to believe that code refactoring was solely intended to tidy up the codebase and cut down on lines of code, but the example of refactoring below allowed me to use the same piece of code in an interactive menu that could read updated files if necessary.
```
def get_data(filename):
  # Get a list of dictionaries from CSV file
  with open(filename) as file:
    reader = csv.DictReader(file)
    row_dicts_list = list(reader)
  # Headers of the CSV are the keys of any row dictionary
  # Get the keys from the first row
  headers = row_dicts_list[0].keys()
  
  return row_dicts_list, headers
```

Along the way, I also made some stupid errors like defining local variables outside of the method. However, I've learnt over the past few weeks that declaring local variables inside a function is probably the best course of action rather than declaring them elsewhere. The functions will still run in this scenario.
```
  columns = []
  def get_columns(row_dicts_list, headers):
  # Let user choose which columns to print, or print them all
  if interface.input_is_yes(f"File '{filename}' has {len(headers)} columns. Select which columns to print?\n", default = "y"):
    for header in headers:
      selected = interface.input_is_yes(f"Do you want {header} in simplified print view?", default = 'y')
      if selected:
        columns.append(header)
  else:
    print("All columns will be printed")
    columns = headers
  return columns

columns_to_print = get_columns(row_dicts_list, headers)

```

Finally, I was able to give the user the option to quit by following the pattern established by the other choice strings. When a user enters 9, he or she will be able to exit my program.
```
   elif choice_str == "9":
    break
```

I believe the exercise has made me a much more patient coder, and I appreciate that the lecture provided some direction without requiring us to complete the entire project. In week 1, I couldn't finish all to-dos but I was able to do it in week 2. Despite the frustration, I was determined to learn how to read and work with this code so that I could improve. I believe that the time and effort I invested in not only understanding it, but also figuring out what I didn't understand and how to apply the knowldege that I had to finish the program was a very valuable experience for me as a programmer.

Here are my trinkets:

Week 1 trinket: <iframe src="https://trinket.io/embed/python3/058c905ebc" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Week 2 trinket: <iframe src="https://trinket.io/embed/python3/542a112071" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
