# tablelization.com

手作 / 工藝作品集網站。純 HTML + CSS + JS，沒有建置工具，適合直接放上 GitHub Pages。

## 檔案結構

```
index.html         首頁（近期作品 + Instagram 連結）
portfolio.html      作品集總覽
about.html          關於／個人簡介
contact.html        聯絡方式
eggzine.html        蛋誌 — 過往期數列表
egg_child.html       蛋誌第 01 期內頁（QR code 指向的網址：/egg_child）
egg_child/index.html 備援跳轉頁（見下方說明）
css/style.css        全站樣式
js/main.js           捲動浮現效果
CNAME                GitHub Pages 自訂網域設定
```

## 部署到 GitHub Pages（連到 tablelization.com）

1. 在 GitHub 建立一個新 repository（例如 `tablelization`），把這個資料夾內所有檔案上傳 / push 上去。
2. Repository → **Settings → Pages**：
   - Source 選擇 `Deploy from a branch`
   - Branch 選 `main`（或你的預設分支），資料夾選 `/ (root)`
   - 儲存後，GitHub 會給你一個 `xxx.github.io` 網址，先確認能開啟。
3. **接自訂網域**：
   - `CNAME` 檔案裡已經寫好 `tablelization.com`，GitHub 會自動讀取。
   - 到你的網域註冊商（買 tablelization.com 的地方）設定 DNS：
     - 加一筆 `A` record 指向 GitHub Pages 的 IP（185.199.108.153 / .109.153 / .110.153 / .111.153），或
     - 如果用 `www` 子網域，加一筆 `CNAME` record 指向 `你的帳號.github.io`
   - 在 Settings → Pages 的 Custom domain 欄位填入 `tablelization.com`，並勾選 **Enforce HTTPS**（DNS 生效後才能勾）。
4. 等待 DNS 生效（通常幾分鐘到幾小時），之後 `https://tablelization.com` 就會是這個網站。

## 關於 /egg_child 這個網址（QR code 已生成）

`egg_child.html` 這個檔案就是 QR code 指向的內容。GitHub Pages 預設會把「不帶副檔名的網址」自動對應到同名的 `.html` 檔案，所以：

- `https://tablelization.com/egg_child` → 會直接顯示 `egg_child.html` 的內容，**不需要**額外設定。

保險起見，也附上了 `egg_child/index.html` 作為備援：如果將來換了其他主機、而該主機要求資料夾式網址（`/egg_child/`），會自動跳轉到 `egg_child.html`。日常編輯內容只需要改 `egg_child.html` 這一個檔案即可，不用管備援檔。

**建議部署後務必實際掃一次 QR code，確認能正確打開頁面。**

## 之後要換的內容（標示 【】 的地方）

- 所有 `.ph`（灰色色塊）都是圖片佔位，換成 `<img src="圖片路徑" alt="...">` 即可。
- `index.html`、`contact.html`、`egg_child.html` 裡的 Instagram / YouTube / Email / WhatsApp 連結，記得換成你自己的帳號網址。
- `about.html` 裡的自我介紹文字、擅長媒材列表。
- `egg_child.html` 裡的 YouTube 影片嵌入連結（`iframe` 的 `src`，換成你自己影片的 embed 網址）。

## 新增一期蛋誌

1. 複製 `egg_child.html`，重新命名（例如 `egg-002.html`），把內容換成新一期的作品。
2. 在 `eggzine.html` 的期數列表裡，照範本複製一個 `<a class="issue-item">` 區塊，連結指到新檔案。
3. 如果想讓新一期出現在首頁「近期作品」，也在 `index.html` 的作品格線裡加一張卡片。
