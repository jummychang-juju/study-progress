# study-progress

國中段考讀書進度表，單一檔案的純前端網頁。

## 專案結構

整個 app 就是 `index.html` 一個檔案：HTML、CSS、JS 全部內嵌，沒有 build、沒有相依套件、沒有 service worker。資料存在瀏覽器的 localStorage，沒有後端。

改完直接用瀏覽器開 `index.html` 就能測。

## 部署（重要）

網站是 https://jummychang-juju.github.io/study-progress/ ，GitHub Pages 從 `main` 分支的根目錄發布。

**只要推上 `main`，Pages 就會自動重新部署**（約 1～2 分鐘），不需要任何 workflow 或手動步驟。改動沒進 `main` 的話，線上就不會變。

使用者已明確授權：**這個專案的改動可以直接 commit + push 到 `main`，不用先開 PR、也不用每次再問一次。** 需要開 PR 時再開就好。

## 常見改動位置

- **科目清單**：`ORDER`（顯示順序）和 `GROUP`（主科／自然／社會分組）兩個常數，改科目時兩個都要改。
- **舊資料相容**：`normalize()` 會把 `ORDER` 裡缺少的科目補進使用者既有的資料，並插在預設順序的鄰位；使用者自己調過的科目順序會保留。新增科目時要確認舊 localStorage 資料開起來不會壞。
- **說明頁範例表**：頁面下方「一份填好的範例」表格，新增科目時順手補一列。

## 慣例

介面文字、註解、commit message 都用繁體中文。
