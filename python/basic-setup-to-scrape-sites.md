# Basic Setup to Scrape Sites

Using Selenium and BeautifulSoup. Saving the websites data to a file.

```python
from selenium import webdriver
from bs4 import BeautifulSoup

url = "https://google.com"
browser = webdriver.Chrome('../drivers/chromedriver')
browser.get(url)

import time
# allow page to load
time.sleep(5)
html = browser.page_source
# passing html to Beautiful Soup parser
soup = BeautifulSoup(html, 'html.parser')
# save scraped data (soup) to txt file, and output soup data to txt file
with open('scraped.txt', 'w') as file:
  # save file as string
  file.write(str(soup))
```

