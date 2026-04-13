# 升級指南

## 你的資料安全嗎？

安全。你的工作資料在 `workspace/` 裡，這個資料夾被 `.gitignore` 保護，`git pull` 永遠不會碰到它。

升級只會更新 `core/`（生成器）、`examples/`（範例）、`docs/`（文件）。

## 怎麼升級

### Step 1：看看有什麼更新

```bash
# 查看目前版本
cat VERSION

# 拉最新版本（還沒套用）
git fetch origin

# 看差異
git log HEAD..origin/main --oneline
```

或直接看 GitHub 上的 [CHANGELOG.md](../CHANGELOG.md)。

### Step 2：決定要不要升級

看 CHANGELOG.md 的分類：

- **新範例**：不影響你，純粹多了可以參考的範例
- **生成器改進**：不影響已生成的系統，但新生成的會更好
- **bug 修復**：建議升級
- **架構變動（主版本升級）**：看說明決定，可能需要手動調整

### Step 3：執行升級

```bash
git pull origin main
```

完成。你的 `workspace/` 沒有被動到。

### Step 4：要不要更新已有的系統？

升級框架之後，你已經生成的 OctoWork 不會自動更新。如果你想要：

**用新版生成器重新生成**（會覆蓋）：
```bash
# 先備份
cp -r workspace/my-OctoWork workspace/my-OctoWork-backup

# 重新生成
claude
> 幫我重新建一套 OctoWork
```

**手動挑選要更新的部分**：
看 CHANGELOG.md 裡提到改了哪些 Skill 或模板，手動複製你需要的。

## 版本號規則

OctoWork 用語義化版本：`主版本.次版本.修補版本`

| 版本類型 | 範例 | 意思 | 需要手動調整嗎 |
|----------|------|------|---------------|
| 修補 | 0.1.0 → 0.1.1 | 修錯字、小 bug | 不用 |
| 次版本 | 0.1.0 → 0.2.0 | 新範例、新功能 | 不用 |
| 主版本 | 0.x → 1.0.0 | 架構變動 | 可能需要，看說明 |
