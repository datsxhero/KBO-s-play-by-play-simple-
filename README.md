# KBO-s-play-by-play-simple-
簡易的使用BeautifulSoup4去抓取韓國職棒的資料


以 KT Wiz 7:4 Kia Tigers August 16, 2016為例 

import requests

from bs4 import BeautifulSoup
res = requests.get("https://mykbostats.com/games/4714-KT-vs-Kia-20160816")
soup = BeautifulSoup(res.text)
for item in soup.select('#live_inning_details'):
    print item.select('#inning-detail-1')[0].text.strip()
    print item.select('#inning-detail-2')[0].text.strip()
    print item.select('#inning-detail-3')[0].text.strip()
    print item.select('#inning-detail-4')[0].text.strip()
    print item.select('#inning-detail-5')[0].text.strip()
    print item.select('#inning-detail-6')[0].text.strip()
    print item.select('#inning-detail-7')[0].text.strip()
    print item.select('#inning-detail-8')[0].text.strip()
    print item.select('#inning-detail-9')[0].text.strip()
