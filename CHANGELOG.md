# Changelog

所有重要的版本變更都會記錄在這裡。
格式基於 [Keep a Changelog](https://keepachangelog.com/)，版本號遵循 [Semantic Versioning](https://semver.org/)。

## [0.3.0] - 2026-04-15

### 新功能

#### 八大核心
- README 新增 OctoWork 八大核心：角色定義、技能、流程、累積、引導、進步、外部資源、成長

#### AI Agent 技能中心
- 新增「不只是人用的工具」段落，定位 OctoWork 為 AI Agent 的技能層
- 附架構圖：觸發層（Agent 框架）→ 技能層（OctoWork）→ 執行層（MCP/API）

#### 復盤系統重新設計
- 從「按檔案面向問問題」改為五階段混合框架
- Phase 1：多輪收集痛點（可跳過，有引導問題，有三選項）
- Phase 2：追問「為什麼」，找根本原因再改
- Phase 3：AI 掃全系統，技能和流程各三層深度（缺什麼/改什麼/深化什麼）
- Phase 4：展望下個月
- Phase 5：清理 + 摘要 + 下次復盤預告
- 新增第七面向「目前進行中」
- 系統紀錄新增「下次復盤關注點」

#### 更多工具支援
- 新增 OpenAI Codex CLI 安裝和相容性
- 新增 VS Code + AI 擴充套件
- 新增 Google Antigravity

#### 目錄指令改為互動式
- 「目錄」從資訊列表改為六選項互動選單
- 選了之後 AI 讀對應檔案做 3-5 句摘要

### 改進

- 做事原則不再有數量上限，鼓勵建立工作百科全書，整理重點改為結構（分類/重複/時效/矛盾）
- Skill 產出和工作產出分開存放：工作產出→outputs/，Skill 檔案→.agents/skills/[name]/
- 修復生成器漏掉系統指令和系統規則的 bug
- 修正 cp 指令遺漏隱藏資料夾（.agents/）
- README 段落重新排列，閱讀順序更流暢
- 新增 Discord 社群 badge
- 新增兩張插圖（AI Agent banner、日常工作 banner）

### 移除
- 移除 Obsidian 段落
- 移除「核心概念」段落（與八大核心重複）

---

## [0.2.0] - 2026-04-13

### 新功能

#### 復盤系統
- 說「復盤」→ AI 讀完所有檔案，找出系統可以補強的地方，一個一個問你
- 系統記錄上次復盤日期，超過 30 天沒復盤，開工時自動提醒
- 復盤結束自動摘要更新了什麼

#### 目錄指令
- 說「目錄」→ 顯示互動式選單（個人總結/公司總結/產品總結/技能清單/流程清單/快速指令）
- 選了之後 AI 讀對應的檔案，用 3-5 句話做摘要總結

#### 訪談流程優化
- 一次只問一個問題，不再一次丟一堆
- 每輪訪談結束立刻存檔，中途關掉不會消失，下次從斷點繼續
- 四輪結束後問「還有想補充的嗎？」再開始生成
- Skill 清單讓使用者選要建哪幾個，不強迫全建

#### Skill 成熟度標籤
- Skill frontmatter 新增 `maturity` 欄位（draft → stable → proven → deprecated）
- 品質檢查從 5 項擴充為「基本」+「進階」兩組

### 改進

#### 結構精簡
- workspace/ 下直接放檔案，不再多一層使用者命名的子資料夾
- 品牌名稱統一為 OctoWork（原 work-os / Work-OS）

#### Marketing 範例補完
- 7 個 Skills 從 placeholder 全部重寫為完整內容（40-55 行）
- 3 個 Workflows 從 12-14 行擴充至 25-35 行

#### README 大幅更新
- 新增三個使用故事（社群小編芷涵、行銷企劃 Kevin、業務助理佩君）
- 新增「怎麼把 OctoWork 用在你的工作上」日常使用教學
- 新增「系統的生命週期」完整流程圖和指令對照表
- FAQ 從 5 題擴充為 13 題，含詳細說明
- 安裝教學從零開始（Node.js → AI 工具 → 下載）
- 修正 Gemini CLI 安裝指令 bug

#### 新增文件
- `docs/security.md` — 資料安全與隱私指南
- `docs/maintaining-your-system.md` — 系統維護指南（做事原則整理 + Skill 盤點）

#### 安全性
- 系統規則明確指示 Skill 只能存到 workspace/，不能存到全域路徑
- FAQ 誠實說明 AI 會處理檔案內容（雲端傳輸）
- Workflow 能力邊界誠實說明（不是全自動，每步要確認）

---

## [0.1.0] - 2026-04-13

### 首次發布

#### 新增
- 生成器 Skill（`core/generator/`）：透過訪談自動生成完整 OctoWork
- 門市營運專員範例（`examples/store-ops/`）：3 背景檔 + 9 Skills + 4 Workflows
- 電商行銷人員範例（`examples/marketing/`）：3 背景檔 + 7 Skills + 3 Workflows
- 模板檔案（`core/templates/`）：CLAUDE.md、company.md、products.md 的生成模板
- 完整文件（`docs/`）：快速開始、原理說明、Skill 撰寫指南、Workflow 撰寫指南、團隊導入指南、升級指南
- 支援 Claude Code 和 Gemini CLI 雙工具

---

## 版本號規則

- **主版本（1.0.0）**：架構有重大變動，可能需要使用者手動調整
- **次版本（0.2.0）**：新增範例、新功能、生成器改進，向下相容
- **修補版本（0.1.1）**：修 bug、改錯字、小調整
