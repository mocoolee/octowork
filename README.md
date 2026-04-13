# OctoWork 🐙

**一個人，八隻手。用 AI 把你的工作變成可重複執行的系統。**

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

## 快速開始

### 方法一：自動生成（推薦）

```bash
git clone https://github.com/你的帳號/octowork.git
cd octowork
claude                   # 或 gemini
> 幫我建一套 work-os
```

AI 會用聊天的方式訪談你，然後自動生成整套系統。約 10-15 分鐘。

### 方法二：從範例改

```bash
# 查看有哪些範例
ls examples/

# 複製到你的工作區
cp -r examples/store-ops workspace/my-work-os

# 改成你自己的內容
```

| 範例 | 角色 | 內含 |
|------|------|------|
| `store-ops` | 門市營運專員 | 9 Skills + 4 Workflows |
| `marketing` | 電商行銷人員 | 7 Skills + 3 Workflows |

---

## 升級

OctoWork 會持續更新——新增範例、優化生成器、修 bug。你的資料不會受影響。

```bash
# 查看目前版本
cat VERSION

# 查看更新了什麼
cat CHANGELOG.md

# 升級（你的 workspace/ 不會被動到）
git pull
```

詳見 [升級指南](docs/upgrading.md)。

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

## 相容性

| 工具 | 狀態 | 說明 |
|------|------|------|
| Claude Code | ✅ | CLAUDE.md + .agents/skills/ |
| Gemini CLI | ✅ | 改名 GEMINI.md，格式通用 |
| 其他 AI CLI | 🟡 | 核心是 Markdown，可適配 |

---

## 靈感來源

OctoWork 融合了 GTD、PARA、Second Brain、Agentic AI Workflows 的精華，但重新設計為「AI 幫你執行」而非「你自己執行」。

---

## 貢獻

歡迎提交新的角色範例！詳見 [CONTRIBUTING.md](CONTRIBUTING.md)。

## License

MIT
