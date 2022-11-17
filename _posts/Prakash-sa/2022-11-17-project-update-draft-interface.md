---
layout: post
author: Prakash-sa
title: "Prakash's Final Project Interface"
---

# Final Project Interface Start

For the final project, as stated in the inital project proposal, I am planning to do the data processing. I am going to do the web scraping of https://www.tradingview.com/. 
I will do the Data Cleaning, Visualization and Storing with the python programming.

I will clean and visualize the Stock market data from the different country. It will include the feature of the performance, rise and fall, Large cap, Small cap, Top gainers, Most active, etc.

- For the data, I am using the HTML format from the website.

I feel the following is a good plan to create the project:

- [x] Get the data.
- [x] Extract the data from the HTML
- Design and implement the interface for the stock market
- Implement the different analysis as functions in the program
- Integrate them all in the main interface.
- Save the Stock market data in the CSV file.

## Extracting the data

I sucessfully got the data using BeautifulSoup, urllib library.

```python
from urllib.request import urlopen
from urllib.request import urlopen
from bs4 import BeautifulSoup

dataUrlList=["all-stocks","large-cap","small-cap","largest-employers","high-dividend","highest-net-income","highest-cash","gainers","losers","active","pre-market-gainers","pre-market-losers","active-pre-market-stocks","pre-market-gappers","after-hours-gainers","after-hours-losers","active-after-hours-stocks","unusual-volume","most-volatile","high-beta","best-performing","highest-revenue","most-expensive","penny-stocks","pink-sheet-stocks","overbought","oversold","ath","atl","52wk-high","52wk-low"]
countryList=["usa","argentina","australia","bahrain","belgium","brazil","canada","chile","china","colombia","denmark","egypt","estonia","finland","france","germany","greece","hong-kong","hungary","iceland","india","indonesia","israel","italy","japan","latvia","lithuania","luxembourg","malaysia","mexico","netherlands","new-zealand","nigeria","norway","peru","philippines","poland","portugal","qatar","romania","russia","ksa","serbia","singapore","slovakia","south-africa","korea","spain","sweden","switzerland","taiwan","thailand","turkey","uae","united-kingdom","venezuela","vietnam"]

def getUrl(country,feature):
    return "https://www.tradingview.com/markets/stocks-"+country+"/market-movers-"+feature+"/"

def getNewsUrl(country):
    return "https://www.tradingview.com/markets/stocks-"+country+"/news/"

    
dataUrl="https://www.tradingview.com/markets/stocks-usa/market-movers-all-stocks/"
html = urlopen(dataUrl)
print(html.read())

html = urlopen(dataUrl)
bs = BeautifulSoup(html.read(), 'html.parser')
print(bs)
print(bs.h1)
```

Extracting the stocks data from HTML

```python

nameList = bs.findAll('tr')
for i in range(1,len(nameList)):
    for name in nameList[i]:
        print(name.get_text())
    print("\n")
   
}
```

## Next Steps
- I want to create the menu dictionary and allow the user to choose the country and feature they want to select for the stock. 
- Add the functionality to save the data in the CSV.


Trinket Embed for the Interface:

<iframe src="https://trinket.io/embed/python3/54256b5176" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
