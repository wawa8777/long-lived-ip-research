# Skill 02 執行驗收清單

## A. 專案與安全
- [ ] 確認正確網站、repo、分支、部署平台及 production URL
- [ ] 讀取 README／playbook、最新 commit、部署 workflow 與既有測試
- [ ] 判斷網站技術類型，不假設所有專案都是靜態 Pages
- [ ] 定義需求與可驗證的驗收標準
- [ ] 只修改必要檔案，檢查最終 diff
- [ ] 確認沒有提交 secrets、測試殘留或無關變更
- [ ] 確認未混用其他網站的內容、網址、資產或 Cloudflare 專案

## B. 新網站部署相容性（必做）
- [ ] 確認入口檔、build command 與輸出目錄正確
- [ ] 確認必要的 HTML、CSS、JS、圖片、字型及設定檔都已提交
- [ ] 確認 workflow 的 push paths 涵蓋本次變更檔案
- [ ] 確認 workflow 裡的網站網址、專案名稱、分支與資產清單沒有沿用錯站設定
- [ ] 確認實際部署機制：Git integration、Deploy Hook 或 Wrangler CI/CD
- [ ] 確認必要 secrets／環境變數的名稱與設定狀態，不輸出秘密值
- [ ] 若自動部署設定不相容，先修正專案專用流程或明確標記 BLOCKED；不可假定 push 就會上線

## C. 部署前品質閘門
- [ ] 語法／設定檢查
- [ ] 專案既有 build、lint、unit／integration tests（若存在）
- [ ] 內部連結、路由及資產路徑
- [ ] 關鍵圖片、字型、腳本與樣式存在
- [ ] 手機約 390px 與桌面版排版
- [ ] 檢查橫向溢出、重疊、裁切及可讀性
- [ ] 關鍵互動與瀏覽器 console／network（工具可用時）
- [ ] 無法執行的測試標記 NOT RUN 並說明原因
- [ ] 必要閘門通過後才部署 production

## D. Commit 與部署
- [ ] 記錄基準 commit、變更檔案及新 commit SHA
- [ ] 優先驗證 preview deployment，避免未驗收就直接影響 production
- [ ] 讀取實際 Actions job／step／log 或平台 deployment 狀態
- [ ] 區分 Deploy Hook 接受請求與部署真正完成
- [ ] 確認部署目標是本次正確網站，而非其他網站

## E. 正式網站驗收
- [ ] 正式網址回應成功，頁面包含本次預期內容
- [ ] 確認發布版本與目標 commit／deployment 相符（若可驗證）
- [ ] 關鍵本地資產回應成功，不只檢查 HTML
- [ ] 主要連結與路由指向預期目的地
- [ ] 真實瀏覽器檢查主要按鈕、選單、表單及核心流程（工具可用時）
- [ ] 手機版無橫向溢出、文字重疊或明顯裁切
- [ ] 檢查桌面版版面及可用性
- [ ] 檢查 console／network 錯誤（工具可用時）
- [ ] 修復後重跑失敗測試與相關回歸測試，再重新驗收

## F. 交付
- [ ] 提供 repo、正式網址、變更檔案、commit 與 Actions／deployment 連結
- [ ] 分開列出 PASSED、FAILED、NOT RUN、BLOCKED
- [ ] 說明正式網址驗收的具體證據與未測試項目
- [ ] 說明未解決問題及使用者需要採取的最小步驟
- [ ] 未完成完整驗收時，不使用 VERIFIED LIVE 或「全部成功」
