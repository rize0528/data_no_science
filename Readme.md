# 我在哪？ 我是誰？

這個Repo是存放『資料不科學幹話天地』的文字紀錄儲存點，主要是利用hackmd的github同步功能來進行自動更新。

# 製作共筆

節目進行都會有來賓分享他們的許多經驗與想法，有時候錯過真的很可惜，所以每次節目開始前建議安排幾個人預先建立共同筆記，
讓熱血的聽眾們可以共同紀錄並事後可以翻閱。

## 如何新增一條筆記

首先打開[HackMD](https://hackmd.io/)並點選『協作筆記』，如果你是新增開啟筆記的人，請點選『建立筆記』

![](/res/imgs/hackmd_01.jpg)

筆記建立完畢後，請點選『分享』![](/res/imgs/hackmd_share.jpg)，並複製共享連結並貼至頻道，讓更多人可以同時編輯。

![](/res/imgs/hackmd_02.jpg)

## 如何連結Github

### Github權限
HackMD本身提供了Github同步的功能，所以在開啟或是同步Github之前，  
請跟Repo原owner(頻道內密Riz)或是主持人(名字為紅色的)申請加入github collaborator
Repo位置(https://github.com/rize0528/data_no_science)

### Hackmd連結到Github
連結到Github有兩種方法，第一種是新增筆記時會在編輯器的下方出現『推送至 Github』

![](/res/imgs/hackmd_03.jpg)

點開後會出現下面的對話窗，請填寫
1. 選擇Repo (rize0528/data_no_science)
   * 如果無法看到，就表示你還沒有Repo的權限，請回上一步確認你擁有編輯的權限
2. 選擇要同步的檔案
   * 請照著格式 "EP?_本次節目題目_講者或講者的公司名稱.md"
3. 簡單輸入一些commit描述後就點選推送

![](/res/imgs/hackmd_04.jpg)

## 筆記的格式

筆記沒有特別的格式需要follow，不過HackMD有所謂的標籤功能，為了整理方便所以希望在文章頭加入以下標籤
```
---
title: EP4 「四處打工的斜槓資料科學家@Trend Micro」 
tags: 資料不科學幹話天地
credits: riz_hsu
---
```

* title: 節目名稱，可以從Discord的節目表複製貼上
* tags: 本節目一率為 『資料不科學幹話天地』
* credits: 筆記貢獻者，請附上你的名字並用半形逗號(,)連接

最後，文章編輯就以編輯者喜歡個格式進行編輯，但還是建議使用Markdown style的編輯方法以利其他人觀看。