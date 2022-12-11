---
layout: post
author: Prakash-sa
title: "Prakash's Final Project"
---

# Web Scrapping of TradingView Website

## About 
Selecting the final project was very hard for me because the scope of python is very broad. I selected this project because I am interested in stocks and want to invest in some.
Then an idea came to my mind of coding the web scrapper of the website and displaying the stocks according to the country, and features and also providing the functionality of saving the stock data in a CSV file.
The software is to display the stocks by the web scrapping of https://www.tradingview.com/ website using python. 
I mostly used the python core features in this software and used urlopen, BeautifulSoup, and CSV third-party libraries. 
The software has many features like:-

- Extracting the data from an old script.
- Getting the updated data from the website.
- User-friendly interface and display.
- Functionality of saving the data in CSV file.



### Extract the data from url and HTML content

- The major obstacle of this project was to get the data from the website. I researched a lot and found the python third-party library urlopen which helps to get the HTML format data from the website.
urlopen helps to get the data from the website but in string format so to parse the HTML string format to the list and dictionary format, I have used the python third-party library BeautifulSoup.

I have declared the functions to get and extract the data from the website in a separate file with the crawler.py name.
Below is the function to get the data from the URL and parse the HTML format using BeautifulSoup and then return it.

```
# function to get the data from the url
def getPage(url):
  # get the HTML data from the url
  html = urlopen(url)
  
  # parse the HTML string data using BeautifulSoup
  bs = BeautifulSoup(html.read(), 'html.parser')
  
  # return the result
  return bs
```

- Extracting the country name from the HTML content was hard and after digging into the HTML format I found that all country names have the same `tv-dropdown__item-text` class.
So I extract all the tags which have the class name `tv-dropdown__item-text` using the BeautifulSoup function findAll. The resulting output will be the list of tags with the `tv-dropdown__item-text` class as below:-

```
[<span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Argentina</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Australia</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Bahrain</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Belgium</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Brazil</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Canada</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Chile</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">China</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Colombia</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Denmark</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Egypt</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Estonia</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Finland</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">France</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Germany</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Greece</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Hong Kong</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Hungary</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Iceland</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">India</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Indonesia</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Israel</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Italy</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Japan</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Kenya</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Latvia</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Lithuania</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Luxembourg</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Malaysia</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Mexico</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Netherlands</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">New Zealand</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Nigeria</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Norway</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Peru</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Philippines</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Poland</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Portugal</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Qatar</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Romania</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Russia</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Saudi Arabia</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Serbia</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Singapore</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Slovakia</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">South Africa</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">South Korea</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Spain</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Sweden</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Switzerland</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Taiwan</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Thailand</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Tunisia</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Turkey</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">United Arab Emirates</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">United Kingdom</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Venezuela</span>, <span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Vietnam</span>]
```

Then after iterating through the whole list and using the BeautifulSoup function `get_text()` to get the text between the span tag, I was able to get all country names and store that in the countries list.
After getting the country name the function returns the list.

```
# extract the country name from the content
def getCountries(content):
  """
  Utilty function used to get countries name from the content.
  Returns a list of countries.
  """
  
  # declare the list to store the country name
  countries=[]
  
  # get all the tag whose class name is tv-dropdown__item-text 
  countryList=content.findAll(class_='tv-dropdown__item-text')
  
  # iterate through the list
  for country in countryList:
    
    # append the country name in the list
    countries.append(country.get_text())
  
  return countries
```


- Each country name has a different link to access their stocks from the website, so we have to first get the link to extract the stocks from a particular country.
After extracting the `tv-dropdown__item` class from the content, it gives the following list:-

```
[<a class="tv-dropdown__item" href="/markets/stocks-argentina/market-movers-all-stocks/">
<img alt="" class="tv-circle-logo tv-circle-logo--xxsmall tv-category-dropdown-header__dropdown-item-flag" src="https://s3-symbol-logo.tradingview.com/country/AR.svg"/>
<span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Argentina</span>
</a>, 
...
...
, <a class="tv-dropdown__item" href="/markets/stocks-vietnam/market-movers-all-stocks/">
<img alt="" class="tv-circle-logo tv-circle-logo--xxsmall tv-category-dropdown-header__dropdown-item-flag" src="https://s3-symbol-logo.tradingview.com/country/VN.svg"/>
<span class="tv-dropdown__item-text tv-category-dropdown-header__dropdown-item-text">Vietnam</span>
</a>]
```

I then extracted the name from the list using the `get_text()` function and used `strip()` to remove the white spaces before and after the word.
I extracted the link by selecting the attribute of `href` which contains the link of format `/markets/stocks-vietnam/market-movers-all-stocks/`. I only needed the country name link because the rest of the part is repeated for all the countries, so we don't need to extract it.
I extracted the countryLink name from that link using the `split('\')` which helps to splits and make the list of the above link based on `/` and get the second index and then split it again based on `-`. After getting the name and extracted link, I compared the resulting name which the desired country name using an if statement, and if the conditions satisfy it will return the countryLink.


```
# get the link of the stock for the particular country
def getCountryLink(content,countryName):
  """
  Utilty function used to get a url of particular country from the content. 
  Returns an link of that country if exist otherwise send "No country link found!".
  """
  
  # get all the tag whose class name is tv-dropdown__item
  countryList=content.findAll(class_='tv-dropdown__item')
  
  # iterate through the list
  for country in countryList:
    
    # top remove the whitespace from beginning and the end
    name=country.get_text().strip()
    extracted_link=country.attrs['href'].split('/')[2].split('-')[1]
    
    # compare the country name with the desired country name
    if str(name)==str(countryName):
      return extracted_link
  
  return "No country link found!"
```

- Getting the stocks from the content is the major rollercoaster of the whole project because I have to extract the stocks which are dependable on the country and stock type. 
So, before extracting the stock, I have to get the country name whose stock the user wants and the stock link of that country.
Heading of the column is stored in the `th` tag and I extracted that using the `get_text()` function and used the `strip()` function to remove the white space in the name to store in the headlines list with the `|` char to make the visualization and storing of the data more attractive.

After researching and debugging, I found that the stock data are in tr tag. So I used beautifulsoup function findAll to get the data in the below list format:-

```
[<tr class="row-EdyDtqqh listRow" data-rowkey="NASDAQ:ACDC"><td class="cell-TKkxf89L left-TKkxf89L cell-fixed-f5et_Mwd onscroll-shadow"><span class="tickerCell-hMpTPJiS"><img alt="" class="tv-circle-logo tv-circle-logo--xsmall tickerLogo-hMpTPJiS" src="https://s3-symbol-logo.tradingview.com/profrac.svg"><a class="apply-common-tooltip tickerNameBox-hMpTPJiS tickerName-hMpTPJiS" href="/symbols/NASDAQ-ACDC/" target="_blank" title="ACDC − ProFrac Holding Corp.">ACDC</a><sup class="apply-common-tooltip tickerDescription-hMpTPJiS" title="ProFrac Holding Corp.">ProFrac Holding Corp.</sup><div class="marksContainer-v2Oqy8ms"><span class="dataMode-Vap_2unz"></span></div></img></span></td><td class="cell-TKkxf89L right-TKkxf89L">21.71<span class="currency-uW0GcYqJ">USD</span></td><td class="cell-TKkxf89L right-TKkxf89L"><span class="negative-C2C2Vilj">−3.25%</span></td><td class="cell-TKkxf89L right-TKkxf89L"><span class="negative-avn2kVRm">−0.73<span class="currency-uW0GcYqJ">USD</span></span></td><td class="cell-TKkxf89L left-TKkxf89L"><div class="container-epNUk8Mp sell-epNUk8Mp"><span class="ratingIcon-epNUk8Mp"><svg height="18" viewbox="0 0 18 18" width="18" xmlns="http://www.w3.org/2000/svg"><path d="m4.67 7.38.66-.76L9 9.84l3.67-3.22.66.76L9 11.16 4.67 7.38Z" fill="currentColor"></path></svg></span>Sell</div></td><td class="cell-TKkxf89L right-TKkxf89L">268.12K</td><td class="cell-TKkxf89L right-TKkxf89L">5.821M</td><td class="cell-TKkxf89L right-TKkxf89L">3.367B<span class="currency-uW0GcYqJ">USD</span></td><td class="cell-TKkxf89L right-TKkxf89L">—</td><td class="cell-TKkxf89L right-TKkxf89L">−0.19<span class="currency-uW0GcYqJ">USD</span></td><td class="cell-TKkxf89L right-TKkxf89L">—</td><td class="cell-TKkxf89L left-TKkxf89L"><a class="link-j5JxgHa0" href="/markets/stocks-usa/sectorandindustry-sector/industrial-services/" target="_blank">Industrial Services</a></td></tr>
...
,<tr class="row-EdyDtqqh listRow" data-rowkey="NYSE:ACEL"><td class="cell-TKkxf89L left-TKkxf89L cell-fixed-f5et_Mwd onscroll-shadow"><span class="tickerCell-hMpTPJiS"><span class="tv-circle-logo tv-circle-logo--xsmall tickerLogo-hMpTPJiS">A</span><a class="apply-common-tooltip tickerNameBox-hMpTPJiS tickerName-hMpTPJiS" href="/symbols/NYSE-ACEL/" target="_blank" title="ACEL − Accel Entertainment, Inc.">ACEL</a><sup class="apply-common-tooltip tickerDescription-hMpTPJiS" title="Accel Entertainment, Inc.">Accel Entertainment, Inc.</sup><div class="marksContainer-v2Oqy8ms"><span class="dataMode-Vap_2unz"></span></div></span></td><td class="cell-TKkxf89L right-TKkxf89L">8.44<span class="currency-uW0GcYqJ">USD</span></td><td class="cell-TKkxf89L right-TKkxf89L"><span class="positive-C2C2Vilj">1.81%</span></td><td class="cell-TKkxf89L right-TKkxf89L"><span class="positive-avn2kVRm">0.15<span class="currency-uW0GcYqJ">USD</span></span></td><td class="cell-TKkxf89L left-TKkxf89L"><div class="container-epNUk8Mp sell-epNUk8Mp"><span class="ratingIcon-epNUk8Mp"><svg height="18" viewbox="0 0 18 18" width="18" xmlns="http://www.w3.org/2000/svg"><path d="m4.67 7.38.66-.76L9 9.84l3.67-3.22.66.76L9 11.16 4.67 7.38Z" fill="currentColor"></path></svg></span>Sell</div></td><td class="cell-TKkxf89L right-TKkxf89L">213.275K</td><td class="cell-TKkxf89L right-TKkxf89L">1.8M</td><td class="cell-TKkxf89L right-TKkxf89L">738.222M<span class="currency-uW0GcYqJ">USD</span></td><td class="cell-TKkxf89L right-TKkxf89L">11.34</td><td class="cell-TKkxf89L right-TKkxf89L">0.74<span class="currency-uW0GcYqJ">USD</span></td><td class="cell-TKkxf89L right-TKkxf89L">900</td><td class="cell-TKkxf89L left-TKkxf89L"><a class="link-j5JxgHa0" href="/markets/stocks-usa/sectorandindustry-sector/consumer-services/" target="_blank">Consumer Services</a></td></tr>
]
```

As you can see, the data which I got from the function is very complex. The beautifulsoup function `get_text()` helps me to get only the text in this bunch of HTML tags, and I have already stored the column name previously. 
I have declared one counter to store the column number and display the stock data according to that column number. 
Since each element of the list contains the stock details for a particular company, so I declared the `tmp_list` to store the details of stocks for that company and after that append that into the data.
In the end, I have returned the stored headline and data in list format so that if the user wants to store the data in CSV, we can use this data and don't have to call this function again.


```
# function to get the stock data from content
def getStocks(content):
  """
  Utility function used to get stocks from a Beautiful Soup
  object and a selector. Returns the list which contains the 
  headline and data of stock.
  """
  
  # to store all the stocks data
  data=[]
  
  # to store the column headline of the stock
  headlines=[]
  
  # get all the tag with th
  headlineList = content.findAll('th')
  
  # adding all the column headline in the headlines list
  for headline in headlineList:
    headlines.append("| " + headline.get_text().strip())
  
  # content of the stock are in tr tag so make the list of stock
  stockList = content.findAll('tr')
  
  for i in range(1,len(stockList)):
    # declared counter to keep the number of the column 
    count=0
    
    # list to store the stock for particular country
    company_list=[]
    
    # iteration through the stockList
    for stock in stockList[i]:
      
      # adding the stock data in the company_list
      company_list.append("| "+stock.get_text().strip())
      
      # printing the data
      print(headlines[count]+": "+stock.get_text().strip())
      
      # increasing the counter for next column
      count+=1
    
    # add space to make the visalization alluring
    company_list.append("\n\n")
    
    # add the stock data of the company in data list
    data.append(company_list)
    print("\n")
  
  # return the column headline and data of stock from the function
  return [headlines,data]
```


### Interface for the data

- I have given the menu for the user to select the content they want to see in the software. I have added the old script functionality in which the software will extract the data from the script which is already stored in the system, so we don't have to use the urlopen to get the data from the live website.
But extracting the data from the old script provide a very narrow scope for visualizing the data because we have to store the HTML format data for each country and it will be more memory-consuming. 
The second option is the latest script in which data will be extracted from the live website and it has the feature of selecting the country and multiple stocks. So, I recommend using the latest script option which has more features for stock visualization.
The third option will give the description of the software and the final option will help the user to exit from the system.

```
# List of options for the interface menu 
menu_dict = {
  "1" : "Old Script(6th Dec 2022)",
  "2" : "Latest Script",
  "3" : "Help",
  "0" : "Exit"
}

```
I have called the `interface.get_menu_choice(menu_dict)` function in the main file by passing the argument `menu_dict` in the function.
The below function will get the valid user input and return the index which is selected by the user. If the user selects the choice which is not valid then it will prompt the above menu again until the user selects the valid choice.

```
#takes the given dictionary and lets user select an option
def get_menu_choice(choices_dict, prompt_str = "Select the option:- "):

  # Make sure keys to the choices are strings
  assert all([isinstance(x, str) for x in choices_dict]), "Keys to choices_dict must be strings"

  # Keys of the dict are the possible choices
  valid_choices_list = list(choices_dict.keys())
  
  # Print main menu and all choice labels and decriptions
  print("Main Menu")
  for label, description in choices_dict.items():
    # print(f"{label}: {description}")
    print(label + " : " + description)
  
  # Get a user choice
  user_choice = input(prompt_str)
  
  # Check if it's a valid choice. If it is, loop is skipped.
  while user_choice not in valid_choices_list:
    # User's choice was invalid; loop until it is
    print(user_choice + " is not a valid selection.")
    
    # Get a user choice
    user_choice = input(prompt_str)

  return user_choice
```

- I have added the interface to select whether the user wants to save the data in a CSV file or not. To save the file user can select the 'y' | 'n' | 'Y' | 'N' options.
```
# function if user wants to save the data in CSV file or not
def selectCSV(prompt_str="Do you want to save the CSV file?\nPress 'Y' or 'N' or 'y' or 'n'"):
  
  # list of valid choices
  valid_choices_list=['Y','N','y','n']
  
  # Get a user choice
  user_choice = input(prompt_str)
  
  # Check if it's a valid choice. If it is, loop is skipped.
  while user_choice not in valid_choices_list:
    # User's choice was invalid; loop until it is
    print(user_choice + " is not a valid selection.")
    
    # Get a user choice
    user_choice = input(prompt_str)

  return user_choice
```

### Functionality of the software


- Leveraging previous work means working smarter—not harder. Right now, copying and pasting from script to script might seem like a simple, risk-free fix. 
But creating the function in a single file and importing it makes the process simpler and gets rid of potential mistakes. I have created the crawler file which contains the functions of web scrapping and the interface file which have the function to simplify the user input.

```
from urllib.request import urlopen
from bs4 import BeautifulSoup
import crawler
import interface
import csv
```

- This software has the functionality of continuously running according to the user input until the user wants to exit the system by pressing 0 as user input.

```
while True:
  choice_str = interface.get_menu_choice(menu_dict)
  
```

- I saved the HTML data of the website on 6th Dec 2022 in a data.txt file and used that to display the output. The data in the file is an HTML string that is parsed by BeautifulSoup and after that `getStocks(content)` function is called to print the stocks in the file.

```

# get the HTML data from data.txt file
f = open('data.txt', 'r')

# parse HTML string using BeautifulSoup
result = BeautifulSoup(f.read(), 'html.parser')

# close the file after getting the data
f.close()

# get the stocks
content=crawler.getStocks(result)
```

- Getting the output from the latest script is a cumbersome task. First of all, we have to extract the country name and country stock link from the HTML content.
After that, we have to get the HTML content from that country URL and extract the stocks from that. I have added the option of selecting the country and selecting the stock feature user wants to see.


```
# get html parsed content from the url
result=crawler.getPage(url=default_url)

# get all the countries name from the html content
countriesname=crawler.getCountries(result)

# user will select for which country they want to see the stocks
country=interface.selectCountry(countriesname)
print("Selected country:",country,"\n\n")

# get the country url from the content and country name
countryLinkName=crawler.getCountryLink(result,country)

# get the stock features
features=crawler.getFeatures(result)

# select the available feature
selectedFeature=interface.selectFeature(features)

# get the complete url of the stock
url=crawler.getUrl(countryLinkName,selectedFeature)
print(url)

# get the html content of the page
result=crawler.getPage(url)

# get the stocks
content=crawler.getStocks(result)
    
```


### Saving the output in a CSV file

I used the knowledge of CSV file reflection and assignments which we already performed in the classes to complete this task. 
First, it will open the `output` file in write mode and then use the CSV writer function to write the column heading and column data in the output file.

```
with open('output', 'w') as f:
  write = csv.writer(f)

  # add the column heading 
  write.writerow(content[0])

  # add the data to CSV file
  write.writerows(content[1])
    
```

#### Final Requirements

- [X]  **At least one external data file** - external data.txt file
- [X]  **Dictionaries** - used in main.py for menu option.
- [X]  **Custom modules** - main.py, crawler.py and interface.py
- [X]  **Definite `(for)` loops** - I have used many `for` loops in crawler.py and interface.py files
- [X]  **Custom functions** - used in crawler.py and interface.py files
- [X]  **Have help text available somehow** - user can press `0`  for help
- [X]  **Have an iterative interface** - users have the flexibility to select the options in every step from the start of the program to save the data in a CSV file.
- [X]  **Visualize data** - I have displayed the stocks of the company in an engaging way.

Here's the link to my final trinket:
<iframe src="https://trinket.io/embed/python3/f89f994e23" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
