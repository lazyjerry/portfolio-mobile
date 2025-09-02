# GitHub Copilot 指令

## 專案概述

這是一個受版權保護的個人作品集網站（`index.html`），展示林書賢的專業經歷。網站採用單一檔案架構，整合 138 張專案截圖，具有現代玻璃擬態設計和互動式折疊專案區段。

**重要**：此專案採用嚴格版權保護（All Rights Reserved），僅供展示與評估用途。

## 架構與核心組件

### 核心結構

- **單一 HTML 檔案**：所有樣式、腳本和內容整合在 `index.html`，簡化部署
- **Screenshot 資料夾**：26 個專案資料夾，138 張截圖，使用相對路徑 `./screenshot/{專案名稱}/{檔名}`
- **Bootstrap 5.3.2 + Font Awesome 6.4.0**：透過 CDN 引入，無建置需求
- **語言**：繁體中文（`zh-TW`）為主，含英文技術術語
- **字體堆疊**：`"Helvetica Neue", "Helvetica", "Arial", "Microsoft JhengHei"` 確保跨平台中文顯示

### 專案截圖系統

```html
<!-- 截圖連結遵循固定格式 -->
<a
	href="./screenshot/{專案資料夾}/{圖片檔名}"
	target="_blank"
	rel="nofollow noopener"
>
	[截圖 1]
</a>
<a
	href="./screenshot/{專案資料夾}/{圖片檔名}"
	target="_blank"
	rel="nofollow noopener"
>
	[截圖 2]
</a>
```

**關鍵規則**：

- 截圖路徑必須使用 `./screenshot/` 開頭
- 連結文字格式：`[截圖 N]`，N 從 1 開始遞增
- 所有截圖連結使用 `target="_blank" rel="nofollow noopener"`

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

## 開發模式與關鍵實作

### 折疊動畫系統

折疊系統的 JavaScript 處理**必須**遵循以下模式：

```javascript
// 動態高度計算 - 絕不使用固定高度值
content.style.maxHeight = content.scrollHeight + "px";

// 按鈕狀態切換
button.classList.toggle("expanded");
content.classList.toggle("expanded");
```

### 專案卡片結構

所有專案必須遵循此確切的 HTML 模式：

```html
<div class="project-card">
	<div class="mb-3">
		<h3 class="project-title"><b>公司/專案名稱</b></h3>
		<span class="project-date">時間範圍</span>
	</div>
	<button
		class="project-toggle"
		onclick="toggleProject(this)"
	>
		<span>查看詳細資訊</span>
		<i class="fas fa-chevron-down"></i>
	</button>
	<div class="project-content [expanded]">
		<!-- 專案描述與截圖連結 -->
	</div>
</div>
```

### CSS 慣例

- **主色調**：`#007bff` 和 `#0056b3` 藍色系漸層
- **玻璃擬態**：`backdrop-filter: blur(10px)` + `rgba(255, 255, 255, 0.95)`
- **懸停動畫**：`transform: translateY(-3px)` + 陰影變化
- **響應式**：Bootstrap 網格搭配自定義 CSS

### 內容指導原則

- **專案分類**：官網、活動網站、系統平台
- **狀態標示**：已結束專案標記【已結束】
- **連結格式**：包含描述性文字 + 實際網址
- **無障礙設計**：`data-enable-grammarly="false"` 防止語法檢查衝突

## 開發工作流程

```bash
# 開發流程
1. 直接編輯 index.html
2. 瀏覽器預覽：open index.html 或 python3 -m http.server 8000
3. 截圖管理：新增至 screenshot/{專案名稱}/ 資料夾
4. 部署：將 index.html + screenshot/ 複製到網頁伺服器

# 專案截圖統計
find screenshot -name "*.png" -o -name "*.jpg" -o -name "*.PNG" | wc -l
ls -1 screenshot | wc -l
```

## 版權與授權

- **嚴格版權保護**：採用 "All Rights Reserved" 授權
- **用途限制**：僅供展示、評估、教育參考
- **禁止事項**：商業使用、複製、修改、重新分發
- **專案來源**：https://github.com/lazyjerry/portfolio-mobile

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
