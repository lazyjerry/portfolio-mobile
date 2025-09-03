# 林書賢 - 個人作品集

一個現代化的單頁面響應式作品集網站，展示軟體開發工程師的專業經歷與 138 個專案截圖。

線上預覽：https://profolio-mobile-250903.jlab-app.cloud

## 專案簡介

本作品集採用玻璃擬態設計風格，完全響應式佈局，展示個人的全端開發經歷。包含 26 個專案類別，涵蓋官網開發、活動網站、系統平台等多元化項目，搭配詳細的專案截圖與技術說明。

主要功能：

- 現代玻璃擬態設計，採用 backdrop-filter 與漸層效果
- 完全響應式佈局，適配桌面、平板、手機各種裝置
- 互動式折疊區段，具備平滑的展開收合動畫
- 中文字體優化，針對繁體中文排版調整
- 零建置需求，單一 HTML 檔案即可部署
- **AI Coding 實戰作品集**：涵蓋自動化文件產生、PDF 處理、SEO 分析、會議記錄、社群標籤管理等，並整合 Cloudflare Workers、Hono (TypeScript)、AI API、RAG 技術與多種 AI CLI 工具。

### 代表性 AI Coding 專案

- [Git 自動 Commit Message 工具](https://github.com/lazyjerry/git-auto-push)：一鍵自動化 Git add/commit/push，並可整合多種 AI CLI 工具自動生成語意化 commit message。
- [報價單產生器](https://github.com/lazyjerry/estimate-generator)
- [社群標籤 Chrome 擴充](https://github.com/lazyjerry/My-Notes-Extension)
- [瀏覽器尺寸檢測器](https://github.com/lazyjerry/screen-size-detector)
- [老媽整點叫你機器人](https://github.com/lazyjerry/telegram-reminder)
- [飲食紀錄工具](https://github.com/lazyjerry/diet-record)
- [勞務報酬單產生器](https://github.com/lazyjerry/taiwan-labor-receipt)

更多專案請見 index.html 作品集區塊。

## 系統結構

```
portfolio-mobile/
├── index.html                          # 主要檔案（HTML/CSS/JS 一體化）
├── screenshot/                         # 專案截圖資料夾（26 個專案，138 張圖片）
│   ├── Gwall 巨幄室內裝修設計-官方網站/
│   ├── TheJob/
│   ├── 西井科技/
│   ├── 當紅俱樂部/
│   └── ...（其他 22 個專案資料夾）
├── README.md                           # 專案說明文件
├── LICENSE                             # MIT 授權條款
└── .github/
    ├── copilot-instructions.md         # AI 開發助理指令
    └── instructions/
        └── copilot-readme.instructions.md
```

## 安裝與啟動

### 本地開發

```bash
git clone https://github.com/lazyjerry/portfolio-mobile.git
cd portfolio-mobile
```

### 本地預覽

```bash
# 直接用瀏覽器開啟
open index.html

# 或使用 Python HTTP 伺服器
python3 -m http.server 8000
```

瀏覽器開啟 `http://localhost:8000` 即可預覽。

### 部署

將 `index.html` 和 `screenshot/` 資料夾複製到任何靜態網頁伺服器即可完成部署。

## 技術架構

- **前端框架**: Bootstrap 5.3.2（透過 CDN）
- **圖示庫**: Font Awesome 6.4.0
- **字體堆疊**: Helvetica Neue, Helvetica, Arial, Microsoft JhengHei
- **動畫效果**: CSS3 transitions 搭配 JavaScript 動態高度計算
- **響應式設計**: Mobile-first 設計原則，支援所有裝置尺寸

## 核心組件

## 核心組件

### 個人資訊區塊

- 專業頭像與聯絡資訊
- 自我介紹與職業定位
- 社群媒體連結

### 技能展示區

- 6 個響應式技能卡片
- 技術能力分類展示
- 懸停互動效果與漸層背景

### 專案經歷區

- 時間軸式專案排版
- 26 個專案類別，138 張專案截圖
- 可折疊的詳細內容展示
- 動態高度計算的平滑動畫
- 多層級專案分類系統

### 互動功能

- JavaScript 驅動的折疊展開動畫
- 平滑的頁面載入動畫效果
- 按鈕狀態切換與視覺反饋

## 使用方法

### 常用指令

```bash
# 啟動本地開發伺服器
python3 -m http.server 8000

# 或使用 Node.js
npx http-server

# 或使用 PHP
php -S localhost:8000
```

### 專案截圖管理

所有專案截圖存放在 `screenshot/` 資料夾中，按專案名稱分類：

```bash
# 查看所有專案資料夾
ls -la screenshot/

# 統計截圖數量
find screenshot -name "*.png" -o -name "*.jpg" -o -name "*.PNG" | wc -l
```

## 使用情境

### 個人作品集展示

適合軟體工程師、前端開發者、全端開發者展示專業技能與專案經歷。

### 專案展示

每個專案都包含詳細說明與多張截圖，適合向客戶或雇主展示具體成果。

### 技能說明

透過視覺化的技能卡片，清楚展示技術能力與專業領域。

## 自訂指南

### 修改個人資訊

編輯 `index.html` 中的以下區段：

1. 個人基本資料（姓名、職稱、聯絡方式）
2. 自我介紹內容
3. 技能卡片的技術項目

### 新增專案

按照既有的 HTML 結構新增專案：

```html
<div class="project-card">
	<div class="mb-3">
		<h3 class="project-title"><b>專案名稱</b></h3>
		<span class="project-date">時間期間</span>
	</div>
	<button
		class="project-toggle"
		onclick="toggleProject(this)"
	>
		<span>查看詳細資訊</span>
		<i class="fas fa-chevron-down"></i>
	</button>
	<div class="project-content">
		<!-- 專案詳細內容與截圖連結 -->
	</div>
</div>
```

### 樣式自訂

所有 CSS 樣式都在 `<style>` 標籤內：

- 主色調：修改 `#007bff` 與 `#0056b3` 色值
- 字體設定：調整 `font-family` 屬性
- 動畫效果：修改 `transition` 與 `transform` 屬性
- 背景漸層：調整 `linear-gradient` 參數

## 錯誤排除

### 截圖無法顯示

檢查截圖檔案路徑是否正確：

```bash
# 檢查檔案是否存在
ls -la screenshot/專案名稱/

# 檢查檔案權限
chmod 644 screenshot/**/*.png
```

### 動畫效果異常

確認 JavaScript 功能正常運作：

1. 開啟瀏覽器開發者工具
2. 檢查 Console 是否有錯誤訊息
3. 確認 `toggleProject()` 函數可正常執行

### 響應式佈局問題

檢查 Bootstrap CSS 是否正確載入：

```html
<link
	href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css"
	rel="stylesheet"
/>
```

## 授權條款

本專案採用嚴格的版權保護條款，保留所有權利。詳細內容請參閱 [LICENSE](LICENSE) 檔案。

**重要提醒**：

- 本作品集僅供展示與評估用途
- 禁止商業使用或任何形式的複製、修改
- 如需使用相關內容，請先取得書面授權
- 專案來源：https://github.com/lazyjerry/portfolio-mobile

## 作者

**林書賢 (Jerry Lin)**

軟體開發工程師，專精於全端開發與專案管理。

---

更詳細的開發指導原則請參閱 [.github/copilot-instructions.md](.github/copilot-instructions.md)。
