# Importing the necessary modules
import requests
from bs4 import BeautifulSoup

# Defining the URL of the webpage to scrape
url = "https://en.wikipedia.org/wiki/Web_scraping"

# Sending a request to the webpage and get the response
response = requests.get(url)

# Parsing the HTML content of the webpage using BeautifulSoup
soup = BeautifulSoup(response.content, 'html.parser')

# Extracting the title of the webpage from the <title> tag
title = soup.title.text

# Printing the title of the webpage
print("The title of the webpage is:", title)

# Extracting all the links from the webpage and store them in a list
links = []
for link in soup.find_all('a'):
    href = link.get('href')
    if href is not None:
        # Checking if the link is an internal link
        if href.startswith('/wiki/'):
            # Removing
            any URL fragments from the link
            href = href.split('#')[0]
            # Adding the base URL to the link
            href = 'https://en.wikipedia.org' + href
            links.append(href)

# Printing the number of links found in the webpage
print("Found", len(links), "links in the webpage.")

# Printing the links found in the webpage
print("Links in the webpage:")
for i, link in enumerate(links):
    print(str(i+1) + ". " + link)

# Writing the links found in the webpage to a file
filename = "links.txt"
with open(filename, 'w') as file:
    for link in links:
        file.write(link + "\n")

# Printing a message to confirm that the links have been written to a file
print("The links have been written to the file", filename)

 
