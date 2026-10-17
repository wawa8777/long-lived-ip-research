# 部署 Skill 02：與原版比較

## 原版（基準）

原版操作手冊：`NEW_SITE_PLAYBOOK.md`  
原版 starter：`site-starter/`  
原版部署工作流：`.github/workflows/deploy-cloudflare-pages.yml`

原版重點是新網站建立、Cloudflare Pages 設定、Deploy Hook、基本正式網址驗證與操作口令。

## Skill 02（平行版本）

入口：`deployment-skill-02/SKILL.md`

新增或強化：
- 專案辨識、技術架構與部署模式檢查。
- 修改前定義驗收標準、保留原有行為。
- 修改差異檢查與最小變更原則。
- 按專案情況執行建置、測試、連結、圖片、響應式與瀏覽器驗收。
- 將 PASSED / FAILED / NOT RUN / BLOCKED 分開回報。
- 區分 Deploy Hook 已接受請求與正式部署已完成。
- 失敗診斷、有限度修復、重跑測試與安全回滾評估。
- 交付 commit、Actions 證據、正式網站驗證與未完成事項。
- 明確規定不覆蓋原版、不要求使用者在聊天貼出秘密、不擅自執行付費或不可逆操作。

## 比較規則

1. 原版仍是基準；Skill 02 是獨立新增的實驗版本。
2. 不要將 Skill 02 的規則自動合併回原版。
3. 使用者可分別說「部署skill」或「部署skill02」指定版本。
4. 在完成真實專案任務後，依實際證據比較完成度、失敗處理、測試覆蓋率與使用者介入次數；不可只因規格更長就宣稱 Skill 02 更好。
5. 此資料夾是 Skill 的可讀規格/封裝起點。若要在其他執行環境自動載入，仍須將其安裝到該環境支援的 Skills 目錄或系統。
