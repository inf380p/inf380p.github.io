---
layout: post
author: manasvini2906
title: Manasvini's Final project submission with reflection
---
Code: <iframe src="https://trinket.io/embed/python3/951990004c" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Hi everyone !

In my final project, for the course "Introduction to Programming" I decided to take the data analysis track. Since I am an aspiring data scientist, 
this project really helped me solidify my basics, and stregthen my foundation in key conceptual areas. I have always been very intrigued by climate change, and
for my project I wanted to analyze if different places with varying socioeconomic factors face the same pollution as everyone else.

About the dataset:

**What is CalEnviroScreen?**

CalEnviroScreen is a mapping tool that helps identify California communities that are most affected by many sources of pollution, where people are often especially 
vulnerable to pollution's effects.

CalEnviroScreen ranks census tracts in California based on potential exposures to pollutants, adverse environmental conditions, socioeconomic factors 
and the prevalence of certain health conditions. Data used in the CalEnviroScreen model come from national and state sources.

The dataset is pretty huge, and has a comprehensive list of features. The original dataset had around 30 columns and 8000 rows. 

For the purpose of this project, I wanted to analyze how 'Lead', 'Poverty', and 'Umemployment' in each county is related to the CES Score.

Data Dictionary:

Draft CES 4.0 Score: CalEnviroScreen Score, Pollution Score multiplied by Population Characteristics Score
Lead: Potential risk for lead exposure in children living in low-income communities with older housing
Poverty:	Percent of population living below two times the federal poverty level
Unemployment: Percent of the population over the age of 16 that is unemployed and eligible for the labor force

There are four key concepts I learnt over this project:

* Exploratory data analysis; using pandas
* The importance of removing outliers; IQR method
* Groupby; plotting the mean over groups
* Regression Analysis (Bivariate Analysis)

First I started by importing important packages that enabled me to easily navigate through my project:

```
import numpy
import matplotlib.pyplot as plt
import pandas
```

Next I wanted to gain an overview about my dataset after importing the csv file:

```
# Load data
df = pandas.read_csv('ces_score.csv')


#converting the csv file to dataframe, for data manipulation
df = pandas.DataFrame(df)


#getting the dimensions of the dataset
print('Dimension of the dataframe : ', df.shape)

#getting the top 5 rows
print('Top 5 rows:', df.head())
```

Next, I wanted to perform univariate analysis. That is get the mean, standard deviation, minimum, maximum and count.
So I initiated user input, giving the user the choice of feature for which they want the decriptive statistics. This is something new I learnt in class! I had never used input
before. So this was a cool new thing I learnt.


```
options = ['Lead', 'Poverty', 'Unemployment', 'DRAFT CES 4.0 Score']

user_input = ''

q1 = "Pick an option:\n"

for index, item in enumerate(options):
    q1 += f'{index+1}) {item}\n'

q1 += 'Your choice: '

while user_input not in map(str, range(1, len(options) + 1)):
    user_input = input(q1)

print('You picked: ' + options[int(user_input) - 1])

if q1 == "1":
  print(pandas.DataFrame(df.describe()).iloc[:,0])
  
elif q1 == "2":
  print(pandas.DataFrame(df.describe()).iloc[:,1])
  
elif q1 == "3":
  print(pandas.DataFrame(df.describe()).iloc[:,2])
  
else:
  print(pandas.DataFrame(df.describe()).iloc[:,3])
  
```

Converting df.describe() to a DataFrame, I could easily slice it and get the column I wanted using iloc. I learnt a cool way to use data manipulation, using user's input.

After getting the descriptive statistics for the said feature, I wanted to check if my subset of the data had outliers in it.

I did some research on how to detect and remove outliers. In the process, I learnt that plotting is a great way to immediately detect outliers. There are several methods of
dropping the outliers. Predominantly Z score and IQR method is used. I went ahead with the IQR method for my project.

**Context about Outliers**

_An outlier is an observation that lies abnormally far away from other values in a dataset.
Outliers can be problematic because they can affect the results of an analysis.
However, they can also be informative about the data you’re studying because they can reveal abnormal cases or individuals that have rare traits.
Outliers usually are present outside 1.5 times the interquartile range above the upper quartile and below the lower quartile 
(Q1 - 1.5 * IQR or Q3 + 1.5 * IQR)_

For my dataset, I used box-plot to see if the column  'Lead' had outliers. It looked like it had tons! As I plotted using subplot, I appreciated how matplotlib paved the way for data visualiation.

```
plt.subplot(1, 2, 1)
plt.boxplot(df['Lead'])
plt.title('With Outliers')
plt.show()
```

I used the InterQuartile Method to remove the outliers. 

**Context on IQR**
In descriptive statistics, the interquartile range tells you the spread of the middle half of your distribution.

Quartiles segment any distribution that’s ordered from low to high into four equal parts. 
The interquartile range (IQR) contains the second and third quartiles, or the middle half of your data set.

In a boxplot, the width of the box shows you the interquartile range. 
A smaller width means you have less dispersion, while a larger width means you have more dispersion.

An inclusive interquartile range will have a smaller width than an exclusive interquartile range.

The interquartile range formula is the first quartile subtracted from the third quartile:

IQR = Q3 - Q1

Q3: Third Quartile/75th Percentile
Q1: First Quartile/25th Percentile

After calculating the IQR, I just dropped the rows where the Lead values were more that Q3 + 1.5(IQR) and lesser than Q1 - 1.5(IQR).

This reduced the number of rows, as I ran df.shape again. This indicated that outliers were removed.

After the outliers were removed I plotted box-plot again to check, and the outliers were negligent.

After performing univariate analysis and outlier detection and removal, I wanted to explore advanced concepts like groupby and regression mmodels.

For understanding groupby, I plotted the average CES score over California Countys. 

San Bernardino has the highest avg CES score, while Orange County has the lowest. And just as I rightfully hypothesized, Orange county is more expensive and posh while San Bernardino is 
more affordable. I believe this is a good indicator that wealthier the neighbourhood, lesser the pollution. Which makes sense if you think about it, most companies set up their sweatshops
in third world countries! From gucci to kylie jenner's make up line, everything is made in Bangladesh. It was surprising to me that socioeconomic factors that differentiate 
counties (making it a very niche arguement; instead of looking at it country wise), can also make a difference in the CES score.

Here is the code I used for groupby:


```
#Using groupby to plot the average CES score over California County
df_region = df.groupby(by=['California County'])
df_region = pandas.DataFrame(df_region.mean())


CES = numpy.array(df_region['DRAFT CES 4.0 Score'])

fig = plt.figure()
#adding axes to the figure
ax = fig.add_axes([0,0,1,1])

ax.set(ylim=(0,60))

reg = df['California County'].unique()

#Y-label
plt.ylabel('CES Score')
#X-lable
plt.xlabel('California County')

plt.xticks (rotation=75)

#title
plt.title('average CES score over County')

#creating bar-plot
plt.bar(reg,CES,width=0.5,color='blue',alpha=0.7)

#saving the figure in .png format
plt.savefig('plot.png', dpi=300, bbox_inches='tight')
```

AND for the final and the most ambitious part of my project, I wanted to run regression models; and try to gain insight on whether a feature plays a significant role
in predicting the target variable. I also used the summary report to get the coefficients, F-statistic and R-squared value to see how well fit the line was.

For this portion as well, I used the user input and based on the input you would get the bivariate analysis report.
The features I used for this were Lead and Poverty and based on the R2 scores, Poverty explains the variability more. 

Overall through this project, I learnt a LOT of key concepts used in data science and analysis. When I started the project, I was motivated to perform a lot of exploratory analysis,
using different kinds of charts and graphs. But I read that data preprocessing is the most important step, along with visualization. Hence I preprocessed, visualized and also ran a regression model.
I loved how efficient I have become in debugging, noticing my mistakes quicker and solving them.

I hope you enjoyed reading my reflection!



  
  



















