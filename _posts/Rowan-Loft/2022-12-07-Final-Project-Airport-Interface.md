---
layout: post
author: Rowan-Loft
title: "Rowan-Loft's Final on US Airport Information"
---

## Introduction

I decided to go with a data analysis project for two reasons. Firstly, I perceive this sort of work as being something that I would realistically use in my future career, studies, and personal endeavors. Second, while Turtle was interesting to learn, I had a personal disconnect in how Turtle was used to accomplish more "artsy" tasks. While I recognize that *that* is not all Turtle is for, I couldn't and still don't know how I would really use Turtle in the future where I intend to be working in library sciences and research projects. And so, with these first thoughts in mind I turn to my project: The US Airports CSV Explorer. 

I decided to create a program that looked at and tried to make sense of a constantly updating .csv file hosted at Humandata.org which is made up of all the airbases in the United States and their information. In approaching this initial file, I realized that there was no rhyme or reason to ordering: not by id, score, last recorded update date, or beyond. A perfect file for the sort of skills that I've been cultivating through the semester in this class. The page where the .csv is located can be found here: https://data.humdata.org/dataset/ourairports-usa

Here is what the final iteration of my project looks like:

<iframe src="https://trinket.io/embed/python3/facdee0921" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Milestones & Process

### Nov. 10th - 16th

- [x] Determine what values will be used from the incorporated excel spreadsheet
- [x] Ensure that airport.csv is computer readable from the imported excel spreadsheet
- [x] Create user navigable menu
- Created menu interface using previous class examples from .csv files class assignment
- Determined that the scope of the assignment would exclude non-airport entities in the original airport .csv

### Nov. 17th - 21st

- [] Create Filters for users to determine what values they do and do not want included in the return
- [x] Create an option for cleaning the initial data file
- [] Allow users an option that lets them look at airports based on suggested filters
- [x] Further the scope of the project by removing smaller, private airports
- Removed small airports from the scope of the project since they were unlikely to be commercial spaces

### Dec. 1st - 7th

- [x] Create Filters for users to determine what values they do and do not want included in the return
- [x] Allow users an option that lets them look at airports based on suggested filters
- [x] Sort airports by score when returning values to user
- [x] Added an `About` section that explains the project in the program itself

### On the topic of duplicates

As I've mentioned before, there were elements from the original .csv that were removed before I uploaded and started working with the data. Most of these instances occurred where FAA and local information conflicted, such as there being different codes for region where there isn't really a difference other than the inclusion of National differentiation. When there were instances of conflict such as this, I decided to defer to the most authoritative source, which often meant retaining FAA elements and removing local elements in order to make everything more user-readable and to cut down on the number of headers that were going to be in the dictionary. In some cases, FAA elements had duplicates that were retained because they work at different levels (international vs. national vs. local).

The dictionary headers that were retained are defined as follows:

- id: a number assigned to an individual airport
- type: the type or size of airport (seaplane_base vs. small_airport vs. large_airport)
- name: airbase name
- region_name: the state that an airport is located in
- iso_region: international standard for location
- municipality: name of the governing city or town of an airbase
- schedule_service: traffic and capacity element standard
- gps_code: international 4-letter aerodrome identifier
- iata_code: national alphanumeric 3-letter aerodrome identifier
- local_code: local alphanumeric 3-letter aerodrome identifier
- home_link: a link to the airbase' website if it exists
- wikipedia_link: a link to the airbase' Wikipedia page, if it exists
- score: an assigned integer designated by the community that built the .csv

## Some Code Talk

To begin talking about the code itself, I want to breakdown some of the most important functions in the program. Here is arguably the *most* important part of the program:

```
def clean_datafile():
  unwanted = ["heliport", "closed", "seaplane_base", "balloonport", "small_airport"]
  wanted_airports = []
  # get a list of dictionaries from CSV file
  with open("airports.csv", newline='') as file:
    reader = csv.DictReader(file)
    file_row_dicts_list = list(reader)
    with open("airports_final.csv", "w") as output:
      writer = csv.DictWriter(output, reader.fieldnames)
      writer.writeheader()
      for row in file_row_dicts_list:
        if row['type'] not in unwanted:
          writer.writerow(row)
          wanted_airports.append(row)
  output.close()
  return wanted_airports
```

The clean_datafile function looks through the airports.csv and removes any information in cells containing the described airbase types. After locating the undesired airbase types, it creates a new .csv that does not include those types. For the sake of this program's scope, I decided to only include medium and large airports, which are most likely to be commercial (and some military) airbases. This meant removing the `unwanted` variables that were defined. This was immensely helpful in reducing the scope of the program and also reducing my own stress, since the original .csv included roughly 30,000 elements. The number of `wanted_airports` that were thus retained in the program was 872 rows. Plus, while there isn't a means of changing these elements while the code is live, by removing any of the enclosed elements in the `unwanted` list, the user could then re-initiate the program and then search including the newly included airbases. 

Next up in the flow of the program was creating a function that reasonably ordered the information returned to a user, `sort_airports`:

```
def sort_airports(ports):
  #'reverse = true' allows the list to present in descending order
  sorted_ports = sorted(ports, key=lambda x: int(x['score']), reverse = True)
  return sorted_ports
```

The sort_airpots function is what I used to order the airports by "score", one of the headers in the original .csv, "score" was defined by the contributors of the project and other community members, so it is an arbitrary attribute to us, but one that is relevant to the community for determining airbase comparison and one I believe that would be useful to users of this program. While sorting by ID would have also been a viable means of ordering airbases, I believe ordering by score is more meaningful for users.
  
It's important to note that the `sorted_ports` variable comes from 'note.nkmk.me' an online webpage for coding articles. The particular article that assisted me in creating the variable can be found at: https://note.nkmk.me/en/python-dict-list-sort/

Next up is the `filter_airports` function:

```
def filter_airports(headers, ports): 
  # Let user choose what values they would like to filter out of the search
  filtered = ports.copy()
  for header in headers:
    selected = interface.input_is_yes(f"Do you want \"{header}\" to be included in your search?", default = 'no')
    if selected:
      new_filter_value = interface.get_input(f"Value to search for in \"{header}\"")
      if ( new_filter_value == "" ):
        continue
      new_filtered = []
      for airport in filtered:
        if new_filter_value.lower() in airport[header].lower():
          new_filtered.append(airport)
      filtered = new_filtered
  return filtered
```

The `filter_airports` function is used to define what headers the user of the program would like to view the airbases by. It does so by allowing the user to input a value to search airbases by, such as inputting "medium_airport" or "large_airport" into 'type' when the header is called. 
  
After defining the filter, options 1 and 2 in the menu return how many airbases fall under the defined criteria and then return the information related to those airbases respectively.

The last major function in the code is the `while` loop that creates the menu that a user navigates, which is as follows:

```
while choice_str != "6":
  #call the users input
  print(f"\nYou chose {choice_str}:")
  print(menu_dict[choice_str])
  
  if choice_str == "1":
    print(f"Number of Matching Airports: {len(filtered_airports)}\n")
  elif choice_str == "2":
    for airport in filtered_airports:
      interface.dict_print(airport)
  elif choice_str == "3":
    print("To remove all filtering, simply choose no headers to filter by.\n")
    filtered_airports = filter_airports(airports[0].keys(), airports)
    print(f"Number of Matching Airports: {len(filtered_airports)}\n")
  elif choice_str == "4":
    airports = sort_airports(clean_datafile())
    filtered_airports = airports.copy()
  elif choice_str == "5":
    print("\nThe US Airports CSV Explorer is a Python 3 program that allows users to navigate a .csv of compiled airport information that comes from Humandata.org, which can be found here: https://data.humdata.org/dataset/ourairports-usa\n")
  else:
    # get_menu_choice should ensure this is never hit, but just in case.
    print ("Invalid Choice, Please Try Again")
  #prevents the menu from infinitely looping
  choice_str = interface.get_menu_choice(menu_dict)
```

This one is fairly straightforward, but I'll break it down further by menu options! Option 1, "List Number of Airports Matching Criteria," accomplishes exactly what it says: when a user inputs criteria using Option 3 (tbd), they can then choose Option 1 to see how many airports in the `airports_final.csv` module fit the criteria that they select.

Option 2, "Print Airports Matching Criteria," returned airport information falling under the headers that users choose to include in their criteria through the use of Option 3.

Option 3, "Define Filter Criteria," allows users to navigate each header and decide if they want to return airport information using specific values in the headers, such as searching for airbases in Texas by returning "y/yes/yeah" when asked if they `want "region_name" to be included in your search?"` and then typing "Texas/texas/tex" and other variations that include elements of the state name in the user input.

Option 4, "Update and Clean Datafile," initiates the `clean_datafile` function. This function automatically happens when the program first initiates, but a user can run this function again if they change wanted and unwanted variables, or if they want to reset the filter. 

Option 5, "About," gives cursory information about the function of the program and directs users to the link where the original .csv can be found.

Option 6, "Exit," breaks out of the menu loop and ends the program.

One last thing I'd like to note is that the `interface.py` module pulls on previously provided work that makes menu navigation more user friendly.

## Looking forward and Conclusion

Both that class and this final project were exciting for me to experience, as someone who had minimal python experience and knowledge before entering the class. It gave me a new insight into a side of workflow that I often don't get to see and interact with since I often interact with programs from the user-side of the interaction. 

If I were to have more time with this project, I would have liked to look into how I could have created a function that allowed users to remove undesired airbase types on the front end of the interaction. I also would have looked into how I could have worked more directly with the raw .csv to scrape undesired column elements with Python itself, instead of directly removing said columns from the .csv before importing it to the program. I do think that I'll see myself doing more of this sort of work, whether for personal interest or academic/professional, so I'm glad to have had the opportunity for building a foundation for the language.
