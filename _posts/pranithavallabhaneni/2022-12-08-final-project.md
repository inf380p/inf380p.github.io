---
layout: post
author: pranithavallabhaneni
title: "Pranitha's final project
---


**About my program**

Since I came from a medical background and willing to specialize in *Health Informatics*,I would like to utilize my skills learnt in this class for my final project which is based on Health Data analysis and I named it as **Health, Population and Education Statistics**. 

**Milestones**

- [x] Find datasets that are aligned with the scope of the project. 
- [x] Think of how the data needs to be represented to the user.
- [x] Create a sketch of the program flow.
- [x] Start coding to show the available options and take in user input.
- [x] Read the csv data as per user selection
- [x] Find and explore necessary libraries that help to represent data to the user.
- [x] Pick one library functionality and implement it on one dataset.
- [x] Expand the scope of visual data representation of csv data with various library functions
- [x] Implement all the various visual data representations for other data sets based on user selection
- [x] Test the program flow.

**My Project**<br><br><iframe src="https://trinket.io/embed/python3/a4de6a70a9" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe> 



**My Reflection**

Introduction to programming is my first ever course which exposed me to the world of programming. It was really a great experience getting started with coding. I have learned a lot during this course and this course taught me how to think and how to implement a logic in code for a problem. I would like to discuss more about my learnings in this reflection.
 
When I first saw the project description, I was really unsure which project to choose and how to start with the project. Since my background is related to Health Sciences I wanted to think about a data analysis project with health data set. 
Since I came from a medical background and willing to specialize in Health Informatics,I would like to utilize my skills learnt in this class for my final project which is based on Health Data analysis. Upon further investigation I was able to find a place to search for health related datasets from a data bank which I have cited in the reflection. Although some of the data isn’t complete and doesn’t fit my needs, I had to spend some extra time searching for the right data set that would help me build a nice final project. The dataset I finally found is related to health, education and population statistics of the past few years from different countries and regions
Once I got the right dataset, I thought of naming my project as Health, Population and Education Statistics Dashboard.

The next big thing is to think of how do I start the project. This was the beginning of my project which included thinking of what data to use and how to represent the data. I was unsure of where to start from. Based on the project update task I figured out that the next thing I should be thinking is about how a user interacts with my project. It is at this point I started thinking of the design and how the data could be visualized by the user.
I have created a set of milestones which would help me track the progress of my project. As stated in my previous reflections these milestones were being updated as I make progress on the project.

With an idea of the drafted interface in my mind I moved forward in identifying various supported third party modules like Pandas, Pyplots etc which would be used to show the data in proper representational formats that are easily understandable by the user. After I researched about these libraries from various sources and learnt about them, I have started playing around with pandas, matplotlib and started exploring them with various examples. To explore those functions it took me a lot of time to understand initially and then after running into several errors trying to implement and understand the functionality of these function I was able to succeed the task of representing a dummy set of values in a graph, barchart., I made progress on the code to read the respective csv files based on the user selections and then pass the data to the python functions to represent the data from one data set. 
Reading of the csv files was little easy this time since we have had an assignment earlier which helped me better understand how csv file reading works. This made my work a little easier on reading the csv datasets.

I started my program with a iterative interface where the user will be given options to select iteratively until the user exists the program. I have created custom function which would plot the physicians data within a graph. I later realized that since the physicians data is shown for all the countries, it would be ideal for me to represent the data as the bar chart instead of a plot graph and hence I updated the visualization to represent the bar chart instead of a graph. This was really a good learning for me as this helped me think on how the data should be represented based on the type of the data.
My next step was to implement a new visualization functionality on a different dataset. For this part I have chosen to use the population data set which has population information of men and women for a few countries and the world as whole for the years 2013-2021. My initial thought on showing this data is in the form of bar chart but with two barcharts side-by-side (one representing men and the other representing women with different colors) for each country for a specific year. For this I had to do search sources on how could I achieve this behavior of representing two bars for each country. I have cited the source which helped me understand the implementation of this functionality. When I went ahead and implemented this functionality within my project, the result plot wasn’t as per my expectations, the Y-axis data isn’t in a proper order. I wasn’t sure what went wrong for a lot of time. Upon further investigating I realized that the values on the Y-axis are of type ‘str’ but not ‘int’ and hence the plot graph isn’t showing the ascending order of the Y-axis values. This was really tricky for me to understand this problem. I then typecasted the str values to int and then proceeded with the next step.
```
men.append(int(row[idx]))
# here men is a list of population number values which is represented on Y-axis
```

The next step in my process was to use the education data and represent the education data set as a bar chart. By the time I started implementing it I was clear on how to implement the bar chart and this took very less time implementing this functionality.

Moving forward I wanted to expand the functionality of my dashboard with various datasets. Hence I also picked a data set that has the incidences of Tuberculosis for 100K people in various countries. I have implemented the same bar chart functionality on this data set as well.

Later I wanted to try different forms of visualizations and inorder to do that I had to think of few other usecases that fits my datasets. This is when I thought of adding additional user options in the program for each dataset so that the user can choose on what data to be shown.

As the Health Statistics functionality now has two choices to choose from one being Physicians data and the other being Tuberculosis data, I thought of implementing a graph like visualization on growth of population year by year for a selected country. After this I also implemented a pie chart representation of the men and women population in the world for a selected year by the user. 
The Matplot library and other sources which I have cited below really helped me a lot to better understand on how to implement the visualizations in Python.

I have tested the flow of the program every time I implement a functionality. If there were any errors, I used to follow the output screen and figure out where exactly the error happened, put some print statements to understand the values and debug the program. As a part of this when I was testing the iterative approach of user inputs, I noticed that the plots overlap on each other causing chaos. I then figured out a way to clear each plot upon representation in the output. I referred the matplotlib documentation to figure out this function.
```
plt.clf()
```
Later, when I was testing the pie-chart I figured out the pie chart is only seen with the labels but not with the percentages on it. I had review the documentation and other sources on what parameter to add in order to see a percentage on the pie chart. Now comes the other issue as there is no decimal points after the percentage and the pie-chart just shows a whole number. Upon further research I found that using the following parameter helps me get upto 3 decimal points.
```
plt.pie(data, labels = label_names, autopct='%1.3f%%')
```
At this point, I have got the functionality I needed. Upon reviewing my code, I found few repetitive functionality in my code which I later modified and consolidated the code so that a single function would handle the functionality of the bar chart representation. I created a function bar_chart which takes in few parameters and this function is now being called by multiple functions.
```
def bar_chart(xdata, ydata, xlabel, ylabel, title):
  """
  This function plots bar chart based on the input parameters.
  This function will be used by other functions in the program,
  """
  plt.clf()
  plt.bar(xdata, ydata, color ='maroon', width = 0.4)
  plt.xlabel(xlabel)
  plt.ylabel(ylabel)
  plt.title(title)
  # Shows the plot in the output
  plt.show()
  ```
Apart from this I have added a help() function which would give the direction to user upon selection of “Help” on how to use the program.
This project gave me a better understanding of how important designing an interface is, and how drafting milestones and planning ahead will help you achieve your target during a project execution. It also helped me to figure out things on my own and think logically when an error occurs during program rather just making invalid guesses on what went wrong.

Overall it was a great experience for me working on my first ever coding project that is well aligned with my area of interest. I am looking forward to learn and create more projects in Python.








**References:**

https://databank.worldbank.org/

https://matplotlib.org/stable/plot_types/basic/index.html

https://pandas.pydata.org/docs/reference/api/pandas.read_csv.html

https://numpy.org/doc/stable/reference/generated/numpy.array.html 

https://www.geeksforgeeks.org/plotting-multiple-bar-charts-using-matplotlib-in-python/ 

https://www.geeksforgeeks.org/plot-a-pie-chart-in-python-using-matplotlib/ 

https://www.geeksforgeeks.org/reading-rows-from-a-csv-file-in-python/ 

https://www.geeksforgeeks.org/dealing-with-rows-and-columns-in-pandas-dataframe/ 


