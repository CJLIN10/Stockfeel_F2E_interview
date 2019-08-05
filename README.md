# 股感前端面試上機測驗

## 題目

這份專案需要你將商品資料顯示成表格，並且實作排序、篩選等功能。
1. clone / fork 整個專案下來
2. 完成所有需求後，建一個`英文名字_日期_Stockfeel_F2EInterview`分支，並發一個 PR (e.g.,`LemonBear_20190514_Stockfeel_F2EInterview`)

### 先決條件
:pushpin: 
1. 請確保在 `Chrome` 上能夠執行
2. 可以使用任何 library 來取得資料及排版
3. 需使用 vue, react framework 或 Vanilla JS 來完成

### 功能需求
 :pushpin: 請依照你選擇的工具實作滿足以下條件：

1. 頁面載入時，請按照`報酬率高至低`排序。
2. 資料可用下拉式選單調整排序：選擇`報酬率`時，依據資料的`reward`屬性排序；選擇`收盤價`時，依據資料的`closePrice`屬性排序。
3. 選擇`高至低`時，依照當下所選屬性(報酬率/收盤價))的數值高至低排序，`低至高`則反之。
4. 當 `只顯示特選商品` 勾選時，只顯示 `specialStock` 屬性為 `true` 的商品。

### 資料來源
:pushpin:  需要的資料可以透過連至考試的網路從`http://192.168.0.19:7777/funds`中取得，取得後請將資料 render 成表格

商品資料格式如下：

```javascript
{
  "id": 5, // Id
  "name": "股感歡迎你基金", // 商品名稱
  "reward": 80, // 報酬率
  "closePrice": 88, // 收盤價
  "specialStock": true // 是否為特選商品
}
```

:pushpin: 圖檔於專案中的 images 資料夾

### 成果畫面
![result](https://i.imgur.com/8BR909x.gif)
