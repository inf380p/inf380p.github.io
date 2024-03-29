===
layout: post
author: Stuks
title: Stuks' final project!!
===



#Completed Final Project: NYC Zip Code/Gender Data Analysis:


<iframe src="https://trinket.io/embed/python3/71c18aa9f3" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


##Reflection / Recap:

So lets begin.

My original idea for this data analysis program was to create a trinket that can go through a bunch of emails and highlight information that could be used to be redacted. Unfortunately, I spent a lot of time looking for bunches of emails and couldn’t really find any. I got individual ones but there was no way I was going to be able to scrap together 100 and honestly, I was getting worried I wouldn’t be able to complete this work.

I switched over to work with a CSV that collected demographic information related to NY Zip Codes (male/female). It was a bit large so I cut it down to about 200 lines and focused on the male/female ratio as well as the borough.

My goal was to create a simple system that can tell you:
1)	How many men/women responded to this survey
2)	Per what Zip Code
I also added a two additional options along the way as I thought it would be a bit more interesting:
3)	Identify a zip code’s borough – basically, you put in a zip code and it will tell you what borough its from or if its not from NY.
4)	Random – Just pull a line of code from the CSV at random. It seemed silly, but I knew that the random aspect will make it a bit challenging for me to code, so I wanted to give it a go.
I struggled a bit at the start trying to input the csv file, actually, but I eventually got around it by making opening a txt file of the excel spreadsheet and copying it into python.

MY first steps were,  lets try and get some simple stuff up. Before even trying to pull info from the CSV I wrote out the dictionary and created the 7th and 8th option: help menu and end. It worked pretty well, but as you may notice I have a function for both of these instead of them being together inside just one. I’ll explain more on that later.

<iframe src="https://trinket.io/embed/python3/b15805130b" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

When I finally created a function to pull from the csv data, I went through it row by row and printed out the rows from 0 to 6. This was for the first option the General Zip Code. By setting the if statement to row 0, my thought processes was that if the user entered in a zip code on the list in row 0, it would pull all the data up. And it did, but I had some issues where invalid zip codes didn’t’ do anything.  More on th9s later.

When that function worked though, I went through made functions for the Generate Male, Female and Borough Data. It worked on the same principle, but I really didn’t like having so many functions. The same issue of faulty zip codes crashing the system was still present. I also needed to figure out a correct way to prompt the ‘incorrect input’ command when someone entered 9 or a letter.

It was progress though.

<iframe src="https://trinket.io/embed/python3/caceec61ac" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

In order to address the issue of zip codes incorrectly prompting nothing, I added an else statement to the end of this first function to just state if the zip code was a valid NYC zip code or not. I still had some issues (for example, there are certain NY Zip Codes that just were not included in the original CSV for some reason, which were now being labeled not valid NYC zip codes. I put a pin in that for now and thought I’d revisit that when I go back to the zip code identifier .My first attempts used code like:

def generalzip(zc):
  with open('zip_code_demographics.csv','rt')as f:
    data = csv.reader(f)
    next(data)
    for row in data:
        if row[0] == zc:
          print("Zip code:", row[0])
          print("Paticipants:", row[1])
          print("Total Females:", row[2])
          print("Percent Females:", row[3])
          print("Total Males:", row[4])
          print("Percent Males:", row[5])
          print("Borough:", row[6])
        else row[0] !=zc:
          print("This is not a valid NYC Zip Code.")

I believe the issue this had was it checked every zipcode on the list and if it didn’t match it would print out “This is not a valid NYC Zip Code.” This lead to about 200 inputs of that line. This was me just not really thinking about how the else would interact with the for loop, I had thought that by saying else row[0] doesn’t equal the zipcode input, it would just cancel. But it kept looping through.

So I decided to try and make a function instead of editing the loop, I created zipcheck as a way to check to see if the zipcode was actually in row 0. If the user put in a zipcode that was in row 0 on the CSV file it would return as true then and continue with the other functions like pull the male/female data. If it wasn’t, I set it to false and had the error message play. And it worked! I was really excited; this had been bugging me for a few days prior.

<iframe src="https://trinket.io/embed/python3/66cc6ffa33" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

At this point I had set some goals for me to try and work on over the next few days:

Condense my code: I don’t like that I have functions for each of these selections. I want to get these together in a much more condensed way as I don’t think its necessary to have all of these functions floating around. I would like to extend my current functions into a new file a .py like a helper file, but I’m a little concerned given the issues I had with loading in the CSV at first.

Get the data visualization up: I want to have the Male/Female Raito be where I can visualize the data (since the others are just single values). I’m putting this off though until I can get the other functions up and running. I’ll have to return to this later.
Get random going: Another issue, I think I was incorrectly trying to call the random function. I was getting a len error on a line of code listed as 379, which I didn’t understand because neither of my codes went up that far.

I was also still having some slight issues with the zipchecker when it ran through the Zip Code Identifyer function. While it worked most of the time being able to tell if the zip code was a valid with data or not, it was still incorrectly assigning certain zipcodes to be ‘Not from NYC’ even though they were (10008 for example is just not present on the original CSV, and despite being a NYC Zip Code, would come up saying it wasn’t.) I  thought about just changing the print message to ‘No data’ but I felt that wouldn’t be enough so I said I would revisit this later.

The menu itself was still gross, but that was something I had agreed to wait until the end to fix.

However, after this I ran into a bit of a conflict. While discussing my code with a friend of mine who is a programmer, I mentioned that I had used the template code that was shared in class. When I told him this, he mentioned that I may get flagged for plagiarism. Apparently it happened to him in the past and he said it’s a bit common for things like that to shoot up in coding because there is a lot of sharing of code.

This kind of set me into a bit of a spiral. Its no secret I’ve been struggling this class and I already know that my data analysis is not the most complex. But I was happy with what I had made. But now I’m thinking my code is going to be rejected and I might even fail due to a plagiarism strike. I started to panic and tried to scrap together a second program basically last minute, trying to make a quick Turtle text based game… but needless to say, that was a mess and I honestly had no idea what to do.

From this experience I definitely learned to take a minute and chill. While in a panic I came across a line of text in the description that said you could, in fact, use the code provided during class. It was such a wave of relief, I can’t even begin to explain. But I had wasted a few days in a panic so now I needed to pick up and really get through with crunch time. But I definitely took sometime to just relax. I’m a really anxious person, and when dealing with subjects I’m not comfortable with, it makes everything even 10 times worse. But I really need to learn to take a minute and slow down in the future, I could have saved a lot of heart ache if I had just re-read the page. I knew I saw that somewhere!

When I returned to work on the code, I decided to turn my attention to the random function. I tried using the random.choice(csv.reader) and random.choice(generalzip) but neither of these codes were working. I was a little unsure but my thinking because I wanted to pull all the data like I would through my general zip pull, I needed to somehow call the function for random first, so it will randomize the data I was pulling? But I was worried that would just pull actual random data, which wasn’t what I wanted. I just wanted a random zipcode pulled.

So I was thinking since general zip is already pulling this data, what I want to randomize is the data it pulls from the first row. I fooled around for a bit until I was able to assign the row to the random choice option. And it worked, when I assigned the generalzip the row0 that had been randomized, it started picking it at random. This actually wasn’t as difficult as I had originally thought.

<iframe src="https://trinket.io/embed/python3/5a44c75682" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


At this point I was really happy with my progress. There were still a few issues that I needed to take care of. First, I hadn’t touched the graphical interface part. I was a little concerned about how to approach this so I kept putting it off. It felt the most overwhelming of the lot. And there was still the issue of the new York zip codes being flagged on ‘incorrect’ in the Zip Code Identifier. These were the last two things I really needed to work on.

But before that I finally thought it was time to do in and clean up my code. One of the problems I ran into at the start of the project was in the long While True statement that I used for the selections on the menu. Originally, I had each input as its own if statement, basically calling all of them one at a time (I believe is the correct term). It worked, but I didn’t want that. When I tried swapping them over to elif, they actually didn’t work originally saying the syntax was incorrect. However, trying again today, it actually did work. I admit, I’m not sure what changed. My guess is that my original error was related to a typo of sorts. This is another issue I’ve had, not just with programming but with the GitHub posts as well. I type really fast but usually don’t proof read all too much with what I post. I know it’s a bad habit and one I need to break. Thankfully, since my freak out, I started to slow down a bit in my coding, so I think that really helped.

I removed the repeated printing of the main menu which was also causing some weird looping, instead putting it at the end of the while loop. I also finally solved the issue of the menu failing to prompt the user to enter a number between 1 and 8 if they entered two invalid inputs in a row (it would instead go back to the main menu). Easy fix, just add it as an else statement at the bottom of the while loop before the printing of the main menu.
The biggest thing I did next though was move my functions over to a helper folder. I had wanted to do this from the get go, but I was nervous. My first problems with linking in the CSV itself was getting me worried that if I moved stuff over, perhaps I’d run into another issue. Thankfully though, that didn’t happen. While moving this over, I also condensed three of my functions. Originally, I had generalzip(zc), male(zc) and female(zc) all as individual functions, each which called up the same thing, just slightly different. While this worked, it was making the code larger than necessary and I really wanted to slim it down.

It took a bit of playing around but I combined the three into a new function, showzipdata. This was the original generalzip function, however I tweaked the female and males section, setting them to print when flagged as true. After this, I went to where I was calling the Male and Female data, and linked in the new helper.showzipdata, flagging the Male False for the Female and vice-versa. Now, all three of the main functions are rolled into one! And, added bonus, the helper file actually worked which was a great thing to se. 

<iframe src="https://trinket.io/embed/python3/2ce3642d93" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

My last two challenges were addressing the graphic print out and the fixing the zip code issue. After re-reading the notes from the class, I saw that we were allowed to import the matplotlib module. I wasn’t sure what it did, but thankfully w3schools had a tutorial. It looked really easy to use. I gave it a spin, and, well, it worked but I had originally used  a bar graph to display my data. Unfortunately, since I only had two data sets, it was making the Y Axes the two data amounts, which sometimes meant the lower option came out higher on the graph? It was strange. I deleted it though and tried a pie-graph style print out, which worked much better. I also labeled the sections so the data print out will also show the numerical amount in the image.

At this point, technically all of my functions were working. You could grab zip code data, grab it by gender, get a random zip code and put in a zip code and find out what borough it was from. I had also cleaned up the menu’s appearance. The only issue was still putting a zipcode that was from NYC but not on the CSV would yield the error message.

I’m not gonna lie, I thought this would be a lot easier than it was. I created a function betterborough to replace the original borough. The idea was since the zip codes are generally in a numeric range, I could create an if statement focused around it clearing if the input fell within the range of the zip codes. For example:

def betterborough(zc):
  print()
  if int(zc) >=10001 and int(zc) <=10282:
    print("This Zip Code is from Manhattan")

And this worked, sort of. Atleast for some. But a few were getting odd print outs. Some were still getting the ‘not a valid zip code’ and others were printing that they belonged to multiple zipcodes. So I scrapped it and tried to set individual functions again. I started with just Manhattan but, again, I was running into issues with it incorrectly double print messages like “This is no a valid Zip Code” at the same time saying it’s a “Zip Code in Manhattan.” I ran a quick test with test=int(zc) to print it out, which came back true. So I think this means it was being checked before getting checked for the range? Basically, the zip code was running through the zipcheck function first, which sometimes said there was no information on it before running back and saying if the zip code was within the range I had originally assigned.

<iframe src="https://trinket.io/embed/python3/3746b4f0f4" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

So to address this, I created a new function, ziprange(zc). Using the range function, I put in the ranges for the zip codes. I had to break Queens up into Que1 and Que2 since it has two different ranges. Then I assigned it a quick if statement to print back if the inputted zip code was from one of the five boroughs.
All I had to do left was slip the new ziprange into the Borough identifier and it was good to go! I also added some extra messages to help show whether or not there is data on the zip code as well as the borough.

----

##Final Thoughts

This class has been challenging. I struggle, a lot, with the basic logic of programing. Something about the indentations, the functions, : and the ;, it gets me very confused and frustrated. This final project also saw me nearly break down when I thought I had messed up. I need to work on channeling this frustration and anxiety into better outlets to not run into situations like that. I actually feel after I had my freak out and returned to the program with the knowledge that I need to chill, things got a lot easier. I tried to not worry about stupid mistakes like the wrong indenting and look at the bigger picture. I know my data analysis isn’t the most complex but I’m really proud of it. I honestly never thought I’d finish this project, let alone enjoy it by the end of it.  I also don’t think I could have made it through this class without the fantastic resources that are available out there for us all, w3schools and freecodecamp on youtube were great resources  that I could turn too when I was struggling with the text book. The text book was great, but sometimes working through problems in real time just works the best, which was one of my favorite things we did together as a class. I really felt I got the most out of those lessons when we actually sat down and worked through the problem together as opposed to just kind of showing what different things did. 

I’m grateful I had this opportunity. I don’t think I’m going to go off to become a programmer, but at the very least I have gained and incredible appreciation for all of you who do.

