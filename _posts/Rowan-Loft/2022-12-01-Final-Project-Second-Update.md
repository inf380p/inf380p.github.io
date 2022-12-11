---
layout: post
author: Rowan-Loft
title: "Rowan-Loft's Second Project Update"
---

## Starting Reflection

Following the Python Meetup that I attended, I realized that I've been missing out on building my project with the "why" component in mind. Coming from a historian and classical studies approach, my frame of mind for building a project to establish discourse and meaning has traditionally been through the use of essays and presentations, so it's nice that I'm finally beginning to see how I can apply the same frame of mind to the work that I'm accomplishing with my project. When I decided to take on the project of creating a user-navigable menu of a dirty .csv file of airports in the US, I did so simply because it was disorganized. But now that I'm starting to recontextualize the project with the deeper "why" in mind, I can see how my program could be beneficial for people who are looking to travel and are unsure what airports they may be travelling *from* and *to*. While that's not the most contemporary thought or tool since Google can accomplish it easily enough, the project is giving me an idea of how these sorts of programs are used as cornerstones to our possible every-day research both in academia and the simple searches. 

Now for some code talk. Here is the 2nd Iteration of my Program:

<iframe src="https://trinket.io/embed/python3/25b8dd9e20" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

My Milestones are in the code itself at the top of `main.py`, but here they are again for the sake of simplicity:

#### Milestones
* (X)Determine what values will be used from the incorporated excel spreadsheet
* (X)Ensure that airport.csv is computer readable from the imported excel spreadsheet
* (X)Create user navigable menu

* Create Filters for users to determine what values they do and do not want included in the return
* (X)Create an option for cleaning the initial data file
* Allow users an option that lets them look at airports based on suggested filters
* (X)Further the scope of the project by removing smaller, private airports	

## Code Talk

While working on the project, one of the issues that I ran into was in ordering the code. I'm not sure if this is a Trinket feature, but it seems that defining a function must come before calling the function. To elucidate, I created the `clean_datafile()` function at line 37, and called it at line 77 under Option 4 in the menu, but originally I wanted to put all of my functions at the bottom of `main.py` and put my menu towards the top. However, when I ran this I would constantly run into an error where Trinket told me that the function had not yet been defined. While this isn't really a problem, it was something interesting the I noted while working on my program. 

Next up, I would like to revisit the topic of project scope. When I pulled the .csv that I'm using into Trinket, it was originally 30,000 rows of data. As I've talked about in my previous update, I narrowed this to 15,000 after removing non-airports: sea plane bases, balloonports, and helipads. However, after doing some research into what was left, I decided to remove small airports, which are now defined as `unwanted` in my `clean_datafile` function, which leaves me with 800 medium and large airports. Most of which are commercial airports and some military bases. I decided to do this since these are the most likely airports to be traveled to and from commercially or for travel. I *do* recognize that small airports could serve to let community members know where they could find local airfields, I've decided for the moment that those fall outside the scope of what I'm hoping to accomplish. 

Here's the updated `clean_datafile` variable for view:

```
#Looks through the airports.csv and removes any information in cells containing the following airbase types
#After locating the desired airbase types, creates a new .csv that does not include those types
def clean_datafile():
  unwanted = ["heliport", "closed", "seaplane_base", "balloonport", "small_airport"]
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

I've now turned to creating options for users who wish to directly navigate the program, and am now working on a filter creating function, `create_filter`, which allows users to define what among the headers they want included in their search. That bit of code is as follows: 

```
#defines the create_filter function
def create_filter(headers): 
  # Let user choose what values they would like to filter out of the search
  new_filter = []
  for header in headers:
    selected = interface.input_valid(f"Do you want {header} to be included in your search?", default = 'y')
    if selected != "":
      new_filter[header] = selected
  return new_filter
```

## Final Comments

As of now, the function is clashing with my interface, which is what I'll be looking into fixing in the short-term, but following that will be creating a function for users to navigate airports using the filters and inputs that they put in, such as locating an airport through their current state-location, or otherwise. I don't think that any of this is *too* ambitious or outside the scope of what I hope to accomplish, but I look forward to updating you on it soon. Also, as an aside, I want to point out that *this* work, programming for user-navigation, has been much more enjoyable for me than Turtle was. It wasn't that Turtle was bad, but I've always struggled wish creating abstract visualizations, so this sort of work has been a lot of fun for me to experiment with and learn about. Thanks for reading.
