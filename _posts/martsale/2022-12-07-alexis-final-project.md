---
layout: post
author: martsale
title: "Alexis's Final Reflection"
---

# Final Project + Final Reflection

Overall, I enjoyed doing my final project. One thing that made it really enjoyable for me was collecting data from people I know and then creating my program based off of it. This kept it more interesting for me, and it was neat to see the different music suggestions. I brought value (for me at least) to this data by making it more readable and being able to filter down through it a bit. I've talked for a while about wanting to make a random music suggester, and this program did that. albeit with crowdsourced data instead of just the music I like. I thought it was interesting, and not surprising, that a lot of the music suggested was from 2010-2019. A lot of people I know would've been in high school and college during that time, and that's a foundational life stage to developing music tastes. 

Here is my final project:
<iframe src="https://trinket.io/embed/python3/5cc8a03b05" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Milestones
### Original Milestones:
1. Create the data in the CSV
2. Design what the menu structure will look like
3. Implement the menu code
4. Allow the user to browse by the different categories
5. Allow the user to select a random album, from the whole list or within a parameter 
6. Allow the user to visualize data such as albums by each artist, number of albums submitted by people, length of albums, etc
7. Allow the user to calculate numbers similar to the visualizations 
8. Refine the search/filter process

### Updated Milestones:
1. Collect and create CSV
2. Sketch out menu architecture
3. Implement Menu Code
4. Import CSV to browse through the data
5. Create the first option of ways to browse
6. Create and implement help text
7. Allow users to choose a random music suggestion
8. Visualize some of the data
9. Create a function to allow users to filter music browsing by 2 attributes

### Flow of Project Development:
1. Collected the data from people I know
2. Sorted the data and exported to a CSV
3. Created the menu code
4. Create the lists of categories and sort data into the lists
5. Allow users to browse code line by line
6. Create a function to format how each line of data is displayed
7. Allow users to get a randomly generated music selection
8. Clean up code and make sure it's easier to read
9. Visualize the data distribution of years suggested
10. Implement help text
11. Visualize the genre distribution
12. Allow users to choose what category to filter from and choose the first letter to filter by

## Scope Reflection

I really thought my scope was too big a few weeks ago, but the last few features ended up being pretty quick to implement. Once I got back in the swing of coding after Thanksgiving break, the problem solving came a lot easier. The last feature I added was the ability to filter by first letter. If I were to continue this project, I would want to expand upon the filtering capabilities.

## Challenges
### Returning Functions
One area of Python that I consistently struggle with is returning the value of my function appropriately. It doesn't seem to be the same problem every time, which makes it more difficult. The most recent example is that I tried to put the logic for choice 4, filtering through the data, in its own function. For whatever reason, as soon as it was wrapped in a function, the `for` loops wouldn't run. Seeing that this was the last feature that I added, I compromised and put it in the main code where it was at least working. 

### Converting Data Types
I discovered that Python doesn't let values from a list be added to a dictionary. The first thing I did was pull all the values into sorted lists by value type. For example, all artists were sorted into the `artists_list` list. When I went to create a dictionary to count how many times each genre appeared, I discovered I couldn't parse directly from the list into the dictionary after I looked up what a *nonhashable* value means. After learning that a list is nonhashable, I ended up reseparating the values and adding them to a dictionary when I separated them. If I had more time, I would want to refactor to see if I could combine splitting the lists with creating the dictionary. In order to add to a dictionary, I made each word a string and took out the list text like `['']`. I also needed to convert the year to an int when sorting the year list into smaller lists to visualize how many songs from each year were chosen.

### Creating a Dictionary
As I touched on a bit above, I struggled a bit with creating a dictionary. To make this more difficult, I realized that what I thought were dictionaries were actually just lists this week. I had named them things like `artists_dict` but set them up using `[]` instead of `{}`. I'm not sure how this slipped past me because I created them the week I finished the `dictionary` module. I had to go back into Runestone this week to look up how to set up a dictionary and use a dictionary to count because it had been a while since dealing with dictionaries.
```
def visualize_genre_counts_func():
  genre_counts = dict()
  for lines in function_line:
    word =  lines.split(",")
    genre_word = str(word[6:7])[2:-4]
    if genre_word not in genre_counts:
      genre_counts[genre_word] = 1
    else:
      genre_counts[genre_word] +=1
``` 

### Moving Functions to Their Own Module
As I was finishing my code, it was getting really long and complex to read. I decided to move everything that wasn' the actively running code to a separate module. I used the resource posted on the class website to determine that I wanted to use `from final_project_functions import *` to bring my modules in so I didn't have to worry about calling it every time I wanted to bring a function in. It took a little bit of trial and error to make sure I moved everything over, but it now runs successfully from a separate function. 

### Parsing Through the Data
It was difficult to figure out how to start parsing through the data. I did end up manually cleaning my data a little bit to make it easier to write code to transform the data. In my original csv file, a few of the lines were wrapped with "''" because there was a "," in the data. This was not consistently in the same area of data (for example, not always the artist column), so cleaning it through code started to grow into a larger problem than I wanted to focus my time on. After I cleaned up my data, it was pretty quick to sort it into lists based on the area of the line that it was located. When working out how to create the data format, I had 2 different sketches I was working from. In the first one, I tried to split it manually to remove the "\n" at the same time. It didn't work: 

<iframe src="https://trinket.io/embed/python3/3744514cce" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

For my second attempt, I used `readline()` and had success with splitting the data out:
<iframe src="https://trinket.io/embed/python3/63f0c3dc55" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Once I played around with this more, I put this code into a function that I was able to call:
<iframe src="https://trinket.io/embed/python3/5fb19505f6" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

```
#break up lines into entry specific lists
for line in function_line:
  line=line.strip()
  #create title list
  if line.startswith('Submitter'):
    line = line.strip()
    for word in line.split(","):
      title_list.append(word)
  #assign all other attributes
  else:
    words = line.split(",")
    submitted_words = str(words[0:1])[2:-2]
    music_type_words = str(words[1:2])[2:-2]
    song_name_words = str(words[2:3])[2:-2]
    album_name_words = str(words[3:4])[2:-2]
    artist_name_words = str(words[4:5])[2:-2]
    music_year_words = str(words[5:6])[2:-2]
    music_genre_words = str(words[6:7])[2:-2]
    
    #add attributes to dictionaries
    submitters_list.append(submitted_words)
    formats_list.append(music_type_words)
    song_titles_list.append(song_name_words)
    album_titles_list.append(album_name_words)
    artists_list.append(artist_name_words)
    years_list.append(music_year_words)
    genres_list.append(music_genre_words)
```


## Successes
Like any project- while there were challenges, there were also several successes. 

### Filtering Data
I was able to set the filter using 6 lines of code, which is very efficient code for where my experience is at. I chose to only go with the first character of the string to keep the options open and hope that users get some results for most of their searches. 
```
def filter_by_parameter(list):
  filter_letter_input = (input("Please enter a letter").upper())[0:1]
  for item in list:
    if item.startswith(filter_letter_input):
      item_position = list.index(item)
      print_data_function(item_position + 1)
```

### Using Lists to Count
In order to determine how many songs were from a specific range, I created new lists from the list of years. I divided the songs up over the course of decades to make the data more digestible to users. I converted the year list to an int, and used `if` and `elif` logic to append it to the appropriate year's list. Once the `for year in years_list` loop was done, I calculated the length of each list and printed out `*` x the length to represent the number of songs from that decade. 
I created a sketch of the code I would need to visualize the data. In this sketch, you can also see where I was calling variables a "dict" even though they were lists. Select option 3 to see the visualization code and where it started from:
<iframe src="https://trinket.io/embed/python3/c8793d48b9" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

```
def visualize_year_distribution_func():
  #assign year dictionaries
  for year in years_list:
    year_int = int(year)
    if year_int < 1980:
      decade_1970_list.append(year_int)
    elif year_int < 1990:
      decade_1980_list.append(year_int)
    elif year_int < 2000:
      decade_1990_list.append(year_int)
    elif year_int < 2010:
      decade_2000_list.append(year_int)
    elif year_int < 2020:
      decade_2010_list.append(year_int)
    else:
      decade_2020_list.append(year_int)
```

### Using a Dictionary to Count
I was really pleased with the function I wrote to filter results from user input. I used a few different examples from our textbook to refresh myself on dictionaries and help with the syntax, and adapted them to the needs I have in my code. I created the dictionary counting in a separate file as well in case I messed all of my code up. Here is the dictionary code I created before merging it with the final project code(option 3):
<iframe src="https://trinket.io/embed/python3/7850bf0778" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
This code shows how I was printing the data type to get the dictionary to fill in the way I wanted it to.

### Using an Infinite Loop
Similar to the CSV assignment, I used a `while ` loop to keep the main menu of my interface looping until the user chooses to exit. This way, the user is always prompted with some action.

## Debugging Skills I've Used Most
As in previous posts, `print()` is still my best friend when it comes to debugging tools. I really like that I can see what the program is trying to do, and it helps me see where it breaks or stops running. For this assignment, I've leaned heavily on `print(type())` to fix a lot of my errors. I was working with a variety of data types, and this was helpful to see why I couldn't use native Python functions when I wanted to(if I was working with the wrong data type). I also created a lot of my features in a one-off trinket to sketch the idea out for functionality, and then moved it into the final project.

## If I Had More Time to  Work On It
If this was a longer project, I would want to try and create a basic search function that would compare user input with list data. I would also want to build out the filter capabilities a bit more, searching for whole words or numbers instead of just the first value. I would also use the CSV function and potentially import a data visualization module. However, doing all of the parsing by hand really helped me refine my skills for this project. I would also want to refactor and see if I could make my code more efficient.

## In Conclusion
I learned a lot from this project and I feel more confident in my ability to write and debug Python code. I would like to continue using Python, potentially finishing out the textbook. It feels really good to have a program with working features. I was going to say completed, but I'm not sure any program is truly ever done. I'm glad I took the time to sort the data by hand to truly understand string and list parsing, and I'm ready to move on to using packages I can import that will run a lot of the features for me so I can dive into deeper functionality. 
