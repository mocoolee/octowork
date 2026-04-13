<p align="center">
  <img src="assets/logo.png" alt="OctoWork Logo" width="300">
</p>

<h1 align="center">OctoWork</h1>

<p align="center"><strong>一個人，八隻手。用 AI 把你的工作變成可重複執行的系統。</strong></p>

OctoWork 是一個開源框架，讓任何上班族透過 AI 建構自己的工作作業系統。你不需要會寫程式——回答幾個問題，10 分鐘就能生成一整套個人化的工作系統。

支援 [Claude Code](https://docs.anthropic.com/en/docs/claude-code) 和 [Gemini CLI](https://github.com/google-gemini/gemini-cli)。

---

## 這是什麼？

大部分人用 AI 的方式是「每次都重新講一遍需求」。OctoWork 讓 AI 記住你的一切——你的公司、你的產品、你的做事方式——然後用可重複執行的「技能（Skill）」和「流程（Workflow）」幫你做事。

- **做過的事** → 存成 Skill → 下次 AI 自動做
- **一串事** → 串成 Workflow → 一句話啟動流水線
- **學到的經驗** → 加回系統 → AI 越用越懂你

**最終目標：一個人就是一個部門。**

---

## 30 秒看懂

```
你的 work-os/
├── CLAUDE.md          ← 你是誰 + 你怎麼做事
├── company.md         ← 你的公司、品牌、客群
├── products.md        ← 你的產品/服務（可選）
├── .agents/skills/    ← 技能模組
├── workflows/         ← 工作流程
└── outputs/           ← 所有產出
```

你只維護前面 3 個檔案。Skills 和 Workflows 在工作中自然長出來。

---

## 使用教學

### Step 0：安裝 AI CLI 工具

OctoWork 需要搭配一個 AI CLI 工具來運作。請先安裝以下任一個：

| 工具 | 安裝方式 | 官方文件 |
|------|---------|---------|
| Claude Code | `npm install -g @anthropic-ai/claude-code` | [文件](https://docs.anthropic.com/en/docs/claude-code) |
| Gemini CLI | `npm install -g @anthropic-ai/claude-code` 或參考官方 | [文件](https://github.com/google-gemini/gemini-cli) |

安裝完後，在終端機輸入 `claude` 或 `gemini` 確認可以啟動。

### Step 1：下載 OctoWork

```bash
git clone https://github.com/mocoolee/octowork.git
cd octowork
```

### Step 2：啟動 AI 並建立你的 work-os

```bash
claude
```

> 如果用 Gemini CLI，先執行 `cp CLAUDE.md GEMINI.md`，再輸入 `gemini`。

AI 啟動後，跟它說：

```
幫我建一套 work-os
```

### Step 3：回答 AI 的訪談問題（約 10 分鐘）

AI 會用聊天的方式問你 4 輪問題：

| 輪次 | 主題 | 會問什麼 |
|------|------|---------|
| 第 1 輪 | 你是誰 | 公司、職稱、KPI、團隊、工具 |
| 第 2 輪 | 你怎麼做事 | 決策依據、協作者風格、踩過的坑 |
| 第 3 輪 | 重複工作 | 每天/每週/每月固定做的事 |
| 第 4 輪 | 工作流程 | 有沒有一條龍的串接任務 |

像跟同事聊天就好，不用準備什麼。

### Step 4：確認 AI 生成的內容

訪談結束後，AI 會自動生成：

- **CLAUDE.md** — 你的角色設定、做事原則
- **company.md** — 公司背景資料
- **products.md** — 產品/服務資料（如果需要）
- **5-7 個 Skills** — 你最常做的重複性工作
- **2-4 個 Workflows** — 可以一句話觸發的流水線

所有檔案都在 `workspace/你取的名字/` 裡面。

### Step 5：開始使用！

生成完就能直接用了。啟動 AI 後說：

```
開工
```

或指定要進入哪個系統：

```
進入 [你的 work-os 名稱] 的系統
```

AI 就會切換到工作模式，按照你的系統來做事。

---

## 使用範例

以下是進入工作模式後，你可以怎麼用：

### 使用單一 Skill

```
幫我寫今天的日報
```
→ AI 會找到「日報」Skill，按照你設定的格式自動產出。

### 啟動整個 Workflow

```
啟動每日晨會流程
```
→ AI 會依序跑完流程裡的每一步：看數據 → 分析異常 → 準備報告。

### 讓系統越來越聰明

做完一件事後，AI 會問你：
```
有沒有什麼值得記下來的經驗？
```

你分享的經驗會被加到 CLAUDE.md 的「做事原則」裡，下次 AI 就會記住。

### 新增一個 Skill

碰到新的重複工作，跟 AI 說：
```
把剛才的做法存成一個 Skill
```
→ AI 會自動生成新的 Skill 檔案，下次同樣的事就不用重新講。

---

## 不想被訪談？從範例開始改

如果覺得訪談太花時間，可以直接用現成的範例：

```bash
# 在 AI 裡面說
我要看範例
```

或手動複製：

```bash
cp -r examples/store-ops workspace/my-work-os
```

目前有這些範例：

| 範例 | 適合角色 | 內含 |
|------|---------|------|
| `store-ops` | 門市營運專員 | 9 Skills + 4 Workflows |
| `marketing` | 電商行銷人員 | 7 Skills + 3 Workflows |

複製後修改 `CLAUDE.md`、`company.md`、`products.md` 裡的內容就好。

---

## 專案結構

```
octowork/
├── CLAUDE.md                  ← 入口指令
├── VERSION                    ← 版本號
├── CHANGELOG.md               ← 版本紀錄
│
├── core/                      ← 🔒 框架核心（升級時更新）
│   ├── generator/                生成器
│   └── templates/                模板
│
├── examples/                  ← 🔒 範例庫（升級時更新）
│   ├── store-ops/
│   └── marketing/
│
├── docs/                      ← 🔒 文件（升級時更新）
│
└── workspace/                 ← 🔓 你的資料（永不被動到）
    └── my-work-os/
```

**🔒 = 專案的**（`git pull` 會更新）
**🔓 = 你的**（`.gitignore` 保護，永遠不動）

---

## 核心概念

### Skill = 你的能力外部化
做了第二次的事 → 存成 Skill → 從此 AI 幫你做。

### Workflow = Skill 的流水線
「啟動母親節檔期」→ 庫存檢查 → 文案 → 佈達 → 追蹤表。一句話搞定。

### 越做越聰明
做完事 → AI 問你「學到什麼」→ 自動更新做事原則 → 下次做得更好。

---

## 升級

OctoWork 會持續更新——新增範例、優化生成器、修 bug。你的資料不會受影響。

```bash
# 在 AI 裡面說
幫我更新
```

或手動更新：

```bash
git pull origin main
```

AI 會告訴你更新了什麼，並問你要不要把新功能裝到你的系統裡。詳見 [升級指南](docs/upgrading.md)。

---

## 相容性

| 工具 | 狀態 | 說明 |
|------|------|------|
| Claude Code | ✅ | CLAUDE.md + .agents/skills/ |
| Gemini CLI | ✅ | 改名 GEMINI.md，格式通用 |
| 其他 AI CLI | 🟡 | 核心是 Markdown，可適配 |

---

## 常見問題

**Q：我需要會寫程式嗎？**
A：完全不用。所有操作都是用自然語言跟 AI 對話。

**Q：我的資料安全嗎？**
A：你的 work-os 檔案都存在本地的 `workspace/` 裡，不會上傳到任何地方。

**Q：升級會不會覆蓋我的東西？**
A：不會。`workspace/` 被 `.gitignore` 保護，`git pull` 只會更新框架部分。

**Q：可以給團隊裡的多個人用嗎？**
A：可以。每個人在自己的 `workspace/` 裡建自己的 work-os，共用同一套框架。詳見 [團隊部署](docs/team-deployment.md)。

**Q：我想自己寫 Skill 可以嗎？**
A：可以。在 `.agents/skills/` 裡新增一個資料夾，放一個 SKILL.md 就好。詳見 [寫 Skill 教學](docs/writing-skills.md)。

---

## 靈感來源

OctoWork 融合了 GTD、PARA、Second Brain、Agentic AI Workflows 的精華，但重新設計為「AI 幫你執行」而非「你自己執行」。

---

## 貢獻

歡迎提交新的角色範例！詳見 [CONTRIBUTING.md](CONTRIBUTING.md)。

## License

MIT
