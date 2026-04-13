# 團隊導入指南

## 團隊使用 OctoWork 的三種模式

### 模式 A：各自獨立（最簡單）

每個人各自 clone OctoWork，在自己的 `workspace/` 裡建自己的 work-os。互不影響。

適合：5 人以下的小團隊，每個人的工作差異大。

### 模式 B：共享公司層 + 各自個人層

主管先建好「公司層」的檔案（company.md、products.md），發給團隊成員。每個人用生成器建自己的 CLAUDE.md（個人角色和原則）。

適合：10-20 人的團隊，公司資料需要統一。

做法：
1. 主管在 `workspace/company-shared/` 建好 company.md 和 products.md
2. 每個成員複製這兩個檔案到自己的 work-os
3. 各自建自己的 CLAUDE.md

### 模式 C：角色包制度

為每個職位建一個「角色包」，包含該職位的 Skills 和 Workflows。新人入職時，複製角色包 + 填個人資料就能上手。

適合：有標準化崗位的公司（連鎖門市、客服中心等）。

做法：
1. 在 `workspace/roles/` 建各角色包：
   ```
   workspace/roles/
   ├── store-manager/    ← 店長角色包
   ├── store-ops/        ← 營運專員角色包
   └── customer-service/ ← 客服角色包
   ```
2. 每個角色包含預設的 Skills 和 Workflows
3. 新人入職：`cp -r workspace/roles/store-manager workspace/小美的系統`
4. 小美修改 CLAUDE.md 填入自己的資料，開始使用

## Skill 的進化管理

當團隊成員改進了某個 Skill：

1. 成員在自己的版本裡修改，用了幾次確認有效
2. 跟主管或資深人員提出「這個 Skill 我改了 XXX，效果更好」
3. 主管決定要不要更新角色包裡的主版本
4. 如果更新，通知其他成員手動同步

這不需要 Git 流程——LINE 群說一聲、把新的 SKILL.md 丟到群裡就好。
