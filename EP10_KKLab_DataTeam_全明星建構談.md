---
title: EP10 「KKLab DataTeam 全明星建構談」 
tags: 資料不科學幹話天地
credits: kyle, riz_hsu
---

# KKLab DataTeam 全明星建構談

* 資料不科學幹話天地 - 第十集
* 主持人 Kyle@Singapore
* 節目時間: 5/9 22:00

```本週內容簡介```

這次邀請到來自KKLab的資料工程師跟我們聊聊所謂的Data Team的構成，不同角色到底是怎麼分工？他們通常被期待要完成什麼任務？到底專業分工這件事情只是不是嘴巴講講，實際上人人都要十八般武藝樣樣精通？正好咱們來賓本身也是統計學系出身，幹過資料科學家，後來又轉戰資料工程，聽聽他怎麼看待資料業界實務上的分工情況吧！

```閒聊```
> * kk集團 -- kkbox kktv kkstream kklab
> * kklab: 30幾人小公司

```正題與背景故事```

## 來賓介紹

Manson@KKLab
Sr Data Engineer

## (主題內容)

kklab 資料團隊組成

- DS 
- DE
- frontend
- backend
- SRE
- PM
- BD
- Designer

backend的工作根據內容會分散到不同職位，可能是DE可能是backend engineer, SRE(cloud, CICD)。

專案導向，agile，工作主要由工程師自己認領。
最多同時一個人大概會接來自兩個專案的工作，兩個專案不會都是同樣的開發階段。
公司同時在跑的專案大概在五個以上。

DS主要負責poc，如果之後確定會上production則會和DE配合。
這部分DE的品質控管著重在穩定性跟可重複性，如果兩者都有達成則不太會花時間去追求code refactoring，因為時間有限。

KK有一些用R寫的feature在這塊是直接用dockerization image tagging的方式去做版控。

關於R的套件版本控管:嘗試過一些方案但都不盡如人意。
最近Rstudio推出renv可能有機會?但目前還沒聽說業界朋友在使用。

R vs Python

業界趨勢從poc轉移到build product，python在這一塊先天優勢所以慢慢變得更為主流。在新加坡感覺用R的DS比在台北還少。


```來賓提問: (問題簡述)```
> 記得R的問題是有些package是 GPL 2.0
> 不只是一些套件，R本身就是GPL，所以有商業使用上的一些限制。
> 如果是用在backend那問題不大。
> 另外許多強大的R套件本身其實多是apache 2.0。但因為R本身是 GPL所以...


> DE這邊有沒有使用特定的workflow軟體?
> 沒有。目前用一套自幹的。(KK很愛自幹?)
> 主要是能用，沒有複雜情境之下不需要非得用workflow軟體。之後如果需要應該會採用Argo，因為原生於k8s而東西都已經在k8s。
> 除此之外也算常用的另外兩套開源:airflow, azkaban(前者更知名)

```主持人提問: (問題簡述)```
ETL vs ELT

把寫ETL做資料前處理的工作從DE身上相當程度地解放，而是放給下游使用者自己去做處理。
業界並非所有DE都熟捻ETL的技能(比方說spark)，所以這樣的設計可以讓DE的job scope精實化，但對下游DS或DA的要求自然相對應地提高。

兩者沒有優劣，很可能一定程度可以並行，還是要看規模而定。

## (結尾)

grab來台徵才薪水比不上新加坡被噴?請大家諒解。
順便偷渡推廣[<致富的特權>](https://www.books.com.tw/products/0010887333)，是一個解釋台灣人才在國內薪水與物價沒問題但是跟國外比卻大輸的一個說法，供大家參考~
