# KBO-s-play-by-play-simple-

簡易的使用BeautifulSoup4去抓取韓國職棒的資料

==============================================================================

開發環境: 

Anaconda2-juptyer
Step 1至官網下載Anaconda2:

![image](https://github.com/datsxhero/KBO-s-play-by-play-simple-/blob/master/%E6%9C%AA%E5%91%BD%E5%90%8D.png)

Step 2 依序點選下載步驟

![image](https://github.com/datsxhero/KBO-s-play-by-play-simple-/blob/master/%E6%9C%AA%E5%91%BD%E5%90%8D1.png)

![image](https://github.com/datsxhero/KBO-s-play-by-play-simple-/blob/master/%E6%9C%AA%E5%91%BD%E5%90%8D3.png)

之後按下安裝並等候

![image](https://github.com/datsxhero/KBO-s-play-by-play-simple-/blob/master/%E6%9C%AA%E5%91%BD%E5%90%8D6.5.png)

![image](https://github.com/datsxhero/KBO-s-play-by-play-simple-/blob/master/%E6%9C%AA%E5%91%BD%E5%90%8D4.png)

安裝完成

![image](https://github.com/datsxhero/KBO-s-play-by-play-simple-/blob/master/%E6%9C%AA%E5%91%BD%E5%90%8D5.png)


Google InfoLite

至Google下載工具即可

![image](https://github.com/datsxhero/KBO-s-play-by-play-simple-/blob/master/%E6%9C%AA%E5%91%BD%E5%90%8D6.png)

===============================================================================

開發:

使用InfoLite工具至目標網站圈選要抓取的play-by-play局次

![image](https://github.com/datsxhero/KBO-s-play-by-play-simple-/blob/master/%E6%9C%AA%E5%91%BD%E5%90%8D9.png)

開啟Anaconda2中的juptyer

![image](https://github.com/datsxhero/KBO-s-play-by-play-simple-/blob/master/%E6%9C%AA%E5%91%BD%E5%90%8D7.png)

參考以下範例程式碼說明(此程式碼為一部分一部分去抓取範圍)

![image](https://github.com/datsxhero/KBO-s-play-by-play-simple-/blob/master/%E6%9C%AA%E5%91%BD%E5%90%8D8.png)



範例程式碼

以 KT Wiz 7:4 Kia Tigers August 16, 2016為例 



import requests                     //引入requests
from bs4 import BeautifulSoup       //引入BeautifulSoup套件


res = requests.get("https://mykbostats.com/games/4714-KT-vs-Kia-20160816")  //和網站要求資料

soup = BeautifulSoup(res.text)

for item in soup.select('#live_inning_details'):            //利用工具InfoLite將play-by-play的1~9場次圈選起來

    
print item.select('#inning-detail-1')[0].text.strip()      //印出各場次的play-by-play(更換要抓得局次只需改變#inning-detail-中局次數即可)
 
   
print item.select('#inning-detail-2')[0].text.strip()

    
print item.select('#inning-detail-3')[0].text.strip() 

    
print item.select('#inning-detail-4')[0].text.strip()

    
print item.select('#inning-detail-5')[0].text.strip()
 
   
print item.select('#inning-detail-6')[0].text.strip()
 
   
print item.select('#inning-detail-7')[0].text.strip()
 
   
print item.select('#inning-detail-8')[0].text.strip()
 
   
print item.select('#inning-detail-9')[0].text.strip()

