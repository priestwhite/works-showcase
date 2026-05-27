# 李威揚 — 客服營運管理作品集

> 具備多年客服營運與團隊管理經驗，擅長識別現場問題、拆解流程需求，並運用 Excel、Google Sheets、SQL、Python 與 AI 輔助工具，將重複性查詢、報表整理、工單追蹤與營運監控流程**工具化**。
>
> 我的定位不是開發工程師，而是能讓工具真正服務管理需求的**管理型人才**。

---

## 📂 作品索引

| # | 專案名稱 | 核心能力 | 說明 |
|---|----------|----------|------|
| 003 | [客服營運監控 Dashboard](#003-客服營運監控-dashboard) | 數據可視化 / 後端整合 | 自動彙整多來源數據，即時呈現客服 KPI |
| 004 | [LINE 客服整合系統](#004-line-客服整合系統) | API 整合 / 訊息管理 | 整合 LINE API 與後台系統，提升訊息處理效率 |
| 005 | [醫療資料電子化與追蹤決策系統](#005-醫療資料電子化與追蹤決策系統) | OCR 流程電子化 / 臨床規則整合 | 將手寫表單電子化，並結合臨床規則與累積數據提供追蹤提醒 |

> 📌 更多專案持續更新中

---

## 003 客服營運監控 Dashboard

### 💡 背景與問題

客服團隊每日需要跨系統（Excel 報表、工單平台、外部 API）手動彙整數據，製作日報、週報耗時且容易出錯，主管難以即時掌握團隊狀況與異常。

### 🔧 解法

自行設計並建置一套以 **Python FastAPI + React** 為核心的客服營運監控平台，整合多個數據來源，透過排程自動同步，提供即時可視化看板。

**主要功能：**
- 📊 KPI 即時總覽（工單量、處理時效、異常率）
- 📁 Excel 自動匯入與解析（支援多格式、欄位對應設定）
- 🔄 排程自動同步外部系統數據
- 📬 信箱自動抓取附件並觸發匯入流程
- 📤 支援多格式匯出（Excel / CSV / JSON）
- 🔐 JWT 身份驗證 + 審計日誌

**技術組成：**
`Python` `FastAPI` `PostgreSQL` `React` `SQLAlchemy` `APScheduler` `IMAP`

### 📸 畫面截圖

![Dashboard 畫面 1](./003-dashboard/screenshots/003demo-1.png)

![Dashboard 畫面 2](./003-dashboard/screenshots/003demo-2.png)

![Dashboard 畫面 3](./003-dashboard/screenshots/003demo-3.png)

### 📎 相關連結

- 🔗 [原始碼 Repository](https://github.com/priestwhite/003.Dashboard-V2.0)

---

## 004 LINE 客服整合系統

### 💡 背景與問題

客服透過 LINE 接收大量客戶訊息，但缺乏系統化的管理與追蹤機制，訊息容易遺漏，也難以分析高頻問題。

### 🔧 解法

整合 LINE Messaging API，建置後台管理介面，讓客服能統一處理、標記與追蹤 LINE 訊息，並結合 AI 模型進行訊息分析。

**主要功能：**
- 💬 LINE 訊息統一收件與回覆介面
- 🏷️ 訊息分類與標記管理
- 🤖 AI 輔助分析（問題分類、關鍵字萃取）
- 📊 訊息量趨勢報表

**技術組成：**
`Python` `LINE Messaging API` `Gemini AI` `FastAPI` `PostgreSQL`

### 📸 畫面截圖

![LINE 系統畫面 1](./004-line-api/screenshots/004demo-1.png)

![LINE 系統畫面 2](./004-line-api/screenshots/004demo-2.png)

### 📎 相關連結

- 🔗 [原始碼 Repository](https://github.com/priestwhite/004.LineApiIntegration)

---

## 005 醫療資料電子化與追蹤決策系統

### 💡 背景與問題

醫療現場仰賴大量手寫表單與檢驗資料，人工輸入、整理與追蹤耗時且容易出錯。即使完成資料電子化，若沒有再結合院內既有資料與醫療判斷規則，仍難以有效支援個案追蹤與衛教提醒。

### 🔧 解法

建置一套由 **MedicalRecordOCR Workbench + 病人追蹤 Dashboard** 組成的系統。前段將手寫表單轉為可覆核的結構化資料，後段則透過 API 或 CSV 匯入本地 PostgreSQL，並整合檢驗所或院內其他累積數據，依據與醫師、個管師共同討論整理出的判斷邏輯，產出衛教提醒、追蹤標記與優先處理項目。

**主要功能：**
- 📝 手寫表單 OCR 電子化與人工覆核流程
- 📥 支援 API / CSV 匯入本地 PostgreSQL
- 🧪 整合檢驗所與院內既有數據
- 🧠 將醫師與個管師討論出的判斷依據轉為演算法規則
- 🔔 自動產出衛教內容提醒與追蹤建議
- 📊 提供病人工作台、檢驗歷程與優先行動視圖

**技術組成：**
`Python` `PostgreSQL` `OCR` `CSV / API 匯入` `規則引擎` `Dashboard UI`

### 📸 畫面截圖

<!-- 圖片上傳後取消下方兩行的註解 -->
<!-- ![MedicalRecordOCR Workbench](./005-medical-data-workbench/screenshots/005demo-1.png) -->
<!-- ![病人追蹤 Dashboard](./005-medical-data-workbench/screenshots/005demo-2.png) -->

### 📎 補充說明

這個作品的重點不只是 OCR，而是把文件處理流程、資料整合流程與追蹤決策規則串成一套可操作系統。除了提升資料電子化效率，也讓後續追蹤、衛教與例外狀況辨識更有依據。

---

## 🛠️ 工具能力概覽

| 類別 | 工具 / 技術 |
|------|-------------|
| 語言 | Python、SQL、TypeScript、Go（少量使用） |
| 後端 | FastAPI、Flask |
| 前端 | React、TypeScript、HTML/CSS |
| 資料庫 | PostgreSQL、MySQL（現以 PostgreSQL 為主）、SQLite |
| 自動化 | APScheduler、IMAP 信箱整合、Excel 批次處理 |
| AI 工具 | Gemini API、GPT、Grok、GitHub Copilot、Claude |
| 管理工具 | Excel、Google Sheets |

---

## 📬 聯絡方式

如有職缺洽詢或合作機會，歡迎透過 GitHub Issues 或直接聯繫。
