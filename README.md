# 學校活動預約日曆（Web App）

單一前端網頁應用：多角色預約、學校／活動管理、時間衝突偵測、Excel 匯出。  
使用 Tailwind CSS（CDN）+ Vanilla JavaScript，可部署到 **GitHub Pages**，用手機或電腦開啟。

## 檔案說明

| 檔案 | 用途 |
|------|------|
| `index.html` | 主程式（HTML / CSS / JS） |
| `manifest.webmanifest` | 手機「加入主畫面」Web App 設定 |
| `icon.svg` | 網站與 App 圖示 |

## 本機預覽

用瀏覽器直接開啟 `index.html`，或在資料夾執行：

```bash
# Python
python -m http.server 8080

# Node
npx serve .
```

然後開啟 `http://localhost:8080`。

## 部署到 GitHub Pages（取得公開網址）

### 1. 建立 GitHub 儲存庫並上傳

在專案資料夾執行：

```bash
git init
git add index.html manifest.webmanifest icon.svg README.md .gitignore
git commit -m "Publish school booking calendar web app"
git branch -M main
git remote add origin https://github.com/你的帳號/booking-system.git
git push -u origin main
```

也可在 GitHub 網頁新建 Repository，再把這幾個檔案拖上去。

### 2. 開啟 GitHub Pages

1. 打開 GitHub 上的 Repository  
2. **Settings** → **Pages**  
3. **Source** 選 **Deploy from a branch**  
4. Branch 選 `main`，資料夾選 `/ (root)`  
5. 按 **Save**

約 1–2 分鐘後會出現網址，例如：

```text
https://你的帳號.github.io/booking-system/
```

把這個網址分享給其他人，用手機或電腦瀏覽器即可開啟。

### 3. 手機當 Web App 使用

- **iPhone（Safari）**：開啟網址 → 分享 →「加入主畫面」  
- **Android（Chrome）**：開啟網址 → 選單 →「安裝應用程式」或「加入主畫面」

加入後會以全螢幕 App 風格開啟。

## 注意：資料儲存方式

目前資料存在每位使用者瀏覽器的 **LocalStorage**。

| 情況 | 結果 |
|------|------|
| 同一部手機／電腦再開 | 可看到自己之前的預約 |
| 其他人用你分享的網址 | 可以使用同一個 App |
| 不同裝置之間 | **不會**自動同步同一批預約資料 |

若之後要「大家共用同一份雲端資料」，需要再接 Supabase／Firebase 等後端，並改寫儲存邏輯。

## 功能摘要

- 使用者／Admin 角色切換、新增與改名  
- 學校與活動總覽、編輯  
- 月曆預約、時間衝突防呆  
- 本機自動儲存  
- 匯出 Excel 報表  
