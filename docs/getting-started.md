# 快速開始

## 前置條件

你需要安裝以下其中一個 AI CLI 工具：

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code)（Anthropic）
- [Gemini CLI](https://github.com/google-gemini/gemini-cli)（Google）

## 安裝 OctoWork

```bash
git clone https://github.com/你的帳號/octowork.git
cd octowork
```

## 開始使用

### 用 Claude Code

```bash
claude
```

Claude 會讀取 CLAUDE.md，知道這是 OctoWork 專案。直接說：

```
幫我建一套 work-os
```

### 用 Gemini CLI

```bash
# 先把入口指令改名
cp CLAUDE.md GEMINI.md
gemini
```

## 接下來會發生什麼

1. AI 會用聊天的方式問你 4 輪問題（約 10 分鐘）
2. 自動在 `workspace/` 裡生成你的完整 work-os
3. 你可以立刻開始使用

## 不想被訪談？

直接複製範例來改：

```bash
cp -r examples/store-ops workspace/my-work-os
cd workspace/my-work-os
claude
```

然後把 CLAUDE.md、company.md、products.md 裡的內容換成你自己的。
