---
layout: post
author: amptex101
title: "Allison's Final Project post!"
---

####Introduction: Why Data Processing? 

#####I chose data processing for this final assignment. There were a few reasons for this decision. First, my background in programming before this class was manipulating, analyzing, and using CSV files, so I knew of some files I could use already. Second, I haven’t been the biggest of fans of using Turtles. I also didn’t like the fact that we started using Turtles in class before the textbook covered it – I felt behind and confused a lot of the time. Third, I did have a specific CSV file in mind for the project, and I wanted to challenge myself to use the file in ways I hadn’t before. 
#####The CSV file in question is about witchcraft allegations over an approximately 200-year period (1563-1736) in Scotland. The data is pretty extensive, as there were hundreds of alleged cases during this period. The data is from the data.world website, and can be found at https://data.world/history/scottish-witchcraft/
#####There are a lot of individual CSV files on this website. I chose the one specific to alleged demonic pacts – this is called WDB_DemonicPact.csv. This particular dataset categorizes demonic pacts by type (an “Anti-baptism” pact as opposed to a “new name” pact). This dataset might seem silly now, but these people and the allegations they faced really existed. 
#####The link below contains my final project. Treat it nicely! 

https://trinket.io/python3/164a1e5ca4

####Getting Into It 

#####My goal in this assignment was to do a few things: 
#####1)	Allow a user to browse through the data file 
#####2)	Allow the user to delete rows or columns 
#####3)	Produce a FAQ/Help page for this project 

#####To accomplish goal #1, I would need to develop a working menu that printed out from the code. 
#####Towards this end, I would of course be remiss to not mention the CSV file code we used in class. The code is readily available on the class website, and I will also paste it here: https://trinket.io/embed/python3/8f70e6beb2

#####This work from class was my starting point for developing the menu, and thus the project. 

#####An introduction to the pandas library I used in this project seems necessary. This is a Python library which allows you to use data frames effectively, create graphs, create charts and more. I also used the bokehs library, which further assists in data processing and visualization. The link I used to familiarize myself with these libraries can be found below amidst my references. The article, “Visualizing Data with Bokeh and Pandas” is written by Charlie Harper, and I found it generally helpful. 

#####My first task was to set up my library as we had done in class with the CSV exercise. This required setting up the main menu option with numbered options, and then entering the menu options slowly but surely. The code block below shows the finished version, which ended up omitting the “choose a row” function for the sake of time. 

```
# Setting up the main menu 
menu_dict = {
  "1" : "Choose a specific column to look at",
  # show headers, allows the user to choose columns   
  "2" : "Print the spooky dataset on my screen",
  # prints the dataset on the screen
  "3" : "Print this spooky dataset as a graph on my screen",
  #prints the graph as coded below! uses pandas and bokehs! 
  "4" : "HELP and FAQ",
  #A lovely help and FAQ page 
  "5" : "Exit",
  #self explanatory! This is the exit route. 
  
}

```
#####Pretty easy, all things considered. I often forgot a comma or a space here or there, which really messed up the code. But I was easy to fix, especially now that I know what the error messages mean. I found that this project was a lot easier to complete once I had consulted the class resources. 
#####There was another option, besides the “explore rows” function, that got cut for the sake of time as well. I was wondering about executing another option in the menu to define what the columns and rows were (for improved usability). For example, if you selected this option, then chose “Demonic_Type” as the column you wanted to know more about, the program would inform you that this column refers to the type of pact a person was alleged to be in (with the devil, obviously). 
#####Here is another code block from my project, which shows something I am still confused about (I took it from the class notes because it allowed the main menu function to work, but I am still unsure about HOW exactly it works): 

```
def get_menu_choice(choices_dict, prompt_str = "Make a selection"):
  # Print main menu and all choice labels and decriptions
  print("\nMain Menu")
  for label, description in choices_dict.items():
    print(f"{label}: {description}")
```

#####Why do we need a backing page on Trinket? Perhaps I will never know. I tried looking up the answer for myself with Trinket documentation but alas, no answer was found. 
#####My attitude towards this class changed a little bit as I worked on this project. There were highs (getting the main menu to work seamlessly) and lows (why won’t my graph work now? It was working a second ago) as well as worse-than-lows (realizing that my last few posts on the class website were NOT pull requests, as I had mixed up two different concepts completely). But there is a light at the end of the tunnel. 
#####I found that when I actually put time, effort, and thought into learning, things came easier. Instead of trying to trudge through the learning process, or worse, fight against it, when I sort of just allowed things to be confusing at first it went ultimately went better. 
#####This has some pretty big implications for the way that I see learning. What if the things I don’t think I’m good at are the things that I just didn’t allow myself to be good at? If you could have told high school Allison that she would be in a programming class – and not against her will – in graduate school she probably would have laughed. I thought I would be bad at computer science for so long that I waited forever to try my hands at it. I now see that things aren’t necessarily as hard as they make them out to be – I put up mental roadblocks. I wish I had this realization earlier in the semester, but sometimes the best is all you can do. 

####Conclusion 
#####I found that this project was not as intimidating as I thought it would be -- at least once I remembered that a backing.py tab is necessary on Trinket. I can't say I'm the biggest fan on trinket, mainly because I find it not helpful in terms of how Python actually works (note: I am not an expert, so take my words with a grain of salt. Maybe a giant block of salt. But I find that the way Trinket works is not as useful as just getting right into Python. I don't know -- those are just my thoughts. I also learned not to doubt myself so much. Maybe that's a conversation for my therapist and I, but the issue does truly affect my schoolwork sometimes (and my willingness to get said schoolwork done). Thanks for a great semester!

####Final project link again: https://trinket.io/python3/164a1e5ca4
####Bokehs and Pandas historian link --> https://programminghistorian.org/en/lessons/visualizing-with-bokeh
####Class notes --> https://trinket.io/embed/python3/8f70e6beb2
####Dataset link --> https://data.world/history/scottish-witchcraft/


![image](https://user-images.githubusercontent.com/114114819/206816236-b2402cf9-f08c-4b99-9105-8c4033260298.png)

