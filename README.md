---
header-includes:
  - \usepackage{fontspec}
  - \setmainfont{Heiti SC}  # Or another CJK-supporting font installed on your system
  - \usepackage{xeCJK}
  - \setCJKmainfont{Heiti SC}
  - \XeTeXlinebreaklocale "zh"   # Set line breaks for Chinese
  - \XeTeXlinebreakskip = 3pt plus 1pt
  - \usepackage{geometry}
  - \geometry{top=1in, inner=1in, outer=1in, bottom=1in, headheight=3ex, headsep=2ex}
---

# 臺灣銀行委辦 AI 人才進階訓練期末專題

郭耀仁 <yaojenkuo@ntu.edu.tw>

## 專題實作項目

1. 上傳副檔名為 .ipynb 的 Jupyter Notebook，學員可以在 Google Colab 完成之後，點選 File > Download > Download .ipynb（由課程講師評分，佔分 75%）
2. 上傳副檔名為 .pptx 的 Power Point 簡報，採用台灣銀行模板。
3. 使用 2. 的簡報檔案進行 10 分鐘的簡報（由聆聽主管評分，佔分 25%）。

## 評分標準

- 課程講師評分
    - 預期產出（10%）：學員是否有依題目需求達成預期產出？
    - 專題組織性（15%）：學員是否能用精練的文字讓讀者快速理解專題的重點與亮點？圖表是否幫助讀者理解？學員是否從題目、資料集與實作中提出與業務有關的可能延伸應用？
    - 資料工程（20%）：Jupyter Notebook 中的程式碼是否有整理為函數、類別或模組的型態？重現這個專題的前置作業或步驟是否簡單便捷？學員是否能妥善整合結構化與非結構化資料？是否妥善運用資料載入、清理與轉置的技巧？面對資料中可能存在的缺失值或雜訊，處理邏輯是否合理？
    - 機器學習（30%）：學員是否妥善運用了機器學習的知識？是否有運用機器學習技巧處理多觀測值、多特徵、類別不平衡或交叉驗證等難題？是否有運用恰當的評估指標？
- 聆聽主管評分
    - 簡報表達（25%）：學員台風是否穩健？能否在規定時間內（10 分鐘）清楚表達專題的挑戰、洞察與發想等內容？有沒有讓聽眾耳目一新的潛力？是否有提出與業務有關、可行的創新想法？

\newpage

## 資料集授權聲明

- GENERAL COMPETITION RULES
    - COMPETITION DATA. "Competition Data" means the data or datasets available from the Competition Website for the purpose of use in the Competition, including any prototype or executable code provided on the Competition Website.
        - Data Access and Use. Unless otherwise restricted under the Competition Specific Rules above, after your acceptance of these Rules, you may access and use the Competition Data for the purposes of the Competition, participation on Kaggle Website forums, academic research and education, and other non-commercial purposes.
- CODE SHARING
    - Participants are permitted to publicly share source or executable code developed in connection with or based upon the Data, or otherwise relevant to the Competition, provided that such sharing does not violate the intellectual property rights of any third party. By so sharing, the sharing Participant is thereby deemed to have licensed the shared code under the MIT License (an open source software license commonly described at ).

Source: [Competition Rules](https://www.kaggle.com/competitions)

\newpage

## 題目與資料集

1. Santander Customer Satisfaction

你是任職於 Santander Bank 的資料科學家，請在規定時間內完成資料清洗並建立一個預測效能優於隨機猜測的基礎模型。

- 需求：
    - 找出並刪除資料集中所有「常數特徵」（所有值都一樣的欄位）以及「重複特徵」（欄位內容完全相同的特徵）。
    - 請試著處理類別不平衡（4% vs. 96%）的樣本比例問題。
    - 針對過多的特徵進行主成分分析降維，或利用統計方法找出前 30 個關鍵變數。
    - 使用三種以上的分類器（不限 Scikit-Learn 模組）建立模型並評估擇最佳模型或集成模型。
    - 請計算 AUC 並畫出混淆矩陣。
- 預期產出：
    - 清理後的特徵清單。
    - 混淆矩陣。
    - 符合 sample_submission.csv 格式的預測值。
    - 模型在驗證資料上的 AUC > 0.65
- 來源：Soraya_Jimenez and Will Cukierski. Santander Customer Satisfaction. <https://kaggle.com/competitions/santander-customer-satisfaction>, 2016. Kaggle.
- 檔名與概述：從第一線的客服團隊到高階管理層，客戶滿意度始終是衡量成功的關鍵指標。不快樂的客戶不會留下來；更重要的是，這些不滿意的客戶在離開之前，鮮少會主動表達他們的反感。Santander Bank 希望在客戶關係建立的初期，就辨識出那些潛在的不滿意客戶。若能做到這一點，就能在情況惡化之前，採取主動措施來提升客戶的滿意度。利用數百個去識別化（匿名化）的特徵，來預測客戶對其銀行服務體驗是感到滿意還是不滿意。
    - sample_submission.csv
    - test.csv
    - train.csv
- 樣本數與特徵數：

|資料表|樣本數|特徵數|
|-----|----:|----:|
|train|76,020|371|
|test|75,818|370|

\newpage

2. Home Credit Default Risk

你是任職於 Home Credit 的風管分析師，請在規定時間內使用 `application_train.csv` 與 `bureau.csv`，建立一個預測違約率（PD）的模型。

- 需求：
    - 計算每位客戶在 bureau.csv 中的「過往貸款總筆數」與「目前總欠款金額」，並將其合併回 application_train.csv。
    - application_train.csv 中有三個外部評分欄位 EXT_SOURCE_1/2/3，請處理其中的缺失值（用中位數填補或設為特定值）。
    - 使用三種以上的分類器（不限 Scikit-Learn 模組）建立模型並評估擇最佳模型或集成模型。
    - 請計算 AUC，並針對預測結果進行機率分組，觀察高機率組的實際違約比例。
- 預期產出：
    - 合併完成的特徵矩陣。
    - 機率分組 vs. 實際違約比例
    - 符合 sample_submission.csv 格式的預測值。
    - 模型在驗證資料上的 AUC > 0.65
- 來源：<https://www.kaggle.com/competitions/home-credit-default-risk>
- 檔名與概述：
    - application_{train|test}.csv：這是主表，分為訓練資料（含目標變數 TARGET）與測試資料（不含目標變數）。內容包含所有貸款申請案的靜態資料，每一列代表一筆貸款申請案。
    - bureau.csv：包含樣本客戶過往在其他金融機構申請、並回報給聯徵中心 (Credit Bureau) 的所有信用紀錄。針對樣本中的每一筆貸款申請，該客戶過去在聯徵中心有多少筆信用紀錄，此表就會對應顯示多少列。
    - bureau_balance.csv：聯徵中心過往信用紀錄的每月餘額明細。此表紀錄了回報至聯徵中心的每一筆既往信用紀錄的每月歷史資料。總列數等於（樣本貸款數 × 相關既往信用紀錄數 × 該信用紀錄可觀察的歷史月數）。
    - POS_CASH_balance.csv：申請人過往在 Home Credit 的 POS 機 (Point of Sales) 貸款與現金貸款的每月餘額快照。此表包含與樣本貸款相關的每一筆 Home Credit 既往信用（消費信貸與現金貸款）的每月歷史紀錄。
    - credit_card_balance.csv：申請人過往在 Home Credit 的信用卡每月餘額快照。此表包含與樣本貸款相關的每一張 Home Credit 既往信用卡之每月歷史紀錄。
    - previous_application.csv：包含樣本客戶過往在 Home Credit 申請的所有貸款紀錄。樣本中的每筆貸款若有對應的過往申請案，皆會在此表以獨立的一列呈現。
    - installments_payments.csv：與樣本貸款相關的 Home Credit 既往已撥款信用之還款歷史紀錄。包含每一筆已繳款紀錄，以及每一筆漏繳紀錄。每一列相當於「一筆分期付款的一次繳款紀錄」或「一次繳款對應的一筆分期付款」。
    - HomeCredit_columns_description.csv：此檔案包含各個資料檔案中所有欄位的詳細定義與說明。
    - sample_submission.csv
- 樣本數與特徵數：

|資料表|樣本數|特徵數|
|-----|----:|----:|
|application_train|307,511|122|
|application_test|48,744|121|
|bureau|1,716,428|17|
|bureau_balance|27,299,925|3|
|POS_CASH_balance|10,001,358|8|
|credit_card_balance|3,840,312|23|
|previous_application|1,670,214|37|
|installments_payments|13,605,401|8|

\newpage

3. All Lending Club loan data

你是任職於 Lending Club 風險管理部門的風管分析師，請在規定時間內針對已經違約的貸款案件，建立一個違約損失率（LGD）模型。

- 需求：
    - 樣本僅篩選 loan_status 為 "Charged Off" 的觀測值，因為只有違約的人才有 LGD
    - LGD 計算方式：`LGD = 1 - (recoveries / loan_amnt)` 
    - 若 LGD 計算結果小於 0（超額回收）或大於 1，請將其強制修正在 [0, 1] 區間。
    - 選取核貸時可得的特徵，不要使用例如 total_rec_int 或 last_pymnt_d 作為特徵，因為這些是違約過程中產生的數據，核貸時無法預知。
    - 將類別變數進行 One-Hot Encoding 或 Ordinal Encoding
    - 使用三種以上的回歸模型（不限 Scikit-Learn 模組）建立模型並評估擇最佳模型或集成模型。
- 預期產出：
    - LGD 分佈直方圖（Histogram）：觀察違約者的損失率分佈。
    - (m, 2) 外型的預測值，m 為驗證資料列數（可以用 20-30% 作為驗證比例），第一個欄位是 `id`、第二個欄位是 `LGD`
    - 模型在驗證資料的 MSE/MAE 應低於單純用平均值預測（Baseline model）的誤差。
- 來源：<https://www.kaggle.com/datasets/wordsforthewise/lending-club>
- 檔名與概述：
    - accepted_2007_to_2018Q4.csv：資料集包含 LendingClub 平台從 2007 年創立至 2018 年第四季的所有貸款申請紀錄。紀錄了每筆貸款從申請、審核、撥款到最終還款或違約的完整生命週期。
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

\newpage

4. Bank product recommendation

你是任職於 Santander Bank 的信用卡產品經理，請在規定時間內建立一個分類模型，預測哪些客戶在 2016 年 6 月會新購買信用卡(ind_tjcr_fin_ult1)。

- 需求：
    - 不預測全部 24 種產品，僅鎖定信用卡(ind_tjcr_fin_ult1)作為目標。
    - 時間選取 2016-04-28（作為特徵期）與 2016-05-28（作為標籤期）的數據。
    - 串接 4 月與 5 月的資料。
    - 定義「新購買」：
        - 條件 A：該客戶在 4 月 沒有 信用卡 (ind_tjcr_fin_ult1 == 0)
        - 條件 B：該客戶在 5 月 持有 信用卡 (ind_tjcr_fin_ult1 == 1)
        - 符合條件 A 以及 條件 B 則 Target = 1（新購買），其餘為 0
    - 處理 age (年齡)、renta (年收入，需填補缺失值)、segment (客戶分群)
    - 計算每個客戶在 4 月份一共持有了多少種「其他產品」（加總其餘 23 項產品的數量）。
    - 利用 fecha_alta (入行日期) 計算該客戶截至 2016 年 4 月的入行月數。
    - 使用三種以上的分類器（不限 Scikit-Learn 模組）建立模型並評估擇最佳模型或集成模型。
- 預期產出：
    - 找出預測機率最高的前 100 名客戶，對照他們的年齡與年收入。
    - 混淆矩陣。
    - 比較「入行月數」還是「持有產品數」對購買信用卡的預測力更強。
    - (929615, 2) 外型的預測值，第一個欄位是 `ncodpers`、第二個欄位是 `ind_tjcr_fin_ult1`
    - 模型在驗證資料的 Accuracy/F1 Score 高於 Baseline model

- 來源：<https://www.kaggle.com/competitions/santander-product-recommendation>
- 檔名與概述：資料集包含 Santander 銀行 1.5 年的客戶行為紀錄。目標是根據客戶過去的持有紀錄與人口統計學特徵，預測客戶在 2016 年 6 月會新增哪些金融產品。
    - sample_submission.csv
    - test_ver2.csv
    - train_ver2.csv

- 樣本數與特徵數：

|資料表|樣本數|特徵數|
|-----|----:|----:|
|train_ver2|13,647,309|48|
|test_ver2|929,615|24|

- 特徵：
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

\newpage

5. Santander Value Prediction

你是任職於 Santander Bank 的客戶關係經理，請在規定時間內建立一個能夠預測客戶「交易價值」的模型。

- 需求：
    - 找出並刪除變異數為 0 的特徵。
    - 計算每個特徵的「非零個數」，刪除那些非零個數低於 1% 的特徵。
    - 觀察目標變數 `target` 的分佈，觀察後進行 Log 轉換再重新觀察。
    - 計算特徵與 `target` 之間的相關係數，保留相關性最高的前 200 個特徵
    - 產出 Feature Importance，選出貢獻度最高的前 50 個特徵。
    - 使用三種以上的回歸模型（不限 Scikit-Learn 模組）建立模型並評估擇最佳模型或集成模型。
    - 使用 RMSLE(Root Mean Squared Logarithmic Error)作為模型評估指標。
- 預期產出：
    - 前五十 Feature Importance 排行。
    - 清理後的特徵清單。
    - 比較預測值與真實值的散佈圖（Scatter plot）。
    - 符合 sample_submission.csv 格式的預測值。
    - 模型在驗證資料上的 RMSLE(Root Mean Squared Logarithmic Error)優於直接取平均值的 Baseline
    - 匿名特徵建模的心得，在不了解業務邏輯時，如何量測特徵的重要性？
- 來源：<https://www.kaggle.com/competitions/santander-value-prediction-challenge>
- 檔名與概述：Santander Bank 不僅要辨識出客戶對金融服務的需求，還要進一步判斷客戶交易的具體金額或價值，識別每位潛在客戶的交易價值，這是 Santander Bank 在實現大規模個人化服務必須精準踏出的第一步。
    - sample_submission.csv
    - test.csv
    - train.csv
- 樣本數與特徵數：

|資料表|樣本數|特徵數|
|-----|----:|----:|
|train|4,459|4,993|
|test|49,342|4,992|

\newpage

## 附錄：資料集下載

請參考 [Google 雲端硬碟](https://drive.google.com/drive/folders/1TDTJFM0lPxfpD_usCEoSutyDyy3V9428?usp=drive_link)