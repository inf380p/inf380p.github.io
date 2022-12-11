---
layout: post
author: emmtm
title: "Emmalee's Final Project!"
---

trinket embed link: 
 <iframe src="https://trinket.io/python/8ed826c445" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
 
 For my final project, I wanted to make a tarot card reader. This reader would ask users questions about their lives, then show them a past, present, and future reading for three different categories (romantic, career, and personal). 

My first step was to create a list of questions that users would answer so they would feel like they were getting a more personalized reading. I used a chain of while loops to ask questions about users romantic life, career, personal outlook, as well as their name and zodiac sign. To store these for future use I created an empty list- answer_list, and then appended the answers of each question so I could pull them out and have the program remember the users inputs.

```
answer_list = []

while True:
  ask_name = input("What is your name?")
  name = [str(ask_name)]
  if ask_name in name:
    print("\nNice to meet you " + str(ask_name) + "!")
    answer_list.append(ask_name)
    break
  else:
    continue
  
time.sleep(2)
os.system("clear")

  
while True:
  signs = ["Aquarius", "Pices", "Cancer", "Taurus", "Sagittarius", "Virgo", "Leo", "Libra", "Aries", "Gemini", "Capricorn", "Scorpio"]
  question1 = input("What is your astrological sign?")
  if question1 in signs:
    print("\nOkay, so your sign is " + str(question1) + "." )
    answer_list.append(question1)
    break
  else:
    print("\nThat is not one of the 12 astrological signs. Please try again! Remember to capitalize.")

```

I also added a system clear after each question so that the text box at the bottom wouldn’t get bogged down with text, resulting in a cleaner user interface.

To create the actual reading, I created two nested dictionaries. One with the name of each card, the facing (up or down) and a few words associated with the up or down interpretation of each card. The second dictionary also had the name of each card, with the name of each card image that I uploaded into trinket. I then created three randomize variables as well as an image variable:

```
card = random.choice(list(cards.card_names))
facing = random.choice(list(cards.card_names[card]))
reading = (cards.card_names[card][facing])
Image = images.card_images[card]

```
And then added the randomized card images using:

```
screen.addshape(images.card_images[card])
self.shape(images.card_images[card])

```

The first three variables randomized the card and facing, and then pulled the reading from the last nested dictionary. The image variable then searched the second dictionary for a matching card name key from the one randomized with the card variable, and then added the card to the screen using a turtle. This resulted in the card appearing on the screen, corresponding with each part of the past, present, and future reading.

Once it was working, Elliot challenged me to add more of a graphical interface to it. So I set out to use turtle classes to make the cards all appear on the screen (flippy), and then flip over when clicked(reflippy). This proved harder than expected, and on my first draft of this feature all three cards were revealing the same card instead of three different ones. 

```
card = random.choice(list(cards.card_names))
facing = random.choice(list(cards.card_names[card]))
reading = (cards.card_names[card][facing])


def __init__(self, x, y):
    turtle.Turtle.__init__(self)
    screen.addshape("tarot-back.jpg")
    self.penup()
    self.hideturtle()
    self.goto(x,y)
    self.shape("tarot-back.jpg")
    self.rt(-90)
    self.showturtle(
    if self.facing == "Up":
      self.hideturtle()
      self.rt(0)
      self.showturtle()
    elif self.facing == "Down":
      self.hideturtle()
      self.rt(180)
      self.showturtle()
self.onclick(self.flippy)

  def flippy(self,x,y):
    screen.addshape(images.card_images[card])
    self.shape(images.card_images[card])
    self.onclick(self.reflippy)


```

I reached out and asked for help, and realized I needed to make the random.choice part that selected the cards an attribute in my turtle classes instead of defining the random.choice as a variable. Once I changed this, the program was showing three different cards, as well as remembering the cards even once they were flipped back over. This looked something like this:

```
def __init__(self, x, y):
    turtle.Turtle.__init__(self)
    screen.addshape("tarot-back.jpg")
    self.penup()
    self.hideturtle()
    self.goto(x,y)
    self.shape("tarot-back.jpg")
    self.rt(-90)
    self.showturtle()
    self.card = random.choice(list(cards.card_names))
    self.facing = random.choice(list(cards.card_names[self.card]))
    self.reading = (cards.card_names[self.card][self.facing])
    self.facing
    self.reading
    if self.facing == "Up":
      self.hideturtle()
      self.rt(0)
      self.showturtle()
    elif self.facing == "Down":
      self.hideturtle()
      self.rt(180)
      self.showturtle()
self.onclick(self.flippy)

def flippy(self,x,y):
    screen.addshape(images.card_images[self.card])
    self.shape(images.card_images[self.card])
    self.onclick(self.reflippy)

```


Now that this was working, I needed the correct reading outputs to show on the screen. I wanted these readings to correspond with each instance of a cardturtle. Originally, I had each card appear separately, so I was able to control the readings a little better so that the past card would correspond directly with the past reading:

```
def career_reading():
  card = random.choice(list(cards.card_names))
  facing = random.choice(list(cards.card_names[card]))
  reading = (cards.card_names[card][facing])
  image = images.card_images[card]
  screen.addshape(image)
  if facing == "Up":
    turtle.penup()
    turtle.hideturtle()
    turtle.goto(80,20)
    turtle.rt(-90)
    turtle.shape(image)
    turtle.showturtle()
  elif facing == "Down":
    turtle.penup()
    turtle.hideturtle()
    turtle.goto(80,20)
    turtle.rt(90)
    turtle.shape(image)
    turtle.showturtle()
  
  print(__main__.answer_list[0] + ", your past was represented by " + card + ", which is facing " + facing + "." " This tells me that your past career experiences brought " + reading + " into your life.")
  while True:
    continueop = [""]
    continues = input("\nPress enter to see your present reading!")
    if continues in continueop:
      break
    else:
      print("\nPlease press enter to continue your reading!")
      continue
```

By structuring my code like this, a new random card was generated each time the user pressed enter to continue, which guaranteed the past card would be viewed with the past reading output. But it also resulted in a lack of interactivity for the user as well as code being repeated over and over again, which made my program lag significantly. Using custom turtle classes to generate the cards helped with both graphic interactivity and the lagging, but the challenge now was for me to make the readings correspond with whichever card was being flipped. This was one of the biggest hurdles I faced when making this program, and I was able to get the first draft of this project working by reaching out for help on stackoverflow. 



Since there are three cardturtles on the screen, one representing past, present and future, I figured my best bet was to create a list to append each instance of self.card into. I was hoping that this would store each of the three cards in the list as items 0, 1 and 2. 

```
def flippy(self,x,y):
cardlist = []
self.card
screen.addshape(images.card_images[self.card])
self.shape(images.card_images[self.card])
self.onclick(self.reflippy)
cardlist.append(self.card)

if __main__.answer_list[5] == "romantic":
  if self.card == cardlist[0]:
    print __main__.answer_list[0] + ", your past was represented by " + self.card + ", which is facing " + self.facing + "." " This tells me that your past " + __main__.answer_list[5] + " experience brought " + self.reading + " into your life."
  elif self.card == cardlist[0]:
    print "Since you are" + __main__.answer_list[2] + ", your present is represented by " + self.card + ", which is facing " + self.facing + "." + " This tells me that you are currently experiencing " + self.reading + " in your " + __main__.answer_list[5] + " life."
  elif self.card == cardlist[0]:
    print "Your future will be represented by " + self.card + ", which is facing " + self.facing + ". " "As a " + __main__.answer_list[1] + " This tells me that you can expect plenty of " + self.reading + " in your future" + __main__.answer_list[5] + " endevors."
elif __main__.answer_list[5] == "career":
  if self.card == cardlist[0]:
    print __main__.answer_list[0] + ", your past was represented by " + self.card + ", which is facing " + self.facing + "." " This tells me that your past " + __main__.answer_list[5] + " experience brought " + self.reading + " into your life."
  elif self.card == cardlist[0]:
    print "Since you are" + __main__.answer_list[2] + ", your present is represented by " + self.card + ", which is facing " + self.facing + "." + " This tells me that you are currently experiencing " + self.reading + " in your " + __main__.answer_list[5] + " life."
  elif self.card == cardlist[0]:
        print "Your future will be represented by " + self.card + ", which is facing " + self.facing + ". " "As a " + __main__.answer_list[1] + " This tells me that you can expect plenty of " + self.reading + " in your future" + __main__.answer_list[5] + " endevors."
    elif __main__.answer_list[5] == "personal":
      if self.card == cardlist[0]:
        print __main__.answer_list[0] + ", your past was represented by " + self.card + ", which is facing " + self.facing + "." " This tells me that your past " + __main__.answer_list[5] + " experience brought " + self.reading + " into your life."
      elif self.card == cardlist[0]:
        print "Since you are" + __main__.answer_list[2] + ", your present is represented by " + self.card + ", which is facing " + self.facing + "." + " This tells me that you are currently experiencing " + self.reading + " in your " + __main__.answer_list[5] + " life."
      elif self.card == cardlist[0]:
        print "Your future will be represented by " + self.card + ", which is facing " + self.facing + ". " "As a " + __main__.answer_list[1] + " This tells me that you can expect plenty of " + self.reading + " in your future" + __main__.answer_list[5] + " endevors."
```
Unfortunately, this method did not work. Because each card is generated on the click, no matter which cardturtle I clicked on, the cardlist was interpreting it as the first card in the list. This made each card show the past reading output, instead of the corresponding past, present, or future output. This is something I was unable to resolve in the time allotted, so I opted for a more generic reading on each click:

```
def flippy(self,x,y):
    screen.addshape(images.card_images[self.card])
    self.shape(images.card_images[self.card])
    self.onclick(self.reflippy)
    if __main__.answer_list[5] == "romantic":
      print __main__.answer_list[0] + ", this stage of your life is represented by " + self.card + ", which is facing " + self.facing + "." " This tells me that this stage of your " + __main__.answer_list[5] + " experience is characterized by " + self.reading + "."
    if __main__.answer_list[5] == "career":
      print __main__.answer_list[0] + ", this stage of your life is represented by " + self.card + ", which is facing " + self.facing + "." " This tells me that this stage of your " + __main__.answer_list[5] + " experience is characterized by " + self.reading + "."
    if __main__.answer_list[5] == "self":
      print __main__.answer_list[0] + ", this stage of your life is represented by " + self.card + ", which is facing " + self.facing + "." " This tells me that this stage of your " + __main__.answer_list[5] + " experience is characterized by " + self.reading + "."

```
This allowed for the same amount of personalization, and let the users know which type of reading they chose consistently throughout. To make sure users didn’t get lost about which card they were getting a reading for, I labeled the cards using a turtle to say past, present, and future below them. This wasn’t ideal to me, and I still want to try and figure out how to get the correct card to correspond with the original readings I wrote. For the purpose of turning this project in though, I am pretty satisfied with the workaround I figured out as it does not significantly hinder the tarot reading experience.

The final step for me was to add iterative gameplay into the program. I had this working beforehand by simply pulling the input prompt for type of reading into a function, which I called at the beginning of the program: 
```
def get_reading():
  while True:
    tarot_options = ["1", "2", "3"]
    question5 = input("What type of Tarot Reading would you like? \n1. Romantic \n2. Career \n3. Self")
    if question5 in tarot_options:
      if question5 == "1":
        print("\nOkay, I will give you a Tarot reading about your romantic past, present, and future.")
        answer_list.append("romantic")
        time.sleep(2)
        os.system("clear")
        readings.romantic_reading()
        break
      if question5 == "2":
        print("\nOkay, I will give you a Tarot reading about your career past, present, and future.")
        answer_list.append("career")
        time.sleep(2)
        os.system("clear")
        readings.career_reading()
        break
      if question5 == "3":
        print("\nOkay, I will give you a Tarot reading about your personal past, present, and future.")
        answer_list.append("personal")
        time.sleep(2)
        os.system("clear")
        readings.self_reading()
        break
    else: 
      print("\nThat is not an option, try again!")
    
get_reading()
  
```
After the user finished their first reading, I simply asked them if they wanted another one. If they responded with yes, I would call this function again, allowing them to get a new reading without having to answer all of the questions again. 

This got a little more complicated with the new custom turtle classes however, and I ran into a bug that restarted the program fine, but upon beginning the second reading, the outputs for all three cards were shown despite the user only clicking on one at a time. This code is here:

```
  def exityay(x,y):
    while True:
      exityes = ["yes","Yes","y","Y"]
      exitno = ["no","No","n","N"]
      exitinput = input("Would you like another reading? Y/N")
      if exitinput in exityes:
        __main__.get_reading()
        break
      if exitinput in exitno:
        quit()
      
    
  
  texit = turtle.Turtle()
  texit.penup()
  texit.hideturtle()
  texit.color("black")
  texit.goto(-180,250)
  texit.write("Exit",None,"center","12pt bold")
  texit.goto(-200,255)
  texit.showturtle()
  texit.onclick(exityay)
```

I am not sure why it was doing this, and commented it out in my program. I wanted to keep it in there so you could still use it if you wanted, but it does bug out a little bit. I am assuming it has something to do with the way the attribute self.card is being stored, but I am unsure of how to clear it so that it works in the same way it does the first time around.

Overall, I am very pleased with the progress I made on this project. I am a little sad I was not able to figure everything out that I wanted to, as I am a bit of a perfectionist. But I do think this project shows my progress as a programmer, and for the most part it works exactly how I was hoping it would. This is a project I am inclined to continue working on until I get it perfect, but things such as classes I had less experience working with and would need more time learning how to structure the flow with them for everything to work perfectly. I think this project really pushed the limits of my knowledge and capabilities and I feel like a much stronger programmer after completing it. 

Despite it not being perfect I am feeling more motivated than ever to keep learning and improving my programming skills. Getting the classes to work how I wanted them to was an exciting moment for me, and it helped me understand refactoring better than any other exercise we have completed. This project helped me learn a lot about flow of control and I found myself able to locate and fix errors much more effectively than I have been able to in the past. This project also made me realize I have an immense weakness with for loops. While I feel confident in my ability to use while loops (obviously, as there are plenty of instances of them in this code) the iteration of for loops confused me as I was continuously unsure about what the range would be for them. This is something I wish I had practiced with more consistently within the class as I know they probably would have been helpful with some of the bugs and issues I had when creating this project. 

Overall, I found the original goals for my project very easy to complete and well within my range. Once I was challenged to add more graphic interface elements to it, I was overconfident and found myself low on time to complete the additional goals I added to the completion of my project. The way I initially structured my code ended up getting in the way once I started adding turtle classes. In the future I would like to create a more detailed initial plan that includes any possible stretch goals I may want to add so that I can think more about how I structure my code could positively or negatively affect my process when adding new things. 
