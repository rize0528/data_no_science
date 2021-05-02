---
title: EP8 「量化交易員的工作日常」
tags: 資料不科學幹話天地
credit: Riz Hsu
---

# 「量化交易員的工作日常」 
```
資料不科學幹話天地 - 第八集
主持人 Kyle
節目時間: 4/25 22:00
```

* 講者角色：PM，在ML系統中是管理Model performance的，主要是要扛責任，還是要寫code。要負責盈虧。
* DS應用在金融面有很多面向，舉例像是股市signal中的sentiment資料

    ```Q: sentiment資料在股市分析有用嗎```
    * A: 很有用

    ```Q: 需要跟其他資料correlate嗎？```
    * A: 不需要，其本身就是一個客觀的事實。而且越來越有用。什麼樣的news sentiment比較有用就很看用途，而且要看市場。

    ```Q: 主要是看哪個Region的sentiment news? 有亞洲的嗎？```
    * A: 主要是美國的，亞洲的不清楚。

    ```Q: Sentiment是多類別的嗎？ 你們有在用categorical的sentiment data嗎？```
    * A: 主要使用是比較continous的。 但沒有偏向，都是看資料來源taxonomy來做。

    ```Q: 能否聊聊台灣Quantitative Researcher的過往...```
    * A: 常常假日加班，當然Performance是看排名的，在這種競爭為基調的環境，一鬆懈就會被超越，就是辛苦的地方。

    ```觀眾提問: 好奇 evaluation 的框架大概會考慮哪些？是完全以歷史回測結果當作最終判斷嗎？有沒有測出來賺比較少、但因為其他考量還是會採用的情況？```
    * A: 不完全以歷史結果當作主要依據。首先光從歷史回測結果就有多種定義，根據長度、市場跟Cover的目標不同就不同。 

    ```Q: 怎麼定義Quan的領域的overfitting?```
    * A: 還是傳統ML的做法。有Train/Test/Validation data。 

    ```Q: Deep learning想要切入金融圈，目前的發展與前景在QR有什麼機會嗎。 是技術變好了嗎，還是找到什麼方法可以tune模型。```
    * A: 不是主要，但是重要性變高。目前已經可以賺錢，但還不是主角。

    ```Q: DL是用什麼寫的？```
    * A: C++ or Python

    ```Q: Covid19對Quan.有什麼影響？```
    * A: 基本上來說是好事，從學理上來說。有波動才有辦法賺錢。

    ```Q: 怎麼看GME事件```
    * A: 這是一個隨機性的風險，事前很難預測到。關鍵在風險管理有沒有做好，這是無法預測到的。比誰事件發生後的操作好。 Reddit是否要放入training data就是事後的選擇了。