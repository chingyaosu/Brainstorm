# Brainstorm — 想法收集 / 產品規劃 / 產品開發

## 對話開始時請先讀
進度與最近更動都在 Obsidian：`/Users/yao/My Drive/Obsidian/Brainstorm/Work Progress.md`

## 工作模式
- **加新專案**：對 Claude 說「Brainstorm - <專案名>」→ Claude 會建 `/Project/<專案名>/` 子資料夾、引導規劃
- **結束工作**：對 Claude 說「**收工**」→ 對**所有有變更的 sub-project repo** 執行以下動作：
  1. `git add` + `git commit` + `git push`（各 sub-project 獨立 repo，如 Protein-Manufacturing、Mineral-Face-Cream 等）
  2. 更新各 sub-project 對應的 Obsidian Work Progress（`Obsidian/Brainstorm/<ProjectName>/Work Progress.md`）
  3. 若 Brainstorm 主 repo 本身也有變更，一併 commit + push
- **接續工作**：對 Claude 說「**開工**」→ 讀 Work Progress、報告 git 狀態、建議下一步

## 工作桌 + 三個家
- 📋 GDrive 工作桌：`/Users/yao/My Drive/Brainstorm/`（自動跨電腦同步）
- 🐙 GitHub repo：`chingyaosu/Brainstorm`（公開，網頁的家）
- 📘 Obsidian：`Obsidian/Brainstorm/Work Progress.md`（進度與想法）

## 專案清單
（之後加新專案時會自動更新）
- **Mione**（Mineral Face Cream）：自有品牌礦物保濕面霜（無防曬），目標市場美國 → `Project/Mineral-Face-Cream/`
- **HER2-CDx**：CTC 液態切片 HER2 伴隨診斷平台，LDT 方法驗證 → `Project/HER2-CDx/`

## 工作注意事項
- commit 訊息要寫清楚做了什麼 + 為什麼
- 收工前說「收工」讓 Claude 同步三方
- `.claude/` 永遠不要 commit（已加進 .gitignore）
