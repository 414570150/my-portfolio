# my-portfolio
my portfolio
# 🌟 徐薇薇個人履歷與作品集網站

## 專案介紹
這是一個採用純 HTML 和 CSS 建立的個人履歷/作品集網站，用於展示我的學術背景、工作經驗、技能與專案成果。

## 專案部署
- **GitHub 儲存庫：** https://github.com/414570150/my-portfolio.git
- **網站實際部署：** https://414570150.github.io/my-portfolio/

---

## 🛠️ Git 操作與流程展示 (核心作業要求)

### 1. 分支管理與獨立開發
本專案使用了三個開發分支，所有功能皆獨立開發後，透過 Pull Request 合併至 `main` 主分支。

| 開發分支 | 目的 | 狀態 |
| :--- | :--- | :--- |
| `feature/experience-section` | 實作「工作與學習經歷」區塊。 | 已合併至 `main` (PR #1) |
| `feature/skills-bars` | 實作「我的技能」區塊的 A 版 (進度條)。 | **誤合併後被 Revert** (PR #2) |
| `feature/skills-tags` | 實作「我的技能」區塊的 B 版 (標籤雲)。 | **已採納**並合併至 `main` (PR #3) |

### 2. A/B 實驗決策
針對「我的技能」區塊，進行了 A/B 實驗，原本應二擇一合併。

* **最終決策：** 採用 **方案 B (標籤雲)**。
* **顯示內容：** 由於 PR #3 是最後合併的，網站最終顯示為 B 版。

### 3. `git revert` 錯誤回復證明
為展示 Git 錯誤處理能力，我在誤合併了 PR #2 (A 版進度條) 之後，立即執行了回復操作：

* **錯誤操作 Commit：** `Merge pull request #2` (Commit ID: d2331a29d830add93238e76c5f808af5dd781e40)
* **回復指令：** `git revert -m 1 d2331a29d830add93238e76c5f808af5dd781e40`
* **結果：** 成功在 Git 歷史中留下 Revert Commit，將不必要的 A 版進度條程式碼變更從 `main` 分支中移除。這確保了網站最終只保留 B 版的設計。