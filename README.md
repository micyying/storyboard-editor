# Storyboard Editor

給導演自己使用的 Storyboard／Shotlist 工具。直接改字、放多張 Ref、按 Take 記錄多機 coverage，最後打印成 PDF。無需安裝或登入。

## 功能

- 匯入 DOCX、文字版 PDF、TXT／Markdown／Fountain，或貼上劇本，依本機規則產生可編輯分鏡。
- Pages 只支援包含 PDF 預覽的封裝；其他 Pages／舊 DOC 請先匯出 DOCX 或 PDF。掃描 PDF 尚不支援 OCR。
- Cam 可選對白 Coverage／特別鏡頭；包含景別、Take、機位 checklist、movement、angle、打光／效果。
- Shot 及參考圖拖動排序、鏡號自動更新、Undo／Redo；Scene 刪除前確認。
- Ref 支援多張照片、圖片備註及看景地點分組；支援本機 HEIC 轉換。
- Shot Order 可新增行；Props／Location 在同一欄。
- A4 橫向打印，列印時隱藏操作按鈕及空白欄位提示。

## 保存與換裝置

工程自動保存於目前瀏覽器的 IndexedDB，容量允許時也保留 localStorage 備用記錄。清除網站資料、無痕模式或更換瀏覽器，可能無法取回。離開欄位或頁面時會補存待保存的修改。

「Save HTML」可保存含圖片、文字、Shot Order 及編輯功能的完整檔案；Cmd／Ctrl + S 也可呼叫。支援位置選擇的瀏覽器會開啟儲存視窗；其他瀏覽器使用分享選單或下載。

「匯出工程備份 · JSON」保存工程資料與圖片，不包含程式碼。把 JSON 或 HTML 放到 iCloud Drive，在另一台裝置開本工具，選「載入工程 · HTML / JSON」即可繼續。GitHub Pages 不提供自動雲端同步；兩台裝置同時修改後不會自動合併，請用最新備份接續。

本機 HTML 與 GitHub Pages 網址的瀏覽器儲存空間不同。第一次轉到網頁版，請先從舊版 Save HTML，再在網頁版載入；不要重新匯入原劇本覆蓋已做好的分鏡。

## 資料與相依套件

公開版本只包含空白工具。劇本、照片和備份在使用者裝置處理，不會提交到 GitHub，亦沒有分析追蹤程式或 API 金鑰。目前自動分鏡使用規則，未連接 AI 服務。

首次使用部分格式時需要網絡載入下列固定版本套件。套件在瀏覽器執行，文件內容不會作為上傳請求送出：

- Mammoth 1.13.0：DOCX 文字解析（unpkg）。
- PDF.js 6.4.299：PDF 文字解析（jsDelivr）。
- JSZip 3.10.1：Pages 封裝讀取（jsDelivr）。
- heic-to 1.5.2：HEIC 轉換的備用解析器（jsDelivr）。

## 發佈

這是可直接放在 GitHub Pages 的靜態網站。將本目錄作為倉庫根目錄，在 Pages 設定選擇從 `main` 的根目錄發佈。`index.html` 是最新版本；`v/0.32/` 是目前的版本留存連結。

日常固定入口為 https://micyying.github.io/storyboard-editor/ 。每次發佈只更新該入口的工具程式，沿用相同的 IndexedDB 資料庫、工程儲存鍵及備用記錄，不用重新填分鏡。`v/0.31/` 只作版本留存，日常請收藏不含版本號的入口。工程儲存格式日後若有變更，必須先提供相容轉換，不得以空白範本覆蓋舊記錄。

v0.31：空白初始工程、JSON 備份／載入、參考圖刪除 Undo、離開欄位立即保存、中文輸入法處理、Cmd／Ctrl + S、窄屏選單改善，以及打印空白區域壓縮。舊版本和既有本機記錄可繼續保留。

v0.32：Shot Order 移至 Ref 上方；已儲存或載入的舊工程也會套用這個排列，保留所有內容。
