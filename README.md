# 知微金口诀断课分析程序 — 網頁版

金口诀排盘、断课分析工具（公曆／農曆／干支輸入、月將晝夜、神煞、課鈐解讀、占斷結論、AI 斷課、五種格式導出）。
手機、平板、電腦打開網址即可使用，不需安裝。

## 線上網址

| 平台 | 網址 |
|---|---|
| GitHub Pages | https://hungpinoffice-afk.github.io/jinkoujue-web/ |
| WorkBuddy | https://jinkoujue-divination.app.workbuddy.host/ |

## 檔案說明

| 檔案 | 用途 |
|---|---|
| `index.html` | 網頁入口 |
| `assets/` | 程式碼（JavaScript） |
| `keqian.json.gz` | 課鈐解讀資料（1416 筆，必要） |
| `keqian.json` | 同上未壓縮備援版（舊瀏覽器才會用到） |
| `使用說明.txt` | 使用說明 |

`index.html`、`assets`、`keqian.json.gz` 必須同層，不可拆散或改名。

## 更新網站內容

```bash
cd C:\Users\win10\Desktop\金口訣
git add -A
git commit -m "更新說明"
git push
```

推送後 GitHub Pages 約 1 分鐘自動重新建置，網址不變。

## 技術說明

- 純前端 React 19 + Vite 8，靜態網站，無後端。
- 課鈐資料的 `rawAll` 欄位經逐筆驗證（1416 筆、0 筆不符）可由其他欄位精確還原，
  故不重複儲存，改為執行時即時組合。
- 資料改存 gzip 檔，啟動時以 `DecompressionStream('gzip')` 解壓，
  首屏載入量由約 17MB 降至約 1.6MB。
- 導出用的 xlsx / docx / pptxgenjs 改為按下「導出」時才動態載入。

原始桌面版專案未做任何修改。
