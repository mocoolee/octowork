# Changelog

所有重要的版本變更都會記錄在這裡。
格式基於 [Keep a Changelog](https://keepachangelog.com/)，版本號遵循 [Semantic Versioning](https://semver.org/)。

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
