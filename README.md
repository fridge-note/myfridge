# 我的冰箱 · My Fridge

繁體中文、手機優先的冰箱食材管理 PWA。無須建置、後端或 ChatGPT 訂閱。

## 功能

- 緊湊食材清單、分類及有效期限排序。
- 新增與編輯食材、購買日期、數量、常見或自訂單位。
- 有效期限選填；購買日期預設為新增當天。
- 數量加減，歸零移出冰箱，支援復原。
- 水果、蔬菜、蛋白質、乳製品、調味料、其他。
- 主畫面安裝與離線使用（首次須連線成功載入）。

## 發布到 GitHub Pages

1. 將此資料夾的變更提交並推送至 GitHub 的 `main` 分支。
2. 開啟儲存庫 **Settings → Pages**。
3. **Source** 選 **Deploy from a branch**。
4. **Branch** 選 `main`，資料夾選 `/ (root)`，按 **Save**。
5. 等 GitHub Pages 發布完成，使用 Pages 頁面顯示的網址。

目前儲存庫為 `fridge-note/myfridge`，預期網址為 `https://fridge-note.github.io/myfridge/`；啟用前尚未發布。

所有資源、manifest 與 Service Worker 都使用相對路徑，支援 `/myfridge/` 子路徑。`.nojekyll` 讓 Pages 直接提供靜態檔案。不要上傳 ChatGPT Sites 的 `.openai` 設定、部署封裝或其他儲存庫的 `.git`。

## 手機安裝

- iPhone：Safari 開啟網址 → 分享 → 加入主畫面。
- Android：Chrome 開啟網址 → 安裝應用程式／加入主畫面。

## 資料與搬移

食材資料儲存在使用者的瀏覽器 localStorage，不會上傳 GitHub，也不會跨裝置同步。清除網站資料會移除紀錄。

不同網址使用不同儲存空間。舊 ChatGPT Sites 網址的紀錄不會自動出現在 GitHub Pages；目前尚未提供匯出／匯入功能，請保留舊網址資料。搬到新網址後須重新加入主畫面。

## 本機檢查

使用 Node.js 執行 `node tests/verify.cjs`，驗證新增、編輯、數量調整、復原、日期、單位與資料保存。網站本身不需要 Node.js。

本機預覽需使用 HTTP 伺服器；直接雙擊 `index.html` 無法完整測試 PWA。正式 PWA 使用 HTTPS。
