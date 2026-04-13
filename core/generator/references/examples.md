# Work-OS 範例參考

本檔案提供兩個完整範例，讓生成器知道不同角色的 work-os 應該包含什麼。

---

## 範例 A：門市營運專員

### 角色概述
管理 4 家連鎖門市，負責業績追蹤、巡店、人員管理、檔期執行。

### 檔案結構
```
work-os/
├── CLAUDE.md（142 行）
├── company.md（168 行）── 門市資料、營運標準、稽核項目、客訴權限
├── products.md（203 行）── 商品品類、主力品賣點與話術、庫存規範
├── .agents/skills/
│   ├── daily-report/      每日營業數據 → 日報 + 異常標示
│   ├── weekly-report/     週數據 → 主管週報（先結論後數據）
│   ├── store-inspection/  碎片巡店筆記 → 正式巡店報告 + 評分
│   ├── staff-scheduling/  排班需求 → 建議班表 + 衝突提示
│   ├── customer-complaint/ 客訴描述 → 紀錄 + 回覆話術 + 預防措施
│   ├── campaign-rollout/  總部公告 → 白話版通知 + 各店客製提醒
│   ├── sop-builder/       口述流程 → 正式 SOP 文件
│   ├── meeting-minutes/   會議筆記 → 結構化紀錄 + 行動項目
│   └── inventory-alert/   庫存數據 → 補貨警示 + 建議補貨單
├── workflows/
│   ├── daily-morning.md    每日早會：數據→日報→LINE精簡版
│   ├── store-visit.md      巡店：筆記→報告→店長版→LINE版
│   ├── campaign-rollout.md 檔期：庫存檢查→佈達→追蹤表
│   └── friday-closing.md   週五：週報→下週計畫→更新原則
└── outputs/
```

### CLAUDE.md 特色
- 做事原則分 6 大類：數據判讀、巡店、人員管理、客訴、報告、檔期
- 協作者包含 4 位店長，每人標註年資、強弱項、溝通方式
- 系統規則包含「做完後提醒更新做事原則」的回饋機制

---

## 範例 B：電商行銷人員

### 角色概述
一人行銷部，負責官網、SEO、Google/Meta 廣告、EDM、Landing Page。

### 檔案結構
```
work-os/
├── CLAUDE.md（120 行）
├── company.md（150 行）── 品牌語氣、客群 Persona、管道佈局
├── products.md（180 行）── 各產品賣點、異議處理、歷史最佳素材
├── .agents/skills/
│   ├── weekly-report/     週數據 → 行銷週報
│   ├── ad-copy/           產品 + 目的 → 5 組不同角度的廣告文案
│   ├── edm-writer/        主題 → 完整 EDM（含 3 組主旨行）
│   ├── landing-page/      產品 + 檔期 → LP 完整文案結構
│   ├── seo-outline/       關鍵字 → 文章大綱 + 建議字數
│   ├── competitor-brief/  競品名 → 結構化競品分析
│   └── social-post/       主題 → IG/FB 貼文（3 則）
├── workflows/
│   ├── campaign-launch.md  檔期：LP→廣告→EDM→社群→checklist
│   ├── weekly-report.md    週五：數據→週報
│   └── content-pipeline.md SEO：關鍵字→大綱→初稿→檢查
└── outputs/
```

### CLAUDE.md 特色
- 做事原則分 5 大類：廣告、文案、SEO、報告、EDM
- 每條原則都有具體數字（CPA < $150、ROAS < 3 就停）
- 包含歷史學習（影片 ROAS 比圖片高 3 倍、問句開頭 CTR +22%）

---

## 不同角色的 company.md 該有什麼

| 角色 | company.md 重點內容 |
|------|-------------------|
| 門市營運 | 門市清單 + 各店目標 + 營運標準 + 稽核項目 + 客訴權限 |
| 行銷 | 品牌語氣 + 客群 Persona + 管道佈局 + 歷史行銷數據 |
| 業務 | 客戶分級 + 報價規範 + 競品對照 + 成交流程 |
| 客服 | 常見問題庫 + 處理權限 + 回覆模板 + 升級機制 |
| HR | 公司規章 + 招募流程 + 考核標準 + 福利制度 |
| 採購 | 供應商清單 + 採購流程 + 驗收標準 + 付款條件 |
| PM | 專案模板 + 里程碑定義 + 會議規範 + 利害關係人清單 |

## 不同角色常見的 Skills

| 角色 | 最常需要的 Skills |
|------|-----------------|
| 門市營運 | 日報、週報、巡店紀錄、排班、客訴、檔期佈達、SOP |
| 行銷 | 廣告文案、SEO 大綱、EDM、LP 文案、週報、競品分析 |
| 業務 | 提案書、報價單、客戶拜訪紀錄、跟進提醒、業績週報 |
| 客服 | 客訴回覆、FAQ 更新、服務品質報告、話術生成 |
| HR | 招募 JD、面試評估、入職文件、考核報告、離職分析 |
| 採購 | 比價分析、採購單、供應商評估、驗收報告 |
| PM | 專案計畫、會議紀錄、進度報告、風險評估、交接文件 |
