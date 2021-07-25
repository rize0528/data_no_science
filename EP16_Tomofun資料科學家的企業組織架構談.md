---
title: EP16 「Tomofun資料科學家:擔任AI與RD之間的橋樑」 
tags: 資料不科學幹話天地
credits: k9
---

# Tomofun資料科學家的企業組織架構談

* 資料不科學幹話天地 - 第十六集
* 主持人: Kyle，來賓: Ricky
* 節目時間: 7/25 22:00

```本週內容簡介```

- Trend Micro vs. Tomofun - enterprise vs start-up 組織文化差異 (沒錯又是一位ex-trender -> Tomofun XD)
- 新創組織文化、成員特質、AI/ML project開發
- Tagging之餘AI project的重要性
- 從Tomofun AI競賽看學校跟業界的Gap
- AIA(台灣人工智慧協會)演講經驗

```主題```

軟體公司文化差異: 大公司 vs 新創小公司

大公司公司多部門多，其實各自有各自的文化、使用工具、甚至組織結構。
新創小公司可能只有少數甚至一個產品，所以更加專注而有整體性。

- Tomofun產品功能
    * 狗圖像辨識
    * 狗聲音辨識
    * 自動剪輯一日回顧
    * 狗動作分類、行為描述(吃東西、小便)

- Team Strcuture
RD兩個scrum(new/old feature)，各自有完整的分工(FE +BE + QA + PM +...)

- RD Team vs AI Team?

AI team不在scrum裡。
AT team成員特質: Deep Learning領域專門的研究者，知道sota，追最新的research paper並分享
其中甚至有少數人是只追求DL知識，不太在意產品落地的。但這樣的專業分工想必也讓RD team能夠更專注在infra的建構。

對於RD來說AI feature就是service endpint而已，因此AI team裡也有在負責model optimization來達到更好的成本效益。

- BE <> AI

當然也有人擔任這樣的工作(詳見@teebon過去的分享)，能夠溝通AI team和RD關於技術需求的整合。

- 擔任AI <> PM的橋樑，最大的挑戰?

產品需求與技術可行性之間的落差。如何溝通什麼樣的需求在什麼樣的資源限制下是可行或多可行。

- Tomofun AI競賽 (與AWS和T-Train合作)
    - 初賽類似Kaggle，決賽是現場架API實測(每兩秒一筆request)
    - CS出身的學生對一些學理之外的軟體工程基礎知識相對缺乏(出現很多已知用火的情況，需要提供大量教育訓練來輔助比賽能順利進行)
    - 

- Tagging之餘AI project的重要性與挑戰
    - 有些Tag本身即使是人工也不容易辨識(比方純聲音的分類)
    - Guideline不同人詮釋不同，導致tagging inconsistency可能影響模型效果

- Tooling
    - https://labelstud.io/ 好用
    - 各大雲端服務商也有labeling service，但似乎labelstudio還是好用，不過對於task management這塊尚未深入評估

- AIA(台灣人工智慧協會)演講經驗
    - 科技生態發展基金會(中研院色彩)，專案形式委託台灣人工智慧科技基金會(前身為資料科學年會)
    - 現為台灣人工智慧學校基金會，拉回科技生態發展基金會
    - 初期學生比較積極
    - 後期感覺比較被動，可能是因為方向改為企業教育訓練為主要學生來源，這又或許跟台灣沒有足夠的市場支撐這類人才的供給有關?
