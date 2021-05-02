---
title: EP9 「追尋資料人才的艱辛之旅：來聊聊面試吧！」 
tags: 資料不科學幹話天地
credits: riz_hsu
---

# 「追尋資料人才的艱辛之旅：來聊聊面試吧！」Part.3
    ## 面試題目三兩事篇

* 資料不科學幹話天地 - 第九集
* 主持人 Kyle@Singapore
* 節目時間: 5/2 22:00

```本週內容簡介```

這次想聊一下設計技術面試題目（coding challenge）的心得跟一些業界觀察。這邊的面試題目會涵蓋DE與DS兩個角色，當然也會聊聊其中異同。身為一個Hiring manager到底要怎麼找到心目中理想的人選？什麼樣的題目才是合適、不刁鑽卻又能夠鑑別出專業技能的好題目呢？

我會分享我自己設計題目的心得，以及實際操作面試後的觀察。厲害的人都怎麼解題？不適任的人又都卡在什麼關卡？一起來聽故事吧！

```正題與背景故事```
## 談到技術面試
談到現場考DS或DE的實作能力，通常是用現成的服務或是客製化的題目，有分offline或online(幾乎都是限時的)實作，還另外一種就是白板或是同時與跟著candidates一起做，這樣可以看到候選人的人格特質。

```
常見的線上測驗平台：
* Hacker rank 
* Codility
```

使用線上測試(或是上傳答案的那種)，基本上都需要有標準答案，所以沒辦法看到candidate實作過程中的貓膩(?!)。 而這種過程通常是判斷一個候選人是否適合的關鍵點。

* Take-home vs online

假設使用客製化，沒有標準答案的考題，也還是會分成線上會線下測。或者說是線上或者回家作業。

回家作業的好處是可以把題目設計得更細緻，能夠測到更深入的技能。但缺點是他大幅延長了hiring pipeline的時間，而且有些candidate要求延長你也沒轍，很難知道他是解不出來要花更多時間還是真的私下太忙。同時candidate解完題目你還必須跟他另外安排時間過內容。

線上互動實作好處是直接觀察candidate解題過程，包括他用甚麼OS，IDE，習慣terminal還是GUI全部都一目了然。還有另一個是觀察他遇到問題怎麼解決，他會看官方文件嗎?他如何做網路搜尋?這些都很能幫助我們判斷candidate是不是有獨立解決問題的能力。線上互動也能縮短pipeline的時間。當然比起回家作業，缺點就是題目設計不可能做到太深入的技術細節。

### 聊聊面試Data Engineer(DE) and Data Scientist(DS)的一些心得
* 主要考了解資料的能力，很多candidates沒有能力處理raw data的。
* 傳統考試通常是從DB開始，所以會有技術限制。像是會被限制使用postgresql or mysql等等。但每個人的tech stack會不太一樣，所以不見得能測到這個人真正的價值。
* 測試用raw data出發比較好，並不限制使用的技術去分析這份資料與可以自由發問。
* 測試candidate的資料格式：
    * 不建議csv，太簡單惹
    * csv通常也不太會是你的raw data的格式
    * 像是json or parquet等等實際在application溝通中會使用的格式來測試比較實際。
    * 用jsonline來存每一筆單純的raw data，滿常會使用來存一整個data batch。
* 講一些實際考試的例子：
    * DE part (時間1hr)
        1. 讀取raw data部分
            * 用Text editor打開，把第一行丟到json prettify等網站去解看看。
                * 也有習慣用terminal的，就會用類似語法去看：`head -n 1 file.jsonline | jq ...`
            * 或是使用pandas： `pd.read_json(file, lines=True)`
            * 又或是用pandas的json_normalize直接進行資料攤平：`pd.json_normalize(data, max_level=N)`
            * 好的candidate很快就會用類似以上方法就把資料讀進來。
            * 通常，在這一關會刷掉一半人。
        2. 怎麼放進DB
            * 這邊也會刷掉一半，所以到這一步只剩25
            * 也有人直接用自己的RDS來做，或是用mysql的docker image。
            * 如果這關過了基本上第三步也不會有問題。
        3. 自己要怎麼讀這個DB
            * DE的考題因為前面已經花了不少時間了，所以大多都是簡易的query就能得到答案的問題。 
    * DS part (時間1.5hr)
        1. 直接回答怎麼做data query，題目會比較難。
        2. 會有visulization & modeling ( or EDA(Exploratory Data Analysis))
            * DS較偏重於溝通，所以有些人會去測visulization。
            * DS做完以上題目後，也會再更花時間與候選人深入交流。 

