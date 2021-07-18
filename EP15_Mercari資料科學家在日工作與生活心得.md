---
title: EP15 「Mercari機器學習工程師在日工作與生活心得」 
tags: 資料不科學幹話天地
credits: riz_hsu
---

# Mercari機器學習工程師在日工作與生活心得

* 資料不科學幹話天地 - 第十五集
* 主持人: Kyle，來賓: Toby
* 節目時間: 7/18 22:00

```本週內容簡介```
> Mercari是日本二手拍賣平台的龍頭，在日本新創界也享有盛名。
> - 當初怎麼會去日本？對想去日本工作的台灣工程師有什麼過來人的建議？
> - Mercari的組織文化是什麼樣的風貌？
> - 做過哪些有趣的資料科學應用項目(自然語言處理、情緒分析與客訴)跟二手電商獨有的挑戰？
> - Pretrain-then-finetune 在日語遇到的問題
> - ~~AI 裡的性別議題~~ (沒時間聊到)

```閒聊時間```

Toby是目前在東京的Mercari的機械學習工程師，研究所在台灣清大，且專攻NLP情緒分析的研究；Mercari是日本最大的二手拍賣平台，也被戲稱為「老創」，IPO之後因為疫情的關係，第一年財報很好且也有盈餘，在美國也有開創Mercari US。同時也想要嘗試做虛擬貨幣的交易所的計畫。

Mercari的主要目標是想要做二次物流。與一次物流（店面、網購）不同的地方，可以理解為所有的二手交易都想要分一杯羹。

```節目內容```

目前主要在做CRE(Customer Reliability Engineer)中的Text moderator，主要審查使用者在交易平台上的不正發言，並交由後端做評斷。也有做Annotation，另外也會偵測使用者衝突（下標之後的In-APP chat），並主動通知客服。

> Q: 可是如果是要預測糾紛，不就等於糾紛還沒發生？
> A: 日文有一些特性，一個例子就是在糾紛開始之前，吵架方會開始提升敬語等級。又或是利用一些POS來偵測命令型。

> Q: 你的日文很好嗎？
> A: 爛透了，在get offer之時連50音都記不得。

> Q: 為何不用Transformer?
> A: 試過在日語表現很差，有可能是wiki的日語資源不足又或是日本語tokenizer不太行。但像是在美國的部門就是用bert了。

> Q: tokenizer的部分也是用傳統rule-based的tokenizer，效果意外的好。有嘗試過像是google sentencepiece這種tokenizer嗎?(而且是日本人寫出來的)
> A: 目前還是傳統的mecab效果較好

> Q: PII Masking (Pw, Credit card, trade serial, user name)
> A: 主要還是打算用Rule based & NER來做，但還是需要一個benchmark model。 `Google也有做一套(data prevention)`

> Q: 請問DS的編制？
> A: 滿全能的，會需要需求做backend，也會被要求日語能力。AI team大概目前有40個人左右。

> Q: 對於未知的日本字，要怎麼應對？
> A: 會對這些字拆成character level RNN再讓down stream去做分析(Convolution)。

## Mercari的一些projects

* AI team也有做一些有趣的feature，像是做賣產品時的建議價格與一段時候的預測價格。 Mercari US site也有利用物品照片來預測實際運費。

> Q: Mercari的annotator的團隊大嗎（有嗎？）？
> A: 實際真的有一個labeling的團隊在做這件事情。

> Q: 請問Mercari是一個值得推薦的公司嗎？
> A: 如果只是想來日本，可以選Mercari。但談到要不要來日本，就可以再想想(有稅金等等的問題...)。Mercari還鼓勵工程師擁有自己的新創副業，只要不要用同一台NB辦公就好XD

> Q: 請問怎麼會想到日本工作？
> A: 應屆就直接出來嘗試。 然後Mercari直接調了一個很棒的薪水。然後支助研討會、酒店等等的。

> Q: 未來的規劃？
> A: 目前拿到日本Apple的offer，工作內容是做Siri台灣語調教。

關於Mercari的tech stack:

- GCP
- k8s & KubeFlow
- Infra team很強，有很多幫助deploy的工具(像是使用Terraform，生成template, 完整的end2end ML model deployment....)
- 在做ML的都是掛software engineer，在BI有掛DS的會要求有更好的日文水平 (這部分跟Line就很類似)
 