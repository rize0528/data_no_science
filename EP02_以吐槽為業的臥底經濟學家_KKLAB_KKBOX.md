---
title: EP2 以吐槽為業的臥底經濟學家@KKLAB/KKBOX
tags: 資料不科學幹話天地
credits: Teebone_Ding, Riz_Hsu
---



# 以吐槽為業的臥底經濟學家@KKLAB/KKBOX
* 節目時間: 3/7 22:00

```問：簡介一下KKBox```
spotify for artist 可以給音樂人的資料，例如撥放量/demographic data

KKFarm 會賣資料產品給別人，目前對口是會對音樂人，但目前音樂人不知道每首歌被播幾次之類的細部資料。
KK提供數字/人頭等訊息以及更複雜的訊息給製作人理解歌曲多成功/失敗

```問：如何給音樂人資料? ```
KKBOX->KKFARM-> interactive dashboard 有前端提供給客戶
KKLAB以API形式提供給KKFARM
KKFRAM有自製的前端軟體

利用3天的撥放量來預測未來60天的撥放量
也可以觀察其他相似撥放量的歌曲上有什麼特殊之處

K-POP 台灣聽眾很狂，會狂Repeat刷單
但也有聽眾很廣但是不愛repeat的歌曲
20%-30%客戶只播 kkbox 排行榜
排行榜的撥放量滿大，但是排行榜去聽歌的人本身未必是粉絲，KK可以找到核心粉絲做分析

```問：3天是什麼 magic number?```
LifeCycle的survey 撥放量 3 7 14 30天 一首歌上架的撥放量趨勢
新歌榜:上架30天內
drop by 30天因為會30天後會退出新歌榜
所以 3 7 14 30 是數字一路減半減半算出來的

```問：有沒有衡量資料帶給客戶的價值?```
目前沒有特別衡量，總之提供給客戶讓他們看看哪些資料有用

```問：產品做了什麼事情(?) (忘記問題是什麼了)```
針對音樂客戶，發行之前先把音樂檔案過model，預測出來一個分數，來決定主打歌要放哪一首，哪首歌先拍MV。
model input: audio file 副歌30s -> 轉圖片(FFT) -> CNN -> 預測重複撥放有關的數字：用戶量/重複聆聽量等數字創造的數學式

也有 CNN + GRU 這種作法處裡音訊
A段B段 k-pop很明顯，所以有時間序列的概念的模型(ex. GRU)可以清空之前的段落記憶

```問：主流音樂有哪幾種?```
華語嘻哈現在是主流 中國有嘻哈 中國新說唱 熱狗 張震嶽 等在這幾年帶動了一個新的風潮，是過去五年以前沒有的新市場。

```問：不同類型的歌，群眾有沒有不同的行為?```
核心粉絲行為差異很大
地區分布 911在中南部很夯 (這邊有一點斷訊，如有人有聽到可補充)
台北地區台語歌 -10%
台北人都在聽外語歌XDDDD
外語歌在台北以外是負的 (這是互相傷害嗎?)
原住民歌手在花東撥放量是3 4 倍
雷鬼跟原住民粉絲的重疊很大

```問：在KKBOX待了很久，為什麼?```
前兩年意興闌珊，做很多一次性的工作
這三四年做預測模型，大老闆腦動大開
好像這麼模型做出了成果，製作人也覺得可以拿來用
原本音樂人拿到的數據非常少，但像是運動類的籃球跟棒球可以拿到的資訊很多

```問：商業創作vs獨立創作的客戶? ```
(這段忘記回答了什麼)

```問：台灣的製作人拿的到 spotify 的資料做分析嗎? 如果可以的話那KK的資料跟 spotify 之間有什麼競爭上的差異性?```
Spotify 的資料沒有KK多
aggregator 可能可以跟 spotify要到一些細部的資料，可以細到以天為單位之類
但是KK這邊可以找到核心受眾以及未來成長的趨勢分析
ex.楊丞琳出了一首新歌，但原本的TA不買單 


```問：需要對音樂有熱情嗎? 還是只要有基本的domain knoledge?```
應該是不需要熱情XDDD
有同事做了蔡依林的粉絲跟誰重疊的分析 發現都是不熟的歌手
資料科學家其實也不需要對音樂很有熱情
KK偶爾會有突發歌手來唱個兩首歌 
曾來過的嘉賓：**三上悠亞**、田馥甄、瑤瑤


```問：KKLab跟KKBOX之間的分家?```
ML團隊與BE團隊
發現某些部門可以serve集團內不同公司或者serve外面的公司
音樂編輯 對於其他公司可能用處不大，但ML也許可以
目前有revenue可能還沒有profit
但有BD去開發跟音樂無關的客戶
音樂分析這個案子在KKLAB分家之前就在合作

```問：公司的tech stack```
語言上常用 R (預測模型與視覺化分析)與python
包docker + jenkins 來執行程式 (?)
deep learning用pytorch，例如給音檔預測分數的model
Gradient Boost 用R取得可解釋性
Deep learning就都還是用python，其他習慣用R

in-house可解釋性 (這邊也許可以請主講人再多解釋一些?)
tree base model 做分支的時候，看分支左右的權重相減，賦予給分支的node的feature
了解為什麼原因做分支，最後加總起來這個feature
不用SHAP? 
因為通常feature會一個勾一個，不是獨立的feature