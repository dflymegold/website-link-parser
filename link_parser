import requests
import pandas as pd
from bs4 import BeautifulSoup

def extract_all_links(site):
    html = requests.get(site).text
    soup = BeautifulSoup(html, 'html.parser').find_all('a')
    links = [link.get('href') for link in soup]
    return links
site_link = 'https://serenabutelondon.com/'
all_links = extract_all_links(site_link)
df = pd.DataFrame(all_links,columns = ['Link'])
instagram =df[ df.Link.str.contains('https://www.instagram.com') ]
facebook = df [df.Link.str.contains('https://www.facebook.com')]
twitter = df [df.Link.str.contains ('https://twitter.com')]
print (instagram,facebook,twitter)
