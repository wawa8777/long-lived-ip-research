# 對話式新網站 Starter

這是可複製到新 GitHub repository 的簡單靜態網站起點。它不是完整 CMS，也不包含會員、資料庫或金流。

## 內容

- `index.html`：響應式單頁起點。
- `.github/workflows/deploy-cloudflare-pages.yml`：測試並呼叫 Cloudflare Pages Deploy Hook 的通用 workflow。

## 第一次設定

1. 將本資料夾內的內容複製到新 repository 根目錄。
2. 在 Cloudflare Pages 將該 repository 連接到專案，production branch 設為 `main`。
3. 建立 Cloudflare Pages Deploy Hook，分支選 `main`。
4. 在 GitHub repository Settings → Secrets and variables → Actions 新增：
   - Secret：`CLOUDFLARE_PAGES_DEPLOY_HOOK`
   - Variable：`SITE_URL`，例如 `https://your-project.pages.dev`
5. 提交到 `main`，到 Actions 確認測試與部署結果。

如果 Cloudflare Pages 已直接連接 GitHub 並啟用自動部署，通常不必再用 Deploy Hook；避免重複部署時可移除 hook 步驟，改以 Pages 原生部署狀態驗證。
