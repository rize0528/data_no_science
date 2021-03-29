---
title: EP4 「四處打工的斜槓資料科學家@Trend Micro」 
tags: 資料不科學幹話天地
credits: riz_hsu
---

# 「四處打工的斜槓資料科學家@Trend Micro」 

## ```Q: 請簡單的自我介紹```
* 大家好，我是Riz，是趨勢的技術經理，目前在趨勢已經工作了7年半，趨勢算是我第一份工作。
* 來趨勢之前是在中央讀博士班，那時候已經接觸了ML，實驗室主要做的內容是電腦視覺與訊號處理；在那個時代所謂ML就是比誰的特徵處理、特徵抽取演算法好，所以對於模型的調整與評比是較少研究者在做的。
    * 博士班有發一些論文
        * 像是利用MLP去點英國車站的人流。
        * 或是使用curvelet的feature space去對三軸加速計的訊號做手勢辨識。
        * 與惡劣天氣的車流量計算等
* 在趨勢的主要工作內容是負責提供各方面的ML solution的初期版本與嘗試，比較像是個踩雷者(笑)

## ```Q: 大概介紹一下TrendMicro是間什麼公司```
* 趨勢算是跟我滿有緣的，我國小的第一台電腦是我表哥幫我拼的，那時候就跟他學程式語言。而我表哥的第一份工作就是在趨勢，所以還有印象去過對面的319號大樓參觀過。
* 眾所皆知，趨勢科技是防毒軟體公司。不過大約在10年前就開始轉型成雲資安公司，而現在與未來主要的營收目標都是擺在功能訂閱制的企業資安防護。


## ```Q: 為何在TM待這麼久```
* 主要是從進公司到現在，基本上都一直維持著有新的專案可以試新技術的機會。 所以就不知不覺...
* 再來這個team之前，大約每半年開一個新project

## ```Q: 目前產品的資料量```
* 目前所在的團隊是負責生產公司新世代Saas的資安防護引擎，手上有的各Region企業級客戶總共約有3000位，
* 每天要處理的資料量也是很多，以北美來說，大概一天有11M個資料包要處理。
    * ```之前是透過Flink去做ETL，現在則是用Lambda```
* 在AWS花的錢也是很多，每個月大概要花500K USD (最多還是存資料S3 (35%))
* 一些名詞
    * Apex One
    * C1WS(Cloud One Workload Security)
    * DSM (Deep Security Manager)
    * DSA (Deep Securit Agent)

## ```Q: 什麼是到處打工 | Q: 你在趨勢做了哪些事情```
* 之前所在部門的關係，會需要到處支援machine learning solution
    * 剛來沒多久就被叫去考白帽駭客執照，之後做了一個distance base的 sandbox log clustering的計畫，做出來的結果要可以直接變成類似一條病毒碼的那種概念。 所以那時候都不在位置上，都在我們的virus lab tune model XD
    * 這個計畫結束沒多久，就與Consumer team合作，製作TMIS或是diamond box裡面的network anomaly。
    * 這時候又有另外一個車用異常檢測的計畫，去對車上的CANBus log去做finger printing與異常檢測，不過這個計畫的資料量異常的少，所以在現場調教成super ovfitting的model也毫不意外XDD
    * 之後跑去跟APT合作，去做病毒資訊IoC上文字tag的計畫。 除了上tag的model外，也自己刻了aws infra...
    * 同時也做了一個W-C CNN去檢測URL是不是很像釣魚。
    * 現在則跑到這個team做DS

## ```Q: 不同部門對於ML的接受程度?```
* 趨勢科技以我的觀點其實可以切分成三大塊
    1. 零售客戶端
    2. 核心技術（threat knowledge）
    3. 企業產品端
    
* 而對於ML的期待則是越往企業端就越要求精準，因此通常都要求high precision，但近年由於有了Mitre考試的關係，所以漸漸對於high recall又開始重視了。
* Mitre (是MS列舉了並歸類的各式各樣的網路攻擊，可以較有效的標籤化或量化一個攻擊行為)
* 目前合作過的團隊，Consumer團隊對於ML的接受度最高，可能對他們來說是一個nice to have的一個銷售賣點，所以他們並不會太過問你的模型選擇與特徵的選取原因。 不過對於recall也是相當的要求，而他們的解決做法是直接在workflow中解決這個問題，意即去加入allowence or denied list （政治正確說法）。 他們會比較偏向用修正的方式去完善一個solution。 像是之前就有把主持人的大作ZeroOne Engine包裝一下賣給Consumer team XD。 似乎也還運行的滿可以。
* 另外一個例子是去德國跟BMW的一個合作廠商一起研發Canbus log的異常偵測，我與上週的Tomofun講者一起開發了一套基於有限資料的anomaly detection model，裡面包含了(DP, LSTM, VAE等等的模型)，計畫做完後他們還是持續派人去tune參數。

* 再來是核心技術團隊，這個團隊則是想盡辦法爭取對外的曝光，過去幾年對於一些新創的題目都有辦法接受，像是Social media的Spammer detection，又或是Threat intelligence的enhencement使用NLP去做。 不過，一但爭取到了機會，醜媳婦究竟是要見公婆，還是要面對產品端的嚴格要求，所以常常會在這一步卡住。

* 而企業產品端則更是嚴格，對於你的模型不單要求FP很低，也必須考量inference turn around time，model size等等。

* 最後談到是我現在的團隊，實際上一開始是花了很多功夫去recurit公司內部DS有志人士，不過去整個去年因為沒有DS infra的support，所以我們就只能一直出pyspark script去幫忙enrich detection的coverage
* 今年則開始有點不同，可能是遇到solution面的要求，所以除了最近在弄了Incident view(data point aggregation)，也在弄一些基於NLP的reasoning model
* 接下來也計畫要做Account anomaly與特定的asset tagging

## ```Q: 什麼是斜槓```
* 因為個人興趣的關係，算是一個Maker，舉凡
    * 3D design
    * 3D printing
    * 3D printer design
    * CNC操作, CAD設計,CAM操作等物理層面的
    * 前陣子在跟開放咖啡同好社群的人開發了咖啡豆烘焙度檢測機
        * 就有把多種lite weight or shallow learning model放到Wemo上，利用借來的數萬元專業檢測機與自己拼(3d列印與機電)的總價400元的檢測機去做pair sampling。
        * 可以做到與專業烘焙計+-誤差5的模型(最大值是180)
* 而在TM也做了很多與傳統DS不太一樣的Tech track
    * 車用異常檢測(CANBus)
    * 自走車設計(2018)
    * Frontend development得到HIE award (XD)
    * 近幾年公司的獎盃設計