---
title: EP17 「在新創從零開始建立Data Team的奇幻（血淚？）之旅！」 
tags: 資料不科學幹話天地
credits: k9, riz
---

# 在新創從零開始建立Data Team的奇幻（血淚？）之旅！

* 資料不科學幹話天地 - 第十七集
* 主持人: Kyle 
* 節目時間: 8/22 22:00

```本週內容簡介```

> 最近由於工作非常忙碌，閒暇之餘比較沒有心思籌辦節目所以空了好幾周。覺得這樣下去不行所以還是要來聊點甚麼東西～這次是由我自己想來分享一下：
> 「在新創從零開始建立Data Team」的奇幻（血淚？）之旅！
>
> 可能會有點瑣碎但主要是跟大家分享一下這一路過程中曾經遭遇的難題跟各種趣聞。好奇的朋友記得上線準時收聽喔～

旅程摘要:

1. Blurred Job Scope: 職務範圍沒有明確定義，跟著整個公司的策略方向演進的同時，替自己找路出來
2. Changing Reporting Line: 老闆一換再換，最好認清自己才是自己的老闆
3. Multi-Hat Role: 老闆稱呼我是 "Data *(everything)"，除了資料系統架構的設計到實作，還要支援來自每日運營的任何資料分析需求
4. From One-Man Army to A TEAM: 人才招募，要面試同事，要面試新人，要面試學徒，甚至要面試自己未來的老闆
5. I'm Data Team -> We Are Data TEAM: 如何onboard你的同事，不論是比你資深還資遣的，甚至包括你的老闆

```主題```

# 在公司都在做什麼？

包含data stragies，就是擬定公司要怎麼處理資料與這些資料能為公司帶來多少價值？ 這時候公司甚至都還沒有產品就要想這種high level的概念。

有資料的時候，就會開始支援各種資料的insight與QA。還需要建立怎麼收這些資料的pipeline，就是需要design一個新的(modern)系統去大量收集這些資料。

還會自己build自己的BI tool，同時也自己consume那些資料並變成dashboard or some figures。

也幫忙寫了公司產品的code，用的是type script (type version的javascript)...

做了零零總總很多東西，會隨著公司的方針改變，目標也會跟著變...

# Changing reporting line

過去已經換了三個老版，新創會一直optimize新的方向，所以老闆會一直在換，但其實這一點都不重要；要注意到自己才是自己的老闆，大部分的老闆都不會是data field的expert，所以是我自己說話，這個team就是需要自己領導自己，沒有其他的監管...

# Multi-hat role

從hands-on到high-level strategic thinking/planning都要做，所以有時候會有context switching的挑戰，因為任務的性質差異很大。

舉例來說，下面幾種情境都是不同的context:

1. 替自己build的dashboard module寫unit test
2. 設計並實驗不同方向的data injection service
3. 用IaC實作一個設計好的系統架構並且部屬上線
4. 思考未上線的產品該如何設計資料收集的格式與方法，以及可能競爭者的做法
5. 設計面試題目
6. 面試與評分回饋
7. 與product manager開會定義產品資料分析方向

當許多不同context的事情同時發生在一個禮拜，處理上就會比較困難。

# From One-Man Army to A TEAM

時常從面試中學習，大部分的candidates都會有些獨特的想法與觀點是原本你自己不知道的知識。 但面試這個過程真的是很令人suffer，因為太多時間都被面試佔據。過程包含看履歷、想問題與寫Review。這讓我的productivity大幅下降，沒辦法做事。

我會面試三種level的人：包含下屬、同事與老闆。現階段想要找到我認可的老闆（同時也有意願想來）是有點難的，所以最後決定就不hire我老闆了... 目前就是自己做自己的老闆。

# 從downstream user (data scientist/analyst) 到upstream (data engineer)

這個過程學習到下面很有用的技術:

- Infrastructure-as-Code
- C4 Modeling for system diagram (with PlantUML)

是之前在downstream做開發的時候連想沒有想過的事情。

# 過程中遇到最有趣的挑戰

Changing Schema: 資料來源的格式始終不穩定，因為新創產品的快速演進使然，很難歸咎。要如何設計一個pipeline可以不受這種快速變動的影響，但同時又能讓downstream application以最少的改動跟上變化?

傳統上pipeline最理想的狀況是Stable schema，而新創產品性質的event-driven data product很多時候正好是光譜的另一邊:unstable schema。
