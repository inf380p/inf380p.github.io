---
layout: post
author: martsale
title: "Alexis's Final Project Interface"
---

# Final Project Week 1

I had two project ideas- use my spotify data or collect data about people's favorite music. I ended up going with the second option. Here is my original plan:
>For my final project, I want to create a data processing program focused on music. My stretch goal is to use my own data provided by Spotify, with creating an CSV as a back up. I'm not sure how quickly the data will get sent from Spotify, and I'm not sure what condition the data will be in.

>### Option 2: My Own CSV
>If I end up using a custom CSV, I want to start with albums that I like and albums that my friends like. Some categories I would include in the data would be album title, artist name, year released, genre, who submitted the album, number of songs or minutes of the album, and if it's owned in physical form such as a vinyl. I would have clearer data for option 2, allowing for more features while option 1 provides more "real-world" opportunity. Using these data points I listed above, I would try to follow this scope:

>1. Create the data in the CSV
>2. Design what the menu structure will look like
>3. Implement the menu code
>4. Allow the user to browse by the different categories
>5. Allow the user to select a random album, >from the whole list or within a parameter 
>6. Allow the user to visualize data such as albums by each artist, number of albums submitted by people, length of albums, etc
>7. Allow the user to calculate numbers similar to the visualizations 
>8. Refine the search/filter process

## A few changes
The most noteable change from the project plan and what I went with is using data collected via Google Forms. When I got my data from spotify, there was not a lot of metadata to work with, and the files were thousands of lines long.

In my original plan, I had mentioned calculating the average length of albums. This is not easy to collect that data so I won't be calculating that. 

I also ended up collecting the album or song, and then the artist. This will make the data a bit more interesting to sort through.

## Getting started with the menu

Creating the menu was fairly straight forward because it's pretty similar to the CSV project. My first issue was trying to assign the function value inside my `while` loop. After some brief ruminating, I realized I forgot to include `return` in the function. Adding `return` allowed me to get the value out of the function.

My second problem was not having any of the if statements run. Once I converted the `menu_selection` to an `int()`, the `if` statements worked as I expected.

```menu_selection = int(menu_options())```

My menu code is included below:
<iframe src="https://trinket.io/embed/python3/c19854ca17" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Updated Project Plan
1. Collect and create CSV
2. Sketch out menu architecture
3. Implement Menu Code
4. Import CSV to browse through the data
5. Create the first option of ways to browse
6. Create and implement help text
7. Allow users to choose a random music suggestion
8. Visualize some of the data
9. Create a function to allow users to filter music browsing by 2 attributes

## Expectations
For next class, I want to at least have items 4-6 done. Ideally I'll get more done, but I'm not sure what the data will look like when it comes into python. 

I think number 9, allowing filtering, will be a stretch goal. It will potentially be challenging to create the logic to filter down and have the user understand what is happening.

## After Class Discussions
After class today, I'm feeling pretty confident with my plan. One thing I might look at if I have more time would be including a data visualization package to make it more fancy. I know that's not a requirement, but it would make the project more fun for me. I'm excited for this project because using data from people I know makes it feel more sentimental and like I'm more connected to the data set. I'm looking forward to seeing what the actual statistics that I can pull out of the data are. 

One area that I"m a bit more aprehensive in is getting the CSV exported and to read into data well. I would like to do most of the data import by hand instead of using a package like CSV or Panda, but I also realize that might not be feasible will my skill level and the scope I've set out to finish. I could reduce the scope, but I'm excited to use the funcitonality of the proram.
