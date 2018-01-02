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

    
//印出各場次的play-by-play(更換要抓得局次只需改變#inning-detail-中局次數即可)

print item.select('#inning-detail-1')[0].text.strip()      
 
   
print item.select('#inning-detail-2')[0].text.strip()

    
print item.select('#inning-detail-3')[0].text.strip() 

    
print item.select('#inning-detail-4')[0].text.strip()

    
print item.select('#inning-detail-5')[0].text.strip()
 
   
print item.select('#inning-detail-6')[0].text.strip()
 
   
print item.select('#inning-detail-7')[0].text.strip()
 
   
print item.select('#inning-detail-8')[0].text.strip()
 
   
print item.select('#inning-detail-9')[0].text.strip()

-----------------------------------------------------------
爬下資料後，整理每局最終結果

Top of the 1st inning: KT at bat



Batter #1: Lee Dae-hyung


Batter Lee Dae-hyung: Reached base on an error by shortstop


Batter #2: Oh Jung-bok


Batter Oh Jung-bok: Single to left field


1st base runner Lee Dae-hyung: Advanced to 2nd base


Batter #3: Park Kyung-soo


Batter Park Kyung-soo: Strikeout


Batter #4: Yoo Han-joon


Batter Yoo Han-joon: Single to left field


1st base runner Oh Jung-bok: Advanced to 2nd base


2nd base runner Lee Dae-hyung: Scored


Batter #5: Lee Jin-young


Batter Lee Jin-young: Base on balls


1st base runner Yoo Han-joon: Advanced to 2nd base


2nd base runner Oh Jung-bok: Advanced to 3rd base


Batter #6: Yoo Min-sang


Batter Yoo Min-sang: Single to right of right fielder


1st base runner Lee Jin-young: Advanced to 3rd base


2nd base runner Yoo Han-joon: Scored


3rd base runner Oh Jung-bok: Scored


Batter #7: Kim Sun-min


Batter Kim Sun-min: Flied out to center fielder


Batter #8: Lee Hae-chang


Batter Lee Hae-chang: Single to left field


1st base runner Yoo Min-sang: Advanced to 2nd base


3rd base runner Lee Jin-young: Scored


Batter #9: Park Ki-hyuk


Batter Park Ki-hyuk: Grounded out to third baseman

Bottom of the 1st inning: Kia at bat



Batter #1: Shin Jong-gil


Batter Shin Jong-gil: Grounded out to pitcher


Batter #2: Kim Ho-ryeong


Batter Kim Ho-ryeong: Double to left-center gap


Batter #3: Kim Joo-chan


Batter Kim Joo-chan: Home run to left field (Distance: 110m / 360ft)


2nd base runner Kim Ho-ryeong: Scored


Batter #4: Na Ji-wan


Batter Na Ji-wan: Double to right of center fielder


Batter #5: Lee Bum-ho


Batter Lee Bum-ho: Base on balls


Batter #6: Seo Dong-wook


Batter Seo Dong-wook: Reached base on a ground ball in front of second baseman


1st base runner Lee Bum-ho: Force out at 2nd


2nd base runner Na Ji-wan: Advanced to 3rd base


Batter #7: Kim Joo-hyung


Batter Kim Joo-hyung: Popped out to shortstop

--------------------------------------------------------------------------------------------
Top of the 2nd inning: KT at bat



Batter #1: Lee Dae-hyung


Substitution: shortstop Kang Han-wool out, shortstop Park Chan-ho in


Batter Lee Dae-hyung: Grounded out to second baseman


Batter #2: Oh Jung-bok


Batter Oh Jung-bok: Single to right field


Batter #3: Park Kyung-soo


Batter Park Kyung-soo: Infield single to left of third baseman


1st base runner Oh Jung-bok: Advanced to 2nd base


Batter #4: Yoo Han-joon


Batter Yoo Han-joon: Base on balls


1st base runner Park Kyung-soo: Advanced to 2nd base


2nd base runner Oh Jung-bok: Advanced to 3rd base


Batter #5: Lee Jin-young


Batter Lee Jin-young: Popped out to shortstop


Batter #6: Yoo Min-sang


Batter Yoo Min-sang: Flied out to center fielder

Bottom of the 2nd inning: Kia at bat



Batter #8: Lee Hong-gu


Batter Lee Hong-gu: Single to left field


Batter #9: Park Chan-ho


Batter Park Chan-ho: Strikeout


Batter #1: Shin Jong-gil


Batter Shin Jong-gil: Strikeout


1st base runner Lee Hong-gu: Caught stealing (catcher → shortstop tag out)

----------------------------------------------------------------------------------
Top of the 3rd inning: KT at bat



Batter #7: Kim Sun-min


Batter Kim Sun-min: Base on balls


Batter #8: Lee Hae-chang


Batter Lee Hae-chang: Strikeout


Batter #9: Park Ki-hyuk


Batter Park Ki-hyuk: Double (deflected leftward by third baseman)


1st base runner Kim Sun-min: Advanced to 3rd base


Batter #1: Lee Dae-hyung


Batter Lee Dae-hyung: Single to center field


2nd base runner Park Ki-hyuk: Scored


3rd base runner Kim Sun-min: Scored


Batter #2: Oh Jung-bok


Batter Oh Jung-bok: Single to right of right fielder


1st base runner Lee Dae-hyung: Advanced to 2nd base


Batter #3: Park Kyung-soo


Pitching change: Hong Gun-hee → Park Joon-pyo


Batter Park Kyung-soo: Grounded out to pitcher


1st base runner Oh Jung-bok: Advanced to 2nd base


2nd base runner Lee Dae-hyung: Advanced to 3rd base


Batter #4: Yoo Han-joon


Batter Yoo Han-joon: Infield single in front of shortstop


2nd base runner Oh Jung-bok: Advanced to 3rd base


3rd base runner Lee Dae-hyung: Scored


Batter #5: Lee Jin-young


Batter Lee Jin-young: Flied out to right fielder

Bottom of the 3rd inning: Kia at bat



Batter #2: Kim Ho-ryeong


Batter Kim Ho-ryeong: Infield single to left of second baseman


Batter #3: Kim Joo-chan


[19:55-19:56] KT requests replay review on play involving Kim Ho-ryeong. Call on field: Safe; Call after review: Safe


Batter Kim Joo-chan: Infield single to right of second baseman


1st base runner Kim Ho-ryeong: Advanced to 2nd base


Batter #4: Na Ji-wan


Batter Na Ji-wan: Single to left field


1st base runner Kim Joo-chan: Advanced to 2nd base


2nd base runner Kim Ho-ryeong: Scored


Batter #5: Lee Bum-ho


Pitching change: Ju Kwon → Ko Young-pyo


Batter Lee Bum-ho: Flied out to left fielder


Batter #6: Seo Dong-wook


Batter Seo Dong-wook: Reached base on a ground ball in front of pitcher


1st base runner Na Ji-wan: Force out at 2nd


2nd base runner Kim Joo-chan: Advanced to 3rd base


Batter #7: Kim Joo-hyung


Batter Kim Joo-hyung: Strikeout

---------------------------------------------------------------------------------------------
Top of the 4th inning: KT at bat



Batter #6: Yoo Min-sang


Batter Yoo Min-sang: Single to right-center gap


Batter #7: Kim Sun-min


Batter Kim Sun-min: Sacrifice bunt to first baseman


1st base runner Yoo Min-sang: Advanced to 2nd base


Batter #8: Lee Hae-chang


Batter Lee Hae-chang: Strikeout


Batter #9: Park Ki-hyuk


Batter Park Ki-hyuk: Strikeout

Bottom of the 4th inning: Kia at bat



Batter #8: Lee Hong-gu


Batter Lee Hong-gu: Grounded out to shortstop


Batter #9: Park Chan-ho


Batter Park Chan-ho: Grounded out to shortstop


Batter #1: Shin Jong-gil


Batter Shin Jong-gil: Base on balls


Batter #2: Kim Ho-ryeong


Batter Kim Ho-ryeong: Strikeout

--------------------------------------------------------------------------------------
Top of the 5th inning: KT at bat



Batter #1: Lee Dae-hyung


Batter Lee Dae-hyung: Grounded out to pitcher


Batter #2: Oh Jung-bok


Batter Oh Jung-bok: Grounded out to third baseman


Batter #3: Park Kyung-soo


Batter Park Kyung-soo: Strikeout

Bottom of the 5th inning: Kia at bat



Batter #3: Kim Joo-chan


Batter Kim Joo-chan: Uncaught third strike


Batter #4: Na Ji-wan


Batter Na Ji-wan: Grounded out to shortstop


Batter #5: Lee Bum-ho


Batter Lee Bum-ho: Single to left-center gap


Batter #6: Seo Dong-wook


Batter Seo Dong-wook: Strikeout

----------------------------------------------------------------------
Top of the 6th inning: KT at bat



Batter #4: Yoo Han-joon


Batter Yoo Han-joon: Single to right-center gap


Batter #5: Lee Jin-young


Pitching change: Park Joon-pyo → Kim Myung-chan


Batter Lee Jin-young: Grounded into double play


1st base runner Yoo Han-joon: Force out at 2nd


Batter #6: Yoo Min-sang


Batter Yoo Min-sang: Single to right of left fielder


Batter #7: Kim Sun-min


Substitution: 1st base runner Yoo Min-sang out, pinch runner Kim Yeon-hoon in


Batter Kim Sun-min: Base on balls


1st base runner Kim Yeon-hoon: Advanced to 2nd base


Batter #8: Lee Hae-chang


Pitching change: Kim Myung-chan → Kim Yoon-dong


Substitution: 1st base runner Kim Sun-min out, pinch runner Moon Sang-cheol in


Batter Lee Hae-chang: Base on balls


1st base runner Moon Sang-cheol: Advanced to 2nd base


2nd base runner Kim Yeon-hoon: Advanced to 3rd base


Batter #9: Park Ki-hyuk


Batter Park Ki-hyuk: Flied out to center fielder

Bottom of the 6th inning: Kia at bat



Batter #7: Kim Joo-hyung


Pitching change: Ko Young-pyo → Uhm Sang-baek


Position change: pinch runner Kim Yeon-hoon moved to third baseman


Position change: pinch runner Moon Sang-cheol moved to first baseman


Batter Kim Joo-hyung: Grounded out to shortstop


Batter #8: Lee Hong-gu


Batter Lee Hong-gu: Base on balls


Batter #9: Park Chan-ho


Batter Park Chan-ho: Popped out to second baseman


Batter #1: Shin Jong-gil


Pitching change: Uhm Sang-baek → Bae Woo-yeol


Batter Shin Jong-gil: Base on balls


1st base runner Lee Hong-gu: Advanced to 2nd base


Batter #2: Kim Ho-ryeong


Batter Kim Ho-ryeong: Flied out to center fielder

--------------------------------------------------------------------
Top of the 7th inning: KT at bat



Batter #1: Lee Dae-hyung


Batter Lee Dae-hyung: Grounded out to catcher


Batter #2: Oh Jung-bok


Batter Oh Jung-bok: Flied out to center fielder


Batter #3: Park Kyung-soo


Batter Park Kyung-soo: Flied out to center fielder

Bottom of the 7th inning: Kia at bat



Batter #3: Kim Joo-chan


Substitution: left fielder Oh Jung-bok out, left fielder Ha Joon-ho in


Batter Kim Joo-chan: Grounded out to shortstop


Batter #4: Na Ji-wan


Batter Na Ji-wan: Flied out to left fielder


Batter #5: Lee Bum-ho


Batter Lee Bum-ho: Single to center field


Batter #6: Seo Dong-wook


Batter Seo Dong-wook: Flied out to center fielder

--------------------------------------------------------------------------
Top of the 8th inning: KT at bat



Batter #4: Yoo Han-joon


Batter Yoo Han-joon: Strikeout


Batter #5: Pinch hitter Kim Dong-myung batting for Lee Jin-young


Batter Kim Dong-myung: Strikeout


Batter #6: Kim Yeon-hoon


Batter Kim Yeon-hoon: Foul fly caught by shortstop

Bottom of the 8th inning: Kia at bat



Batter #7: Kim Joo-hyung


Position change: pinch hitter Kim Dong-myung moved to designated hitter


Batter Kim Joo-hyung: Base on balls


Batter #8: Lee Hong-gu


Batter Lee Hong-gu: Grounded out to first baseman


1st base runner Kim Joo-hyung: Advanced to 2nd base


Batter #9: Park Chan-ho


Batter Park Chan-ho: Grounded out to third baseman


2nd base runner Kim Joo-hyung: Advanced to 3rd base


Batter #1: Shin Jong-gil


Pitching change: Bae Woo-yeol → Lee Chang-jae


Batter Shin Jong-gil: Flied out to left fielder

-------------------------------------------------------------------
Top of the 9th inning: KT at bat



Batter #7: Moon Sang-cheol


Pitching change: Kim Yoon-dong → Kwak Jung-cheol


Batter Moon Sang-cheol: Double to right-center gap


Batter #8: Lee Hae-chang


Batter Lee Hae-chang: Sacrifice bunt to third baseman


2nd base runner Moon Sang-cheol: Advanced to 3rd base


Batter #9: Park Ki-hyuk


Batter Park Ki-hyuk: Popped out to second baseman


Batter #1: Lee Dae-hyung


Batter Lee Dae-hyung: Strikeout

Bottom of the 9th inning: Kia at bat

Batter #2: Kim Ho-ryeong


Pitching change: Lee Chang-jae → Kim Jae-yoon


Batter Kim Ho-ryeong: Base on balls


Batter #3: Kim Joo-chan


Batter Kim Joo-chan: Grounded out to shortstop


1st base runner Kim Ho-ryeong: Advanced to 2nd base


Batter #4: Na Ji-wan


Batter Na Ji-wan: Flied out to right fielder


Batter #5: Lee Bum-ho


Batter Lee Bum-ho: Double to right of right fielder


2nd base runner Kim Ho-ryeong: Scored


Batter #6: Seo Dong-wook


Substitution: 2nd base runner Lee Bum-ho out, pinch runner Choi Won-joon in


Pitch #1: Ball


Pitch #2: Called Strike


Pitch #3: Called Strike


Pitch #4: Swing


Batter Seo Dong-wook: Strikeout

End of Game

============================================================================

程式碼優化理論: 必須去了解網站的架構、每個標籤所賦予的意義。

可以試著撰寫for迴圈去改變所邀要求的網址的對戰及日期部分，
'#inning-detail-9'的局次資料改變同理(要注意比賽是否提早結束或變為延長賽)

最後在存成txt檔或csv檔時，要注意有些英文外的語言的存取，
要用unicode或UTF-8等形式，某些資料才不會遺失。

=============================================================================
