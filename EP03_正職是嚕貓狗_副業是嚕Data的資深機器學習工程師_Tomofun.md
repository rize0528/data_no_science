---
title: EP3「正職是嚕貓狗，副業是嚕Data的資深機器學習工程師@Tomofun」
tags: 資料不科學幹話天地
credits: riz_hsu
---
# EP3「正職是嚕貓狗，副業是嚕Data的資深機器學習工程師@Tomofun」
* 資料不科學幹話天地 - 第三集
* 資深機器學習工程師 Teebone
* 節目時間: 3/14 22:00

## 會前閒談

## 來賓介紹
* 大學-機械系，碩士是網研所。碩士比較偏分散計算的研究。
* 6~7年的經驗，4年在TM，2年在優必達(AI Engineer)，去年部門解散
* 現在是資深機器學習工程師在Tomofun

## Tomofun是一間什麼公司？
* 一個產品可以觀察寵物與自動餵食。
    * 主要客群是25~45歲的單身女性。
    * 可以用聲音跟寵物對話。
    * APP也有教學人如何教寵物與這台產品互動。
* 也有小型的產品，只有攝影機的部分。
## 這個產品的架構是什麼？
* 有Object detection，然後主要服務都在AWS
* 目前是開發影像與聲音的新模型。
## 資料怎麼取得?
* 第一版是open source dataset。
* 目前有收集客戶的資料，包含聲音與影像。
>      觀眾問: 什麼時候會觸發影像與聲音的上傳?
>      A: Event triggered，只要辨識為Postive會打包前後5秒的資料並上傳。
## 資料如何儲存
* 目前感覺資料儲存還是很亂...正在努力data分區分層好
* Traning data目前是放在公司workstation上

## MLOps?
* 做Machine learning的devops
    * ＡＩ軟體開發跟Opeartor有很巨大的隔閡
        * 傳統是AI model開發完就部署後就完事
        * Opeator不了解怎麼運作的
        * AI developer也不知道AI model的狀態如何
* 有什麼特別不一樣的地方嗎?
    * AI是要一個online的系統的話，就必須要做到MLOps
    * 跟傳統ML development process比較有三個3個anti-pattern
        * Development anti-pattern
            * 傳統需要一個super hero來維持這套ML product，對於一個backend eng來講還是一個黑盒子，沒辦法去修理模型，但對於super hero來說，他的工作重點是開發新的演算法
        * Deployment anti-pattern
            * 如何能replay你的model在過去的特定時間。
        * Operation anti-pattern
            * 有隨時tracking model的prec/recall嗎？ 一個模型deliver出來後，model的精確度會一直往下掉，要怎麼維持模型都表現一致？
## 目前正在做？
* Model 的 monitoring
    * 前陣子有發現alert爆大量，經調查發現是某種FP，是一種電子干擾聲，但是人耳無法辨識。 
* 現在是用什麼ML framework
    * 目前是用pytorch+docker image去deploy
* 現在的model的問題
    * 聲音: 8個model的I/O都不一致，但還是可以work(lol)
> 主持人問: 如果人學狗叫，model會表現的如何？
> A: 應該會辨識成FP吧...哈哈..

> 主持人: 如果你要找一個ML Eng到Tomofun，你會..?
> A: ML Eng的skill set須具備，有處理過大量資料經驗的人，但也不需要到high concurrence的程度。


