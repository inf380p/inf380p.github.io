---
layout: post
author: Rowan-Loft
title: "Rowan-Loft's Final Project Update"
---

#Rowan's Update 1

###Intro

For my final project, I decided to create a data processing program that looked at parsing and making sense of US airport data retrieved from [humandata.org](https://data.humdata.org/dataset/ourairports-usa). I decided to work with this data because they supply an excel containing all of the relevant data, but it is not organized in any discernible way that I've been able to understand. And so, I decided to write code that would allow a user to navigate the messy data and look more easily for information that they wanted.

###The First Step

The first step for working with this data was deciding what would go into the program. While the .csv file contains a lot of information, I deemed a lot to be unnecessary or repeat data. Looking at the .csv you can download, this included columns such as: **latitude**, **longitude**, **country**, **continent** and so on. For some of these elements like **country**, I decided to remove them since the scope of the project is in the name of the program: "US Airports CSV Explorer". However, there were some murkier elements such as **iso_region** and **local_region** that both read the same. For most users, they would recognize **region** as identifying the state of an airport, but I decided to use **iso_region** instead since it is one of the regulated FAA guidelines for airport identification. In instances such as this, where FAA identification or layman identification overlapped, I went with the most authoritative identifiers. 

After manually removing irrelevant or duplicate columns, my next step was to start the actual coding. After putting the excel into trinket, my first lines of code were intended to be further selective of what would be retrieved. In the excel, aside from **airports**--**balloonports**, **seaplane_base**, **heliports**, and **closed** (airports) were also in the list. I made the decision to not include these elements in the program itself, as so now I include the first bit of code:

```
def clean_datafile():
  unwanted = ["heliport", "closed", "seaplane_base", "balloonport"]
  # Get a list of dictionaries from CSV file
  with open("airports.csv", newline='') as file:
    reader = csv.DictReader(file)
    file_row_dicts_list = list(reader)
    with open("airports_final.csv", "w") as output:
      writer = csv.DictWriter(output, reader.fieldnames)
      writer.writeheader()
      for row in file_row_dicts_list:
        if row['type'] not in unwanted:
          writer.writerow(row)
  output.close()
```

`clean_datafile` had a dual purpose: it removed the aforementioned elements from the .csv *and* by assigning them as `unwanted` and remove them, and further enhanced the scope of my program by going from 29,000 rows to only 15,000. Not only does this help refine the intended purpose of the program and make it easier to navigate, it also lightened the load that is the massive excel. 

###The Second Step

Next was to create a user-navigable menu. While I have not created all of the options I wish there to be for a user, I accomplished the menu using some old code that I used on a previous assignment:

```
menu_dict = {
  "1" : "Browse Rows",
  "2" : "",
  "3" : "Make clean_datafile",
  "4" : "Exit"
}
```

This assigns the dictionary for the menu. It is yet to be complete.

```
while choice_str != "4":
  # Tell user what choice they made
  print(f"You chose {choice_str}:")
  print(menu_dict[choice_str])
  choice_str = interface.get_menu_choice(menu_dict)

print("Goodbye")
```

This executes the user navigable menu, ensures that it does not loop infinitely, and creates an invisible `break` clause so the user can exit the program. I believe that the steps to follow will be creating useful functions that allow users to interact with the data itself: displaying by state, by type, municipality, and etc. But for now, I'm mostly glad to just have the program at a reasonable size. Here is the program so far for your perusal: 

<iframe src="https://trinket.io/embed/python3/dce83cf42f" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
