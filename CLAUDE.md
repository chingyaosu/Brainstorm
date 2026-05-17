# Brainstorm — 產品開發總專案

## 對話開始時請先讀
- 總覽索引：`/Users/yao/My Drive/Obsidian/Brainstorm/Work Progress.md`
- 各產品進度：`/Users/yao/My Drive/Obsidian/Brainstorm/<產品名>/Work Progress.md`

## 工作模式
- **加新產品**：對 Claude 說「Brainstorm - ideal」→ Claude 會建 `Project/<ideal>/` 子資料夾 + `Obsidian/Brainstorm/<ideal>/Work Progress.md`，引導做
- **結束工作**：對 Claude 說「**收工**」→ 依序執行：
  1. 更新 Obsidian Work Progress（本次變更摘要 + 更動紀錄）
  2. 重新產生 `mione-roadmap.html`（根據最新進度更新所有內容）
  3. commit + push 到 main（HTML 必須推到 main，GitHub Pages 才會更新）
  4. 確認 https://chingyaosu.github.io/Brainstorm/mione-roadmap.html 已更新
- **接續工作**：對 Claude 說「**開工**」→ 讀對應產品的 Work Progress、報告 git 狀態、建議下一步

## 工作桌 + 三個家
- 📋 GDrive 工作桌：`/Users/yao/My Drive/Brainstorm/`（自動跨電腦同步）
- 🐙 GitHub repo：`chingyaosu/Brainstorm`（公開，網頁的家）
- 📘 Obsidian：`Obsidian/Brainstorm/<產品名>/Work Progress.md`（各產品獨立進度）

## 產品清單
（之後加新產品時會自動更新）
- **Mione**（Mineral Face Cream）：自有品牌礦物保濕面霜（無防曬），目標市場美國，概念階段 → `Project/Mineral-Face-Cream/`

## 工作注意事項
- commit 訊息要寫清楚做了什麼 + 為什麼
- 收工前說「收工」讓 Claude 同步三方
- `.claude/` 永遠不要 commit（已加進 .gitignore）
