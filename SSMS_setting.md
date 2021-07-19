# SSMS 設計資料表時顯示描述欄位
![](https://i.imgur.com/JyR2ENf.png)

## 第零步

### 不要啟動SSMS！！！

## 第一步

使用快捷鍵 win+R開啟執行視窗

![](https://i.imgur.com/mxKufg8.png)

## 第二步

輸入regedit 開啟登錄檔編輯程式

![](https://i.imgur.com/uvG7WWI.png)

## 第三步

找到SSMS的登錄檔 (我自己使用的版本是**18.6**)

**HKEY_CURRENT_USER > SOFTWARE > Microsoft > SQL Server Management Studi >    18.0_IsoShell > DataProject**


![](https://i.imgur.com/sRnvSUK.png)

## 第四步

找到 **SSVPropViewColumnsSQL70** 以及 **SSVPropViewColumnsSQL80**

將預設的數值 1,2,6 多加個17 

設定成1,17,2,6

在設計資料表時系統顯示如下圖

![](https://i.imgur.com/w8hQWvc.png)

### 完成後就可以開啟SSMS設計資料表

## 補充
各個代號所代表的意義

| Number | Means | 中文 |
|--------|--------|--------|
| 1  | Column Name | 欄位名稱 |
| 2  | Data Type | 資料型態 |
| 3  | Length | 長度 |
| 4  | Precision | 整數位數 |
| 5  | Scale | 小數位數 |
| 6  | Allow Nulls | 允許Null|
| 7  | Default Value | 預設值 |
| 8  | Identity |識別|
| 9  | Identity Seed |識別值種子|
| 10 | Identity Increment |識別值增量|
| 11 | Row GUID |  |
| 12 | Nullable | 可為Null |
| 13 | Condensed Type | 資料類型扼要 |
| 14 | Not for Replication | 不可複寫 |
| 15 | Formula | 公式 |
| 16 | Collation | 定序 |
| 17 | Description | 描述 |


8-10 **Identity系列** 常用於設定主Key自動增加id數值
![](https://i.imgur.com/5oPFwgX.png)

11 **Row GUID** 為全域性唯一識別符號 
資料型別為**uniqueidentifier**才可以設定

12 **Nullable** 僅為 6 **Allow Nulls**的結果顯示
