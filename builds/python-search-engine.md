# Python Search Engine

> 1. First check if `python3` is installed in your terminal.

```python
python3 --version
```

> 2. Next, type `python3` to enter python terminal

```python
# Linux or Mac
python3

# Windows
python
```

> 3. In the **python** terminal verify libraries are installed

```python
import requests
import sys
import webbrowser
import bs4
```

> 3a. If you have all of the libraries installed move ahead to need to \# 4. To import any of the 4 libraries exit out of the python terminal.

```cpp
# Exits terminal python session
quit()
```

> Install libraries you need

```python
# For Linux and Mac
pip3 install requests
pip3 install sys
pip3 install webbrowser
pip3 install bs4

# For Windows
pip install requests
pip install sys
pip install webbrowser
pip install bs4
```

> 4. Now open your text editor and create a new file

```python
browserSearch.py
```

```python
import requests
import sys
import webbrowser
import bs4

# request to web browser using get() to google url, which concatenates with what you want to search for
# by concatenating the get request to an empty string, and attaching the join() method (which takes two string and concatenates them)
# with the parameter from the system (or command line) using sys.argv, and inside that we want to grab the parameter by using [1:]
res = requests.get('https://google.com/search?q=' + ''.join(sys.argv[1:]))
# takes the first parameter in red and allows us to search for it using raise_for_status() (build in method for this library)
# which enters the queue
res.raise_for_status()
# creating a soup from Beautiful library that passes on the res parameter with text format, then call the HTML parser
soup = bs4.BeautifulSoup(res.text, "html.parser")
# linkElements is made available which helps take this soup and selects the result which we are getting in this entire HTML parser
# and select only the links by grabbing the regex by going for a total raw request, and select the links
linkElements = soup.select('.r a')
# opening 5 links in the browser, and get length of links
linkToOpen = min(5, len(linkElements))
# loop through linkToOpen and open each link individually in the tab of your browser
for i in range(linkToOpen):
    # opens web browser and pass in the google parameter and concatenate it with linkElements which takes i as a parameter
    # then add a get() request with the parameter href to guide what tags to select
    webbrowser.open('https://google.com' + linkElements[i].get('href'))
```

> To run the program, in the terminal `cd` to the `files location`. Type `ls` to verify you see the `.py` file, then in the terminal type

```text
python3 browserSearch.py 'what you want to search for'
```

