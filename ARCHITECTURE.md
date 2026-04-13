# OctoWork 專案架構

## 核心原則：框架與使用者資料完全分離

```
octowork/                          ← git 管理的專案（可升級）
├── README.md
├── LICENSE
├── CHANGELOG.md                   ← 🆕 版本紀錄，使用者看這個決定要不要升級
├── VERSION                        ← 🆕 當前版本號（語義化版本）
├── CLAUDE.md                      ← 專案入口指令
│
├── core/                          ← 🔒 框架核心（升級時覆蓋）
│   ├── generator/                    生成器 Skill
│   │   ├── SKILL.md
│   │   └── references/
│   │       └── examples.md
│   └── templates/                    模板檔案（生成時參考用）
│       ├── CLAUDE.md.template
│       ├── company.md.template
│       └── products.md.template
│
├── examples/                      ← 🔒 範例庫（升級時覆蓋）
│   ├── store-ops/                    門市營運
│   ├── marketing/                    電商行銷
│   └── ...                           社群貢獻的新範例
│
├── docs/                          ← 🔒 文件（升級時覆蓋）
│   ├── getting-started.md
│   ├── how-it-works.md
│   ├── writing-skills.md
│   ├── writing-workflows.md
│   ├── upgrading.md                  🆕 升級指南
│   └── team-deployment.md
│
├── workspace/                     ← ⚠️ 使用者的工作區（git ignored，永不覆蓋）
│   ├── CLAUDE.md, company.md, products.md（直接放這裡，不建子資料夾）
│   ├── .agents/skills/（Skills）
│   └── workflows/（Workflows）
│
└── .gitignore                     ← workspace/ 被忽略
```

## 兩個區域的規則

### 🔒 框架區（core/ + examples/ + docs/）
- 由專案維護者管理
- 使用者 `git pull` 時會被更新
- 使用者不應該修改這裡的檔案

### ⚠️ 使用者區（workspace/）
- 使用者的檔案直接放在 workspace/ 根目錄，不建子資料夾
- 被 .gitignore 忽略
- `git pull` 永遠不會碰到這裡的檔案
- 這是使用者的資料，只屬於他們

## 升級流程

使用者要升級時：
1. 看 CHANGELOG.md 了解新版本改了什麼
2. 執行 `git pull`
3. core/ 和 examples/ 會更新，workspace/ 不受影響
4. 如果新版本的生成器有改進，使用者可以選擇重新跑生成器來更新自己的系統
