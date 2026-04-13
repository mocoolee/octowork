# 快速開始

從零開始，到你第一次用 OctoWork 完成工作，大概 15 分鐘。

---

## 1. 安裝 Node.js

AI CLI 工具需要 Node.js 才能跑。如果你的電腦已經有了，可以跳過這步。

到 [nodejs.org](https://nodejs.org/) 下載 **LTS 版本**（左邊那個按鈕），安裝時一直按下一步就好。

裝完後打開終端機，輸入：

```bash
node -v
```

看到版本號（例如 `v22.x.x`）就代表成功。

> **什麼是終端機？** Mac 按 `Cmd + 空白鍵` 搜尋「Terminal」或「終端機」。Windows 按 `Win` 搜尋「PowerShell」。就是一個可以打字下指令的視窗。

---

## 2. 安裝 AI 工具

選一個就好，兩個都能跑 OctoWork。

### 選項 A：Claude Code（推薦）

```bash
npm install -g @anthropic-ai/claude-code
```

安裝完輸入 `claude`，會引導你登入。你需要一個 [Anthropic 帳號](https://console.anthropic.com/)。

### 選項 B：Gemini CLI

```bash
npm install -g @google/gemini-cli
```

安裝完輸入 `gemini`，會引導你登入 Google 帳號。

### 安裝卡住了？

| 問題 | 原因 | 解法 |
|------|------|------|
| `command not found` | Node.js 沒裝好 | 回第 1 步重裝一次 |
| `permission denied` | Mac 權限問題 | 指令前面加 `sudo`，例如 `sudo npm install -g ...` |
| `npm ERR` | 網路問題 | 換個網路、或等一下再試 |

---

## 3. 下載 OctoWork

```bash
git clone https://github.com/mocoolee/octowork.git
cd octowork
```

> 沒裝 git？直接到 [GitHub 頁面](https://github.com/mocoolee/octowork) 點「Code → Download ZIP」，解壓縮後用終端機 `cd` 進去。

---

## 4. 建立你的系統

### 用 Claude Code

```bash
claude
```

### 用 Gemini CLI

```bash
cp CLAUDE.md GEMINI.md
gemini
```

AI 啟動後，跟它說：

```
幫我建一套 OctoWork
```

AI 會用聊天的方式問你四輪問題（大概 10 分鐘）：

| 輪次 | 聊什麼 | 大概會問 |
|------|--------|---------|
| 第 1 輪 | 你是誰 | 公司、職稱、KPI、團隊、常用工具 |
| 第 2 輪 | 你怎麼做事 | 判斷依據、協作者風格、踩過的坑 |
| 第 3 輪 | 重複的工作 | 每天/每週/每月固定做的事 |
| 第 4 輪 | 一條龍流程 | 做完 A 就要接著做 B 再做 C 的工作 |

像跟同事聊天就好，不用準備什麼。

聊完之後，AI 會在 `workspace/` 裡生成你的完整系統：CLAUDE.md、company.md、products.md、5-7 個 Skills、2-4 個 Workflows。

---

## 5. 不想被訪談？

直接複製一份範例來改：

```bash
cp -r examples/store-ops workspace/my-octowork
```

| 範例 | 適合誰 | 內含 |
|------|--------|------|
| `store-ops` | 門市營運 | 9 Skills + 4 Workflows |
| `marketing` | 電商行銷 | 7 Skills + 3 Workflows |

複製後把 `CLAUDE.md`、`company.md`、`products.md` 裡的內容換成你自己的就好。

---

## 6. 開始使用

系統建好之後，每次要工作就：

```bash
cd octowork
claude
```

跟 AI 說：

```
開工
```

AI 會讀取你的系統，切換到工作模式。從這一刻起，它知道你是誰、你的公司在做什麼、你的主管喜歡什麼格式。

接下來你可以：

- **做事**：「幫我寫今天的日報」→ AI 用你定義的 Skill 產出
- **跑流程**：「啟動每日晨會流程」→ AI 按步驟引導你完成
- **累積經驗**：做完後 AI 會問「有沒有值得記下來的？」→ 自動加到做事原則
- **新增 Skill**：「把剛才的做法存成 Skill」→ 下次同樣的事不用重新講
