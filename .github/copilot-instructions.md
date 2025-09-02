# GitHub Copilot 指令

## 專案概述

這是一個單頁面中文作品集網站（`index.html`），展示林書賢的專業經歷。網站採用現代玻璃擬態設計，具有響應式佈局和互動式可折疊專案區段。

## 架構與核心組件

### 核心結構

- **單一 HTML 檔案**：所有樣式、腳本和內容整合在一個檔案中，簡化部署
- **Bootstrap 5.3.2 + Font Awesome 6.4.0**：透過 CDN 引入外部依賴
- **語言**：繁體中文（`zh-TW`）含雙語元素
- **字體堆疊**：`"Helvetica Neue", "Helvetica", "Arial", "Microsoft JhengHei"` 確保跨平台中文支援

### 設計系統

```css
/* 主要 CSS 類別遵循一致命名規範 */
.skill-card         /* 三欄響應式技能網格 */
/* 三欄響應式技能網格 */
.project-card       /* 時間軸樣式專案容器 */
.project-toggle     /* 可折疊按鈕含旋轉動畫 */
.project-content; /* 高度動畫內容區域 */
```

### 互動組件

- **折疊區段**：使用 `toggleProject(button)` 函數搭配動態高度計算
- **動畫模式**：CSS 轉場 + JavaScript `scrollHeight` 實現平滑展開/收合
- **預設狀態**：部分區段預設展開（`.expanded` 類別）

## 開發模式

### CSS 慣例

- **漸層效果處處可見**：主要元素使用 `linear-gradient(45deg, #007bff, #0056b3)`
- **玻璃擬態**：`backdrop-filter: blur(10px)` + rgba 背景
- **懸停動畫**：`transform: translateY(-3px)` + 陰影變化
- **響應式設計**：Bootstrap 網格搭配自定義斷點

### JavaScript 模式

- **動態高度計算**：動畫時務必使用 `content.scrollHeight + 'px'`
- **DOM 就緒初始化**：為預設展開項目設定正確高度
- **按鈕狀態管理**：同時切換 `.expanded` 類別和文字內容

### 內容結構

```html
<!-- 專案遵循此確切模式 -->
<div class="project-card">
	<div class="mb-3">
		<h3 class="project-title"><b>公司名稱</b></h3>
		<span class="project-date">日期範圍</span>
	</div>
	<button
		class="project-toggle"
		onclick="toggleProject(this)"
	>
		<span>查看詳細資訊</span>
		<i class="fas fa-chevron-down"></i>
	</button>
	<div class="project-content [expanded]">
		<!-- 內容放這裡 -->
	</div>
</div>
```

## 關鍵實作細節

### 高度動畫系統

折疊系統需要特定的 JavaScript 處理：

```javascript
// 務必計算實際內容高度，絕不使用固定值
content.style.maxHeight = content.scrollHeight + "px";
```

### 多區段專案

最新專案（SOHO/伍壹柒數位）使用**一個卡片內多個獨立切換器**：

- 官網部分
- 活動網站部分
- 系統平台部分

### 字體與無障礙

- 中文優先字體堆疊正確處理繁體中文字元
- `data-enable-grammarly="false"` 防止與中文內容衝突
- 外部連結使用 `rel="nofollow noopener"` 安全模式

## 內容指導原則

- **專案類別**：官網、活動網站、系統平台
- **狀態指示器**：已完成專案標記【已結束】
- **連結模式**：包含描述性文字 + 實際網址
- **技術提及**：務必指定使用的框架/語言

## 快速開發指令

```bash
# 無建置流程 - 直接編輯檔案
# 查看變更：在瀏覽器中開啟 index.html
# 部署：將 index.html 複製到網頁伺服器
```
