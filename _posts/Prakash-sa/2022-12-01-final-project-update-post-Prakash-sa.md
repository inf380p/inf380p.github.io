---
layout: post
author: Prakash-sa
title: "Prakash's Project Update"
---

### Are there any roadblocks ahead? Is there anything your group can do to help out?
I am working on web scrapping of https://www.tradingview.com/, my major roadblock is extracting the stocks and companies from the HTML format. 

### Are your milestones ambitious enough? Make sure to include some stretch goals.
I believe my milestone is ambitious. I have used the BeautifulSoup to extract the required data from the HTML format and then use core python skills to extract the data further. The stretch goal is to code from scratch to extract data and display it according to the user input.

### Are your milestones too ambitious? Make sure to break down the unglamorous parts of coding into chunks that reflect the actual work to be done.
My goals are a little ambitious. I extracted the stocks of the companies according to the country. The link of the stocks of the country changes by their name, so I have to build the function to get the URL for that.

- First, I coded the function that is used most in web scrapping and made a new file for that.
- Second, I figured out the format of the stocks appearing in the HTML format by using the python skills like print, type, etc.
- Once that is done, I intend to save the stocks of the country in the CSV file.

- [x] Get the data from the url.
- [x] Extract the data from the HTML format.
- [x] Design and implement the interface for the stock market.
- [x] Implement the different analysis as functions in the program.
- [x] Integrate them all in the main interface.
- Save the Stock market data in the CSV file.


Got the HTML data using urlopen and used beautifulsoup to parse the HTML data. 
```

def getPage(url):
  html = urlopen(url)
  bs = BeautifulSoup(html.read(), 'html.parser')
  return bs
  
```

After debugging and researching a lot, I found country list is in the 'tv-dropdown__item-text' class. So, I used the beautifulsoup parse method to get all the 'tv-dropdown__item-text' class in the countryList, after that I used the core python function to store the country in the countries list.

```
def getCountries(content):
  countries=[]
  countryList=content.findAll(class_='tv-dropdown__item-text')
  for country in countryList:
    countries.append(country.get_text())
    print(country.get_text())
  return countries
```

Since the link changes with the country name, so I coded the separate function to get the particular link according to the country.

```
def getCountryLink(content,countryName):
    
  countryList=content.findAll(class_='tv-dropdown__item')
  for country in countryList:
    # top remove the whitespace from beginning and the end
    name=country.get_text().strip()
    tmp=country.attrs['href'].split('/')[2].split('-')[1]
    if str(name)==str(countryName):
      return tmp
  return "No country link found!"
```

After researching and debugging, I found that the stocks are in tr tag. So I used beautifulsoup function findAll to extract and print the stocks.

```
def getStocks(content):
  """
  Utilty function used to get a content string from a Beautiful Soup
  object and a selector. Returns an empty string if no object
  is found for the given selector
  """
  nameList = content.findAll('tr')
  for i in range(1,len(nameList)):
      for name in nameList[i]:
          print(name.get_text())
      print("\n")
  return True  
```


### Are you able to keep to your plan? Looking back at what you’ve actually done, is the difference accountable to bad planning (i.e. not anticipating what needed to be done), bad execution (not doing it), or something else?
It's pretty hard to extract the data from HTML format and display it on the console. I struggled a lot in finding the datatype in the HTML format and extracting that data. I am trying to use the python core feature more than third party library, so I have to make my functions to extract the data.
From this project, I got better at writing functions, debugging, importing functions from another file, getting the input, and extracting the data from the raw.

Here's the link to my trinket:
<iframe src="https://trinket.io/embed/python3/54256b5176" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
