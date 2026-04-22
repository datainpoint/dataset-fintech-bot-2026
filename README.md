# dataset-fintech-bot-2026 臺灣銀行委辦 AI 人才進階訓練

Dataset: Fintech BOT 2026.

## 題目說明

1. Bank customer value estimation 銀行客戶價值估計模型。

假設你在一間銀行的數位金融部門任職，你主要管理的產品是數位錢包，你的任務是透過數位錢包的營運資料來建立一個「客戶價值估計模型」，主要用於預測數位錢包使用者的終身價值，數位金融部門需要識別哪些客戶具有高的長期貢獻度，以便更精準地分配行銷資源在這些高價值客戶身上。請根據「資料科學管線」的框架以及「專題評分標準」撰寫一份 Jupyter Notebook 完成這個任務。

2. Bank customer churn prediction 銀行客戶流失預測模型。

假設你在一間銀行的客戶關係管理部門任職，你的任務是透過一份客戶行為特徵資料，建立一個「流失預測模型」，預測每個客戶的流失機率，並且提前識別出「有流失傾向」的客戶，就能透過優惠或服務來挽留他們，在競爭激烈的銀行業中，獲取新客戶的成本遠高於維護舊客戶。請根據「資料科學管線」的框架以及「專題評分標準」撰寫一份 Jupyter Notebook 完成這個任務。

3. Loss given default, LGD prediction 銀行房貸授信違約預測模型。

假設你在一間銀行的風險管理部門任職，你的任務是希望借鏡美國知名金融科技公司 LendingClub 的貸款資料，建立一個「違約損失率模型」，預測每筆貸款在違約後的損失比例，銀行的風險管理愈精準，就能更有效地分配風險準備金，降低營運成本。請根據「資料科學管線」的框架以及「專題評分標準」撰寫一份 Jupyter Notebook 完成這個任務。

4. Bank product recommendation 銀行產品推薦模型。

假設你在一間西班牙銀行 Santander Bank 的資料科學團隊工作，你的任務是透過客戶每月行為資料（從 2015 年 1 月至 2016 年 5 月，長達 1.5 年），建立一個「產品推薦模型」，藉此提升客戶滿意度與銀行的交叉銷售效率，請根據「資料科學管線」的框架以及「專題評分標準」撰寫一份 Jupyter Notebook 完成這個任務。

5. Web traffic/Store sales time series prediction 流量/銷量時間序列預測模型。

假設你在一間銀行的分行管理部門任職，你的任務是希望借鏡零售商店的每日銷售資料，建立一個「時間序列預測模型」，目的在於考慮顯著的季節、節慶與工作日的特性，協助銀行優化分行人力資源管理，在避免人力不足與提高人力運用效率之間取得平衡，請根據「資料科學管線」的框架以及「專題評分標準」撰寫一份 Jupyter Notebook 完成這個任務。

## 專題評分標準

- 資料工程（10%）：學員是否能妥善整合結構化與非結構化資料？資料載入、清理與轉置的環節是否妥善處理？面對資料中可能存在的缺失值或雜訊，處理邏輯是否合理？
- 專題組織性、可重現性（10%）：Jupyter Notebook 中的程式碼是否有整理為函數、類別或模組的型態？重現這個專題的前置作業或步驟是否簡單便捷？
- 溝通（20%）：學員是否能用 3 到 5 分鐘的時間讓聽眾知道專題的重點與亮點？圖表是否幫助聽眾理解？
- 模型與機器學習（30%）：學員是否妥善運用了統計分析、演算法、資料探勘或機器學習等方法論？是否確實生成指定的輸出格式？是否有運用恰當地評估指標佐證模型的表現？
- 應用性配適評估（30%）：學員是否從題目、資料集與實作中提出與行內業務相關的可能延伸應用？該延伸應用提案是否合乎行內業務發展趨勢？是否合乎內部規範與外部監管？

## 實作資料集概述

1. FinTech Customer Life Time Value (LTV) Dataset

- 來源：<https://www.kaggle.com/datasets/harunrai/fintech-customer-life-time-value-ltv-dataset>
- 檔名：digital_wallet_ltv_dataset.csv
- 資料集特性 ：多變量、序列型
- 領域：商業、金融科技
- 相關任務：迴歸、分群
- 特徵類型：實數、整數、類別
- 樣本數：7,000
- 特徵數：20
    - Customer ID: 用戶唯一識別碼
    - Age / Gender / Location: 用戶的基礎背景資料
    - Account Level: 用戶帳戶類型或等級
    - Total Transactions: 總交易次數
    - Recency: 最近一次交易距今的天數
    - Frequency: 交易發生的頻率
    - Monetary Value: 歷史平均或總交易金額
    - App Usage Pattern: 應用程式登入頻率、停留時間
    - Engagement Metrics: 用戶點擊率或特定功能的參與深度
    - Last Interaction: 最後一次與平台互動的時間
    - Support Interactions: 用戶聯繫客服的次數
    - Churn Indicator: 用戶流失風險或不活躍指標
    - 目標變數：`LTV`
- 概述：資料集擷取了用戶的人口統計特徵、交易歷史、參與度指標以及應用程式的使用模式，協助金融科技公司預測數位錢包用戶的客戶終身價值 (LTV)準確預測 LTV 能讓企業識別高價值客戶、優化行銷預算分配並降低客戶獲取成本。

2. Banking Customer Churn Prediction Dataset

- 來源：<https://www.kaggle.com/datasets/saurabhbadole/bank-customer-churn-prediction-dataset>
- 檔名：Churn_Modelling.csv
- 資料集特性：多變量
- 領域：商業、金融
- 相關任務：分類
- 特徵類型：實數、整數、類別
- 樣本數：10,000
- 特徵數：14
    - RowNumber: 資料列編號
    - CustomerId: 客戶唯一識別碼（ID）
    - Surname: 客戶姓氏
    - Geography: 居住地（如 France, Spain, Germany）
    - Gender: 性別
    - Age: 年齡
    - CreditScore: 信用分數
    - Tenure: 客戶年資（已加入該銀行的年份）
    - Balance: 帳戶餘額
    - NumOfProducts: 使用該銀行的產品數量
    - HasCrCard: 是否持有信用卡 (0: 否，1: 是)
    - IsActiveMember: 是否為活躍會員 (0: 否，1: 是)
    - EstimatedSalary: 預估年收入
    - 目標變數：`Exited`
- 概述：資料集包含客戶的人口統計資訊、銀行帳戶信用狀況以及在銀行的活動狀態，協助預測銀行客戶是否會主動停止使用該銀行的服務（流失）。對於銀行業而言，識別潛在流失客戶對於制定留存策略至關重要。

3. All Lending Club loan data

- 來源：<https://www.kaggle.com/datasets/wordsforthewise/lending-club>
- 檔名：accepted_2007_to_2018Q4.csv
- 資料集特型：多變量、時間序列
- 領域：商業、金融
- 相關任務：分類、迴歸
- 特徵類型：實數、整數、類別
- 樣本數：2,260,701
- 特徵數：151（151 個特徵中有許多重複或高缺失率的欄位，在此僅列出可能會用到、重要的特徵。）
    - emp_title / emp_length: 職稱與就業年資
    - home_ownership: 住房狀態 (RENT, OWN, MORTGAGE)
    - annual_inc: 借款人年收入
    - verification_status: 收入是否經過平台驗證
    - dti: 債務收入比
    - earliest_cr_line: 最早信用額度開立日期
    - loan_amnt / funded_amnt: 申請金額與實際撥款金額
    - term: 貸款期限 (36 或 60 個月)
    - int_rate: 貸款利率
    - grade / sub_grade: 由 LendingClub 評定的信用等級（A 至 G）
    - purpose: 貸款用途（如債務整合、信用卡還款）
    - loan_status: 貸款狀態 (Fully Paid, Charged Off, Default, Late...)
    - total_pymnt: 至今收到的總還款金額
    - recoveries: 違約後回收的金額（LGD 建模的關鍵目標）
    - last_pymnt_d: 最後一次還款日期
    - 目標變數：衍生計算欄位 `funded_amnt - recoveries`
- 概述：資料集包含 LendingClub 平台從 2007 年創立至 2018 年第四季的所有貸款申請紀錄。紀錄了每筆貸款從申請、審核、撥款到最終還款或違約的完整生命週期。

4. Bank product recommendation

- 來源：<https://www.kaggle.com/competitions/santander-product-recommendation>
- 檔名：
    - santander_sample_submission.csv
    - santander_test_ver2.csv
    - santander_train_ver2.csv
- 資料集特性：多元分類、時間序列、推薦系統
- 領域：商業、金融
- 相關任務：分類
- 特徵類型：實數、整數、類別
- 樣本數：13,647,309
- 特徵數：48
    - fecha_dato: 統計日期 (Time-Series key)
    - ncodpers: 客戶唯一代碼
    - ind_empleado: 僱傭指標 (A: 活躍, B: 前員工, F: 退休, N: 非員工, P: 實習生)
    - pais_residencia: 居住國家
    - sexo: 性別
    - age: 年齡
    - fecha_alta: 加入銀行的日期
    - ind_nuevo: 新客戶指標 (最近 6 個月內加入)
    - antiguedad: 銀行資歷 (月)
    - indrel: 客戶關係等級 (1: 主要, 99: 初級)
    - indrel_1mes: 月初客戶類型 (1-4)
    - tiprel_1mes: 月初關係指標 (A: 活躍, I: 不活躍, P: 潛在, R: 註冊)
    - indresi: 居住地指標 (S: 與銀行同國, N: 異地)
    - indext: 外籍指標 (S: 是, N: 否)
    - conyuemp: 配偶員工指標 (S: 是, N: 否)
    - canal_entrada: 客戶加入渠道
    - indfall: 死亡指標 (S: 是, N: 否)
    - 目標變數：24 個產品目標變數，均為二元變數 (0: 未持有，1: 持有)。包含儲蓄帳戶、信用卡、抵押貸款、養老金等 24 種產品。
- 概述：資料集包含 Santander 銀行 1.5 年的客戶行為紀錄。目標是根據客戶過去的持有紀錄與人口統計學特徵，預測客戶在 2016 年 6 月會新增哪些金融產品。

5. Store Item Demand Forecasting Challenge

- 來源：<https://www.kaggle.com/competitions/santander-product-recommendation>
- 檔名：
    - store_sample_submission.csv
    - store_test.csv
    - store_train.csv
- 資料集特性：單變量、時間序列、多序列
- 相關任務：回歸、預測
- 領域：商業、零售
- 特徵類型：日期、類別、整數
- 樣本數：913,000
- 特徵數：4
    - date: 交易日期（YYYY-MM-DD）
    - store: 商店識別碼（整數 1-10）
    - item: 商品識別碼（整數 1-50）
    - 目標變數：`sales`
- 概述：資料集包含零售商在 5 年期間（2013-01-01 至 2017-12-31），分布於不同地點的 10 間分店中 50 種特定商品的每日銷售數據。目標是預測未來三個月（2018 年 1 月至 3 月）內每種商品在每間商店的每日銷量。

## 附錄一：資料集下載

請參考 [Google 雲端硬碟](https://drive.google.com/drive/folders/1TDTJFM0lPxfpD_usCEoSutyDyy3V9428?usp=drive_link)

## 附錄二：資料集檢視

請參考 [dataset_describe.ipynb](dataset_describe.ipynb)