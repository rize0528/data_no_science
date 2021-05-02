---
title: EP7 「雲端運算服務踩雷最前線！聊聊在AWS上實作ETL的心得」 
tags: 資料不科學幹話天地
credits: Kyle、Riz
---

# 「雲端運算服務踩雷最前線！聊聊在AWS上實作ETL的心得」 

* 資料不科學幹話天地 - 第七集
* 主持人 Kyle
* 節目時間: 4/18 22:00

## 前言
TEST 

### 來賓簡介

- TrendMicro軟體工程師、資料科學家
- Tomofun機器學習工程師
- KKLab資料工程師

### 什麼是ETL

簡言之就是把資料從A點搬運至B點，並且在這過程中進行任何必要或有助於下游應用開發的資料處理工作。

### 為什麼是AWS?本系列節目宗旨

- 作為三大雲端運算服務市占最高的供應商，非常多的公司都使用其服務。
- 雲端運算應用發展已進入一個不可逆的大勢之趨，即使不使用公有雲，也很難不觸碰到相關的分散式運算開源框架
- 因為主持人私心想多學學AWS上的開發經驗
- 對於不熟AWS但有志於發展資料領域職涯的人，

## 聊聊AWS Glue

- 起EMR要做一堆bootstrap，provision也要花很多時間(8~10mins)。 對於想要立刻做PoC的心會消火。
- Glue會幫你準備container，不到幾秒就好了。 不支援preset jupyter notebook。
- Glue也會幫你用crawler去爬S3的資料自動去生成schema。如果你的datalake是用S3然後放上一堆strutrual or unstructrual data。
- Glue也允許dynamic frame(支援dynamic type)。
- 可以用Glue trigger去觸發，也可以用job bookmarks(僅限S3)。每次job都會紀錄上次跑了哪些S3 key，下次跑就只會跑多出來的資料。
- 如果要interactive開發，可以起dev endpoint然後ssh進去就可以寫pyspark並且import awsglue的模組，但dev endpoint要錢所以東西測試完之後要記得自己手動刪掉endpoint
 
```
Q: KKLab使用EMR嗎？
A: 完全土炮用EC2自幹cluster，原因是價格考量。
```

```
Annie: EMR還是較自由。Glue都幫你包好好，不太了解裡面怎麼運作反而難以操控。 EMR都可以自由調整。

遇過glue的雷:選10個worker會報錯，選兩個就不會???
```

- EC2自幹最便宜，再來是EMR，再來是Glue。但是如果從開發時間跟成本的考量則是剛好相反，所以不同公司在不同階段根據資源會做出不同的選擇。

## Airflow使用心得

- 基於Python所以即使是分析師也能做到自己實作並且部屬job，然後管理job的介面還算直覺，所以不錯用。
- 如果有很多分析師的job會運用到airflow server本身的運算資源(先從雲端跑分散式SQL傳回資料後可能還要做特定複雜的後處理)，就可能讓server負荷不了，變得需要去管理job的時段。

## 下週預告

跨界，而且是個量化交易員，也是寫Code去分析資料。