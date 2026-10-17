# 部署 Skill 02：與原版比較

## 原版（基準）
- 原版操作手冊：`NEW_SITE_PLAYBOOK.md`
- 原版 starter：`site-starter/`
- 原版部署工作流：`.github/workflows/deploy-cloudflare-pages.yml`

原版重點是新網站建立、Cloudflare Pages 設定、Deploy Hook、基本正式網址驗證與操作口令。

## Skill 02（平行實驗版）
- 入口：`deployment-skill-02/SKILL.md`
- 驗收清單：`deployment-skill-02/ACCEPTANCE-CHECKLIST.md`

在原有規範上加強：
- 從需求到正式網址驗收的端到端閉環。
- 每次新網站都檢查部署 workflow 是否涵蓋變更檔案。
- 防止沿用錯誤網站的硬編碼網址、專案名稱、分支與資產清單。
- 區分 Git push、Deploy Hook 接受、平台部署完成與 live site 驗收。
- 優先 preview，再 production；部署後實際驗證 HTML、資產、互動與手機／桌面版。
- 失敗時根據日誌分類、修復、重跑測試並再次驗收。
- 用 VERIFIED LIVE、DEPLOYED — SITE CHECK PENDING 等狀態避免模糊報喜。
- 保留原版、保護 secrets、避免未授權付費或不可逆操作。

## 比較與驗證規則
1. 原版仍是基準；Skill 02 是獨立新增的平行版本。
2. 不要自動將 Skill 02 合併回原版。
3. 「部署skill」指定原版；「部署skill02」指定 Skill 02。
4. 不因規格更完整就直接宣稱可靠性更高；必須透過真實新網站測試，記錄失敗率、測試覆蓋、使用者介入次數及從提交到正式驗收的完整證據。
5. 本資料夾是可讀規格與版本封裝，並不自動成為所有 ChatGPT 對話都會載入的全域 Skill；需由執行環境支援並安裝才會自動載入。
6. 本次優化是規格與驗收流程更新，不等於已經用全新網站完成端到端實測；在完成實測前不得宣稱「保證無阻自動部署」。
