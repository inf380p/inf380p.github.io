---
layout: post
author: unixEnthusiast
title: "Nikhil's Final Project and Reflection"
---

# Final Project and final reflections

As a final tribute to an awesome class, I decided to test all (most) of the skills I had aquired creating a trinket program to analyze a complex set of Formula 1 (F1) CSV data and make some sense of it. I'll explain in detail the various concepts used and the challenges I faced along the way but overall, it has been a humbling and satisfying process to finish this project and I'm quite happy with the final product. Hope you stick around to explore and enjoy the analysis!

## Introduction

I wanted to do a data analysis project as I love the sport of F1 and the plethora of data analysis done by the many pundits online. I wondered if I could create a program to not only enable users to explore the raw data in this distributed datasets, but also to provide some interesting analysis and custom plots making the whole experience even better.

The project can be broken down into the following components for better understanding:
- Collecting the data for the analysis
- Exploring the raw data and cleaning it for analysis
- Loading the data and reading it in trinket
- Creating the Interface for exploring the data
- Creating various helper functions to analyze the data
- Creating helper function for detailed analysis and plotting the graphs
- Finishing documentation and code cleanup
- Testing and verification

Let's take a look into these steps and see where we stand.

## Gathering data for analysis

After searching for clean and reliable sources for the analysis, I was able to find the following repository which contained detailed but distributed datasets:
https://www.kaggle.com/datasets/rohanrao/formula-1-world-championship-1950-2020

The dataset consists of all information on the Formula 1 races, drivers, constructors, qualifying, circuits, lap times, pit stops, championships from 1950 till the latest 2021 season. The data was clean and without any obvious errors and also in CSV format.

## Data Exploration and Cleanup

Despite the data being in a clean condition, I had to make sure, we were analysing a smaller subset of the data. The overall dataset contained over 30000 rows of data which made the process of loading the data and doing complex analysis difficult. I trimmed the result dataset by not including columns like points, fastest lap number etc and also restricted the analysis to the results where the driver obtained a podium finish i.e. his position was 1, 2 or 3. 

This greatly reduced the data size t oabout 3000 rows which can be analysed fairly quickly by the trinket system. After this cleanup, I decided to take the additional datasets of race information, driver information and constructor information for the analysis.

## Loading the data and reading it in trinket

I was able to read the data and load it into the program by creating a list of dictionaries for each dataset. This enabled the list to be dynamic and the data to be read into the list with each row being a dictionary with key value as the column name and value being the value.

For e.g. following is an example of a dictionary entry into the overall list of results:
{'resultId': '1', 'raceId': '18', 'driverId': '1', 'constructorId': '1', 'position': '1', 'points': '10', 'laps': '58', 'milliseconds': '5690616', 'raceTime': '01:34:50.616', 'fastestLapTime': '01:27.5', 'fastestLapSpeed': '218.3'}

The function to load the data and the corresponding headers into a dictionary:

```python
def get_dicts_list_and_headers(filename):
  
  with open(filename) as file:
    reader = csv.DictReader(file)
    dicts_list = list(reader)
  
  headers = dicts_list[0].keys()
  
  return dicts_list, headers
```

This was repeated for the files: "results_updated.csv", "races.csv", "drivers.csv" and "constructors.csv"

## Creating the Interface for exploring the data

As explored in a previous reflection, the interface was created to explore the dataset and do custom analysis for a particular constructor(team), year or driver. It also consisted of an option to open detailed instructions and to close the program.
The interface uses an infinite while loop with a break condition input to exit the program but with any of the other inputs, the user can play with the analysis as much as they want.

## Creating various helper functions to analyze the data

The main aim of the program was to enable exploratory analysis on the vast dataset as well as provide custom analysis on a particular aspect of data. Hence, the following helper functions were created to help with the analysis:

### Explore the results:

Once the user decides to either select the first row, a random row or a particular row number to analyse, the row was selected from the result dictionary list for analysis. This was done as follows:

```python
if(choice_str == "1"):
    # Browse race data from results file
    # User can pick any row or give their own number or select a random row
    if interface.input_is_yes("Start from row one?", default = 'y'):
      # First row in the list is at index 0
      first_row_int = 0
    else:
      if interface.input_is_yes("Return a random result?", default = 'y'):
        first_row_int = random.randint(1, len(result_dicts_list))
      else:
        first_row_int = interface.get_valid_row_num(result_dicts_list)
  
    # Loop through the list of row dictionaries, starting at the selected first row.
    for row in result_dicts_list[first_row_int:]:
      print_result(row)
      if interface.input_is_yes("Continue to next result?", default = 'y'):
        continue
      else:
        break
```

The result helper function is quite intersting as I could have stopped at just providing the result row to the user but it would contain non useful information like race-id, driver-id and constructor-id. It was important to essentially 'join' the datasets of races, drivers and constructors to results to get this data. I used the filter function to filter the various datasets with the correct IDs to be used for cross refrencing. For e.g. to get the correct race information for a particular result, I would do the following:

```python
filtered_race_list = filter(lambda d: d["raceId"] == result_row["raceId"], race_dicts_list)
race_dict = next(filtered_race_list, None)
```

The race dict provided by this filter will contain the same raceID as in the result row. Hence, this race_dict dictionary can be used to get the name of the race for this result. As following:

```python
print("Race: ", race_dict["name"], " Year: ", race_dict["year"])
```

Similar logic is used to get the name and nationality of the driver and constructor for this result. It was quite intersting to filter the dataset to get the required result. I suspect this may be inefficient and quite memory intensive as the size of the dataset and filtering increases and hence some kind of database operation would be better where joins can be applied using 'INNER JOIN' to appropriate keys and then queries can be filtered using 'WHERE' clause.

### Constructor Analysis

A similar analysis was done for constructors. After prompting the user for the team name and validating the name, similar filtering was done to get only the rows from result list whose constructor ID matched the constructor ID for the team name entered. If there exists results for such a team, the resultant result list is analysed. A helper function provides the various metrics like first, second and third place finishes, average fastest lap speeds and finally drawing a plot of the average speeds over time. Year data was also gathered by cross referencing the race dataset and added to the list and the list was ordered according to the year. These helper functions are explained in a later section.

```python
#getting and compiling the correct race information
filtered_result_list = filter(lambda d: d["constructorId"] == constructor_dict["constructorId"], result_dicts_list)
```

### Yearly Analysis

Yearly analysis also follows constructor analysis but filtering on the basis of the year which the user enters. Validation is done here to make sure the entered value is between 1950 and 2022.

```python
#getting the correct race information
filtered_race_list = filter(lambda d: d["year"] == year, race_dicts_list)
```

After filtering the data, similar metrics are obtained and sent to the user.

### Driver Analysis

Driver analysis is also siilar to the constructor analysis but the filtering is done on the basis of the driver ID which corresponds to the name of the driver entered by the user.

```python
#getting the correct constructor information
filtered_driver_list = filter(lambda d: d["fullName"] == driver, driver_dicts_list)
driver_dict = next(filtered_driver_list, None)
```

once the correct set of results are obtained, we can filter the correct set of races and gather metrics for the analysis. Finally the result is sent to the user as follows:

```python
print("\nHere are some results for the driver: ", driver)
  if(num_records == 0):
    print("First Positions: ", first_positions, " Second Positions: ", second_positions, " Third Positions: ", third_positions)
  else:
    print("First Positions: ", first_positions, " Second Positions: ", second_positions, " Third Positions: ", third_positions,
    " Average Speed: ", round(total_speed/num_records, 3), "Km/Hr")
    
    #plotting the speeds over the years
    plot_graphs(filtered_result_list, driver)
```

## Creating helper function for detailed analysis and plotting the graphs

I created two helper functions, the first for gether metrics for analysis and the latter for plotting the data. The first helper function iterates over the result list sent and aggregates information like the total number of first, second and third position finishes and the total fastest lap speeds. This can then be used to determine the average fastest lap speeds over their entire career.

```python
#returns common used metrics for a list of race results
def race_analysis(race_list):
  
  num_records = 0
  total_speed = 0
  
  first_positions = 0
  second_positions = 0
  third_positions = 0

  for dict in race_list:
    
    if dict["position"] == "1":
      first_positions += 1
    elif dict["position"] == "2":
      second_positions += 1
    else:
      third_positions += 1
      
    if dict["fastestLapSpeed"] != '':
      total_speed += float(dict["fastestLapSpeed"])
      num_records += 1

  return first_positions, second_positions, third_positions, num_records, total_speed
```
For plotting the data, I wanted to do a time based analysis, analysing the variation in fastest lap speeds for constructors and drivers over a period of years. I reseasrched and found the matplotlib python library suitable for my requirements. Given a result set, it is able to extract the data into X and Y axis lists for analysis. This can then be sent to the scatter() function to plot the various points over the years.

```python
#plotting the fastest lap speeds over the years
  result_list = [d for d in result if d["fastestLapSpeed"] != ""]
  
  x = [int(d["year"]) for d in result_list]
  y = [float(d["fastestLapSpeed"]) for d in result_list]
  
  plt.clf()
  plt.title("Fastest Lap Speeds for " + str + " over the years")
  plt.scatter(x, y)
```

I also wanted to plot the trend line for this analysis. The numpy package is able to plot a n-degree polynomial trend line for any scatter plot. Hence, I used this package to draw trend lines for the plots.

```python
# Fit a polynomial trend line to the data of degree 1
  z = np.polyfit(x, y, 1)
  p = np.poly1d(z)
  
  # Add the trend line to the plot
  plt.plot(x, p(x), "r--")

  # Show the plot
  plt.show()
```

This created a straight line for the trend analysis.

## Finishing documentation and code cleanup

After finishing the intended functionality, I made sure to clean the code as much as possible and follow the DRY principle of "Don't repeat yourself" I was able to reduce the code complexity and size by making helper functions and reusing them instead of redoing the whole logic again. I made sure to add the required comments at crucial points to make sure the reader has a good idea of code logic and can follow the process flow properly.

## Testing and verification

Once code cleanup was done I tried to play around with the inputs and put the program to test by providing edge cases like giving string inputs instead of years, incorrectly capitalized names for teams and drivers etc. This brought out a lot of vulnerabilities in the process flow and for this reason, I tried to raise the appropriate responses to the user whenever the input in not compliant and fixing the user's input capitalization errors. This was quite interesting as I can seee direct usage of such validation logic in the real world where people enter their email addresses, phone numbers etc into web interafces and this data must be validated before sending it for processing. This will save valuable time and effort.

## If I had more time to work on this..

I really got into the debugging and segemntation of problem task into snmaller pieces and was able to get a lot more throughput than I expected. My initial goal was to just do an analysis but then I was able to add a plotting functionality to the code which really enhanced the analysis done. I believe I would definitely dive deeper into the plotting and visualization aspect as well as optimize the code to handle bigger dataloads effectively as well. The possibilities are endless!

## Conclusions

I thoroughly enjoyed the semester full of learnings and surprises and was glad to finish with such a high. I hope to continue working on better and more detailed data analysis projects using python and it's many packages and libraries. As an aspiring data scientist, this fills me with great curiosity and excitment for the future!

## Trinket Code

Please find the embedded trinket program here. Run the analysis and have fun!

<iframe src="https://trinket.io/embed/python3/422e1b1c27" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
