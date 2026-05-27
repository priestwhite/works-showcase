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

> *(截圖整理中，請稍候)*

<!-- 截圖上傳後，請將下方註解取代為實際圖片 -->
<!-- ![KPI 總覽](./003-dashboard/screenshots/01-kpi-overview.png) -->
<!-- ![工單追蹤](./003-dashboard/screenshots/02-ticket-tracking.png) -->
<!-- ![Excel 匯入](./003-dashboard/screenshots/03-excel-import.png) -->

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

> *(截圖整理中，請稍候)*

<!-- ![訊息管理介面](./004-line-api/screenshots/01-message-inbox.png) -->
<!-- ![分析報表](./004-line-api/screenshots/02-analysis-report.png) -->

### 📎 相關連結

- 🔗 [原始碼 Repository](https://github.com/priestwhite/004.LineApiIntegration)

---

## 🛠️ 工具能力概覽

| 類別 | 工具 / 技術 |
|------|-------------|
| 語言 | Python、SQL、TypeScript |
| 後端 | FastAPI、Flask |
| 前端 | React、HTML/CSS |
| 資料庫 | PostgreSQL、SQLite |
| 自動化 | APScheduler、IMAP 信箱整合、Excel 批次處理 |
| AI 工具 | Gemini API、GitHub Copilot、Claude |
| 管理工具 | Excel、Google Sheets、Notion |

---

## 📬 聯絡方式

如有職缺洽詢或合作機會，歡迎透過 GitHub Issues 或直接聯繫。
