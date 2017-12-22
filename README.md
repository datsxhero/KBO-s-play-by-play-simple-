# KBO-s-play-by-play-simple-

簡易的使用BeautifulSoup4去抓取韓國職棒的資料

==============================================================================
開發環境: 

Anaconda2-juptyer

Python3.6

Google InfoLite

===============================================================================

以 KT Wiz 7:4 Kia Tigers August 16, 2016為例 



import requests                     //引入requests
from bs4 import BeautifulSoup       //引入BeautifulSoup套件


res = requests.get("https://mykbostats.com/games/4714-KT-vs-Kia-20160816")  //和網站要求資料

soup = BeautifulSoup(res.text)

for item in soup.select('#live_inning_details'):            //利用工具InfoLite將play-by-play的1~9場次圈選起來

    
print item.select('#inning-detail-1')[0].text.strip()           //印出各場次的play-by-play
 
   
print item.select('#inning-detail-2')[0].text.strip()

    
print item.select('#inning-detail-3')[0].text.strip()

    
print item.select('#inning-detail-4')[0].text.strip()

    
print item.select('#inning-detail-5')[0].text.strip()
 
   
print item.select('#inning-detail-6')[0].text.strip()
 
   
print item.select('#inning-detail-7')[0].text.strip()
 
   
print item.select('#inning-detail-8')[0].text.strip()
 
   
print item.select('#inning-detail-9')[0].text.strip()

