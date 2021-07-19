#WEB SCRAPPING IN PYTHON
In this post we are going to scrape an ecommerce website.
We'll get into each individual product page and retrieve our information from there.
This is the ```https://www.thewhiskyexchange.com/c/35/japanese-whisky``` WEBSITE we are going to scrape – it's an online shop that sells whisky.



##Getting started

Download or clone the project from github
```
$ git clone https://github.com/ShamsAwais/webscraper.git
```
**How to setup the scrapping project**
Our setup is pretty simple. 
Just create a folder and install Beautiful Soup, pandas, and requests.
To create a folder and install the libraries, enter the commands given below.
I am assuming that you have already installed Python 3.x.

```
mkdir scraper 
pip install beautifulsoup4 
pip install requests
pip install pandas
```
Now, create a file inside that folder and name it anything you like.
I am using the name scraper.py.
We are going to import requests, pandas, and bs4.
```
import requests
from bs4 import BeautifulSoup
import pandas as pd
```
Now, we are going to set the base URL of the main page because we'll need that when we construct our URLs for each of the individual products.
Also, we will send a user-agent on every HTTP request, because if you make GET request using requests then by default the user-agent is Python which might get blocked.
So, to override that, we will declare a variable which will store our user-agent.
```
baseurl = "https://www.thewhiskyexchange.com"
headers = {'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/89.0.4389.82 Safari/537.36'}
```
