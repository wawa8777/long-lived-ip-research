# 新網站對話式建置流程

目標：讓網站需求、開發、版本管理、部署與驗收盡可能透過 ChatGPT 對話完成；只在帳號授權、付款、網域等必要環節請使用者操作。

## 新專案標準流程

1. **確認需求**：網站目的、頁面、內容、語言、視覺方向、互動、表單／資料庫／登入需求。
2. **建立 GitHub repository**：每個網站使用獨立 repository，避免互相影響。確認 GitHub 授權連線有建立 repo 的權限；若目前連線不支援建立 repository，請使用者建立空 repo 一次。
3. **建立網站檔案**：以 `site-starter/` 作為靜態網站起點；依需求加入資產、元件、測試與說明。
4. **設定 Cloudflare Pages**：將新 repository 連接至 Pages，選擇 production branch `main`。純 HTML/CSS/JS 通常不需要 build command，輸出目錄依專案結構設定。
5. **設定自動部署 hook**：在 Cloudflare Pages 專案設定建立指向 `main` 的 Deploy Hook；在 GitHub repository Actions secrets 新增 `CLOUDFLARE_PAGES_DEPLOY_HOOK`。不要把 hook URL 或 token 放進程式碼、issue 或聊天訊息。
6. **設定網站網址**：在 GitHub Actions Variables 新增 `SITE_URL`，值為正式 HTTPS 網址。若未設定自訂網域，先使用 Cloudflare 提供的 `pages.dev` 網址。
7. **測試**：檢查首頁 HTTP 回應、重要文字、內部連結、圖片回應、手機 390px 與桌面寬度、水平溢位及瀏覽器錯誤（若有可用瀏覽器測試環境）。
8. **發布與回報**：提供 GitHub commit、Actions run、正式網址與測試結果；明確標示未驗證項目。
9. **日後更新**：使用者在對話提出修改 → 修改 repository → GitHub Actions 執行測試 → Deploy Hook 觸發 Pages → 驗證正式網站。

## 自動部署 workflow 必要設定

Repository secrets：
- `CLOUDFLARE_PAGES_DEPLOY_HOOK`：Cloudflare Pages Deploy Hook URL。

Repository variables：
- `SITE_URL`：正式網站網址，例如 `https://example.pages.dev`。

Workflow 範本：`site-starter/.github/workflows/deploy-cloudflare-pages.yml`。

## 安全與品質規則

- 不要求使用者在聊天中貼上密碼、API token、Deploy Hook URL 或付款資料。
- 不因為 workflow 被觸發就宣稱部署成功；必須讀取實際 job 結果。
- 不因為 HTML 回應 200 就宣稱所有功能正常；表單、登入、資料庫與金流需獨立測試。
- 不擅自購買網域、開啟付費服務或建立有費用的資源。
- 對正式網站的破壞性修改先保留版本／備份；失敗時提供回復方案。
- 不把目前研究網站的專屬內容或資產直接複製到其他品牌網站。
