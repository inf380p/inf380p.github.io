---
layout: post
author: unixEnthusiast
title: "Nikhil's Final Project Interface"
---

# Final Project Interface Start

For the final project, as stated in the inital project proposal, I plan to use existing data reposiory of F1 historical data and do some interesting analysis on it and present it in a nice interface on trinket as a pythin program

- For the data, I will use resources F1.com and Kaggle to get the data required. I aim to get preformatted CSV data but might need to access some APIs to get the data as well.

I feel the following can be a good plan to create the project:

- Accumulate the data.
- Design and implement the interface for the analysis
- Think of the analysis on the data possible and create a plan for implementation.
- Implement the different analysis as functions in the program
- Integrate them all in the main interface.
- Allow the user to browse the data and use the interface.

## Creating the Inteface Menu

To create the interface menu, I took inspiration from the CSV assignment and assigned separate function for rendering the menu from a dictionary of key 'numbers' and the value of the String option. Then, the function goes through the dictionary and prints out the option. When one option is selected, the selected key is displayed. This can be used later to integrate the different feature functions.

Menu Dictionary:

```python
   menu_dict = {
  "1" : "Browse the F1 data",
  "2" : "Browse data for a team",
  "3" : "Browse data for a year",
  "4" : "Browse data for a driver",
  "5" : "Click for interesting analysis",
  "6" : "Help",
  "0" : "Exit"
}
```

Interface function to display menu from dictionary

```python
   def get_menu_choice(choices_dict, prompt_str = "Make a selection"):

  # Make sure keys to the choices are strings
  assert all([isinstance(x, str) for x in choices_dict]), "Keys to choices_dict must be strings"

  # Keys of the dict are the possible choices
  valid_choices_list = list(choices_dict.keys())
  
  # Print main menu and all choice labels and decriptions
  print("Main Menu")
  for label, description in choices_dict.items():
    # print(f"{label}: {description}")
    print(label + " : " + description)
  
  # Get a user choice
  user_choice = input(prompt_str)
  
  # Check if it's a valid choice. If it is, loop is skipped.
  while user_choice not in valid_choices_list:
    # User's choice was invalid; loop until it is
    print(user_choice + " is not a valid selection.")
    user_choice = input(prompt_str)

  return user_choice
}
```

## Next Steps
I want to gather and start working on the data to be used for the analysis. Also start on atleast 2-3 of the functionality mentioned in the menu. That should be good goals to cover in the coming week.

Trinket Embed for the Interface:
<iframe src="https://trinket.io/embed/python/4a6fa3c601" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
