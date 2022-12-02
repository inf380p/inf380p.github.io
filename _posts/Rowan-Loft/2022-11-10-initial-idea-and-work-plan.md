---
layout: post
author: Rowan-Loft
title: Rowan-Loft's Initial Idea & Work Plan
---

For my final project, I will be looking to create a user-navigable program for a sample size of public commercial and (tentatively) non-commercial airports in the United States. I say a sample size because there are over 5,000 public airports, and this program will specifically not include all other airports in the US, as the number jumps to just under 25,000.

There is already a present and up to date .csv containing data that provides information on open airports, closed airports, and helipads in the US that is produced by the United Nations Office for the Coordination of Human Affairs (OCHA). The list will have to be truncated to some extent as I'm not interested in closed airports and helipads, which contribute to the files' just-under 30,000 rows of data. Further cutting will have to be done to account for some information that would not be pertinent to someone navigating the program such as elevation, longitude, and latitude of an airport. 

This .csv is particularly messy in that there is no rhyme or reason to how it is ordered. My program would-in theory-allow users to navigate airports by size (the FAA has 4 classifications of airport size), states, municipality, and other keys, making the .csv more human readable and useful. This will include scrubbing *some* data from the raw .csv, selecting a reasonable sample size, assigning keys, creating a user-navigable menu, and adding functions to the menu that allow users to manipulate the .csv in different ways. 
