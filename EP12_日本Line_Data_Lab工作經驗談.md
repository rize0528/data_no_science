---
title: EP12 「日本Line Data Lab工作經驗談」 
tags: 資料不科學幹話天地
credits: riz_hsu
---

# 日本Line Data Lab工作經驗談

* 資料不科學幹話天地 - 第十二集
* 主持人 Kyle
* 節目時間: 6/6 22:00

```本週內容簡介```
> 1. Line Data Lab組織架構與分工
> 2. Tech Stack (聽說用私有雲?) DE／DS用什麼語言
> 3. 團隊的國際化程度?
> 4. 做過的有趣的project分享
> 5. 日文不好的話在日本工作會有什麼障礙?
> 6. 日本業界面試經驗談!

```閒聊時間```

Thomas是在日本line福岡工作，擔任機器學習工程師，但目前已經拿到其他公司的offer，也在日本工作了已經四年。

大學跟研究所都在台灣念，背景是NLP相關，在台灣新創待過。


```節目內容```

## Line Data Lab組織介紹

datalab只有日本有，主要跟日本的服務合作，會做推薦系統與dashboard。
2019發現太多team會提供infra，所以data lab把infra移出。
目前的業務主要focus內容的部分

ML engineer在data lab還是有相當一部分要處理infra，比方說資料的串接，workflow (airflow)等等，因為中央化的資料串接並不是那麼快，有需要的資料可能還沒被開發出pipeline就要自己來。

## Line Private Cloud簡介

infra team用openstack。

另外有一個team有維護hadoop cluster。(一樣在私有雲)

類似小型的aws，支援vm, db, k8s等等service。
Line data center有兩處，是在日本(東京與福岡) & 新加坡。

## Line DS & DE的一些問題

> Q: DS會需要deploy嗎?
> 
> A: 主要是做報告與stack holder談，需要日本語能力。 內部文件是用英文，對外寫應該是以日本語為主。
> LINE有買RStudio enterprise! (for DS)

> Q: Line的DS tech stack是什麼？
> 
> A: Line DS主要用R，有若干Ｒ社群大神在那邊。而Line開會有時候會有翻譯在場，就是現場帶耳麥讓口譯(6M~8M年薪)直接翻譯。
> DE以python為主。

> Q: 有做過哪些有趣的project?
>
> A: Line貼圖審查，幫忙做影像搜尋，會審查比如暴力、成人、政治不正確等等。主要會用hash來標記貼圖，貼圖數量有3億筆。
> 審查本身還是人工，模型不會做最終判斷而是輔助人工
> 影像搜尋幫忙處理審查重複上傳(投機者)或者是抄襲的內容
> 因為資料量非常大即使是透過ANN搜尋還是要把embedding壓縮到bit (比方說512B)

> Q: 選擇離開Line的理由？
>
> A: 一直沒有好的manager來帶領，主要是沒有很實質的管理。 想做直接面對使用者的功能。 Line東京都是說日文，比較排外，所以不太考慮。

> Q: 東京跟福岡data lab差異?
> 
> A: 在東京因為日本員工比較多所以對日語的要求會提高，即使是ML engineer也變得要會說日文比較好。國際化程度福岡高出許多。
> 東京對應的使用者相關功能開發項目也比較多。
> 如果日文溝通沒問題還是推薦的。

> Q: 日文能力需要到熟練敬語的程度嗎?
>
> A: 其實不太需要。主要是LINE本身還是相對國際化的企業，所以不是那麼傳統的日語商業環境。

> Q: 聊一下日本業界面試經驗？
> 
> A: Tier1的公司都會需要刷題，ML & system design都會考。
> 日文不夠好會少一些機會，但跨國大型公司基本上還是沒問題能用英文即可。

> Q: 下一步?
> 
> A: 前進東京G社，做跟question hub相關的開發項目。
