# 李威揚 — 客服營運管理作品集

> 具備多年客服營運與團隊管理經驗，擅長識別現場問題、拆解流程需求，並運用 Excel、Google Sheets、SQL、Python 與 AI 輔助工具，將重複性查詢、報表整理、工單追蹤與營運監控流程**工具化**。
>
> 我的定位不是開發工程師，而是能讓工具真正服務管理需求的**管理型人才**。

> 說明：本作品集僅展示脫敏後的畫面、問題背景與功能設計；原始碼、真實營運資料與內部設定不公開。

---

## 📂 作品索引

| # | 專案名稱 | 核心能力 | 說明 |
|---|----------|----------|------|
| 003 | [客服營運監控 Dashboard](#003-客服營運監控-dashboard) | 數據可視化 / 後端整合 | 自動彙整多來源數據，即時呈現客服 KPI |
| 004 | [LINE 客服訊息資料化工具](#004-line-客服訊息資料化工具) | 訊息接收 / 同步保存 / 回溯監控 | 接收、同步與保存 LINE 官方帳號訊息，支援後續客服回溯與營運監控 |
| 005 | [醫療表單電子化與人工覆核工具](#005-醫療表單電子化與人工覆核工具) | OCR 流程電子化 / 人工覆核 / 規則標記 | 將固定格式表單轉為可覆核的結構化資料，輔助後續人工追蹤與資料整理 |

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

---

## 004 LINE 客服訊息資料化工具

### 💡 背景與問題

客服團隊透過 LINE 官方帳號與群組接收大量訊息，但訊息若只停留在即時對話介面，後續容易出現回溯困難、查詢分散、統計不易與高頻問題難以整理等狀況。當本機服務或人員作業中斷時，也需要避免訊息遺漏，確保資料能被保存與追蹤。

### 🔧 解法

建置 LINE 訊息接收、同步與保存流程，以 LINE Webhook 作為入口，將訊息落地至本機 PostgreSQL，並保留 JSONL 備援與 Cloudflare Workers / D1 雲端緩衝機制。本專案重點不是取代正式客服平台，而是將客服訊息資料化，提供後續回溯、監控、統計與分析的基礎。

**主要功能：**
- 💬 LINE Webhook 訊息接收與本機資料庫保存
- 🧾 多帳號 / 群組訊息紀錄與查詢基礎
- 🔁 Cloudflare Workers / D1 雲端接收緩衝與本機同步
- 🗂️ JSONL 備援、歷史回填與同步狀態追蹤
- 🧹 訊息去重、同步確認與維運查詢端點
- 📊 可供 Dashboard 或後續分析流程讀取，支援客服回溯與訊息量觀察

**技術組成：**
`Python` `Flask` `LINE Messaging API` `PostgreSQL` `Cloudflare Workers / D1` `JSONL`

### 📸 畫面截圖

![LINE 系統畫面 1](./004-line-api/screenshots/004demo-1.png)

![LINE 系統畫面 2](./004-line-api/screenshots/004demo-2.png)

---

## 005 醫療表單電子化與人工覆核工具

### 💡 背景與問題

部分醫療或健檢流程仍仰賴固定格式紙本表單與人工輸入，資料整理耗時且容易產生輸入錯誤。即使完成 OCR 辨識，也不能直接視為正式資料，仍需要人工覆核、欄位確認與後續整理流程，才能降低錯誤風險並支援後續追蹤作業。

### 🔧 解法

建置本機端 **MedicalRecordOCR Workbench**，將固定格式表單轉為可覆核的結構化資料。系統採取 trust-first / review-first 思路：OCR 結果只作為候選證據，正式匯出前仍需人工確認高風險或不確定欄位。後續資料可匯出為 JSON / CSV / Excel，或再匯入本機資料庫，供人工追蹤、資料整理與規則標記使用。

**主要功能：**
- 📝 固定格式表單 OCR 電子化與欄位抽取
- ✅ 人工覆核流程，避免 OCR 結果直接成為正式資料
- 📤 支援 JSON / CSV / Excel 匯出，便於後續整理與交付
- 📥 可透過 CSV / API 匯入本機資料庫，延伸為追蹤資料來源
- 🏷️ 以規則標記輔助人工追蹤、待確認項目與例外狀況整理
- 📊 提供工作台介面，協助查看欄位結果、覆核狀態與資料整理進度

**技術組成：**
`Python` `PostgreSQL` `OCR` `CSV / API 匯入` `規則標記` `Dashboard UI`

### 📸 畫面截圖

![MedicalRecordOCR Workbench](./005-medical-data-workbench/screenshots/005demo-1.jpg)

![病人追蹤 Dashboard](./005-medical-data-workbench/screenshots/005demo-2.png)

### 📎 補充說明

這個作品的重點不是以系統取代醫療判斷，而是把固定格式文件處理、人工覆核、資料匯出與後續追蹤輔助流程串成可操作的工作台。系統輸出作為資料整理與人工追蹤參考，仍需由實際業務人員或專業人員確認後使用。

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
