# focus-dom
an entry to spider
# -*- coding: utf-8 -*-
from bs4 import BeautifulSoup
import requests
allin = requests.get('http://www.soupu.com/UIPro/BusniessProject.aspx')
content = allin.text
import re
bigger = re.findall('c_fl child">(.*?)c_fl">',content,re.S)[0]
soup = BeautifulSoup(bigger,'html.parser',from_encoding='utf-8')
link = soup.find('a',href=re.compile(r'shandong'))
print link.name,link['href'],link.get_text()
# how to add multipe sentences, wear mask and cookies, write to mysql
