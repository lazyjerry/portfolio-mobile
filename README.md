# 林書賢 - 個人作品集

一個現代化的單頁面響應式作品集網站，展示軟體開發工程師的專業經歷與技能。

## ✨ 特色功能

- 🎨 **現代玻璃擬態設計**：採用 backdrop-filter 與漸層效果
- 📱 **完全響應式**：適配桌面、平板、手機各種裝置
- 🎯 **互動式折疊區段**：平滑的展開/收合動畫效果
- 🌐 **中文優化**：針對繁體中文字體與排版優化
- ⚡ **零建置需求**：單一 HTML 檔案，開箱即用

## 🚀 快速開始

### 本地預覽

```bash
# 直接用瀏覽器開啟
open index.html

# 或使用簡單的 HTTP 伺服器
python3 -m http.server 8000
# 然後開啟 http://localhost:8000
```

### 部署

將 `index.html` 複製到任何網頁伺服器即可完成部署。

## 🛠 技術架構

- **前端框架**: Bootstrap 5.3.2
- **圖示庫**: Font Awesome 6.4.0
- **字體**: 跨平台中文字體堆疊
- **動畫**: CSS3 transitions + JavaScript
- **響應式**: Mobile-first 設計原則

## 📂 專案結構

```
.
├── index.html              # 主要檔案（包含所有 HTML/CSS/JS）
├── README.md              # 專案說明
└── .github/
    └── copilot-instructions.md  # AI 開發助理指令
```

## 🎯 核心組件

### 技能展示區

- 6 個響應式技能卡片
- 分類展示技術能力
- 懸停互動效果

### 專案經歷區

- 時間軸式排版
- 可折疊的詳細內容
- 多層級專案分類系統

### 互動功能

- 動態高度計算的折疊動畫
- 平滑的頁面載入動畫
- 直觀的按鈕狀態反饋

## 🔧 自訂指南

### 修改內容

1. 編輯 `index.html` 中的個人資訊
2. 更新技能卡片的內容
3. 新增或修改專案經歷

### 樣式調整

所有 CSS 都在 `<style>` 標籤中：

- 主色調：修改 `#007bff` 相關的顏色值
- 字體：調整 `font-family` 設定
- 動畫：修改 `transition` 和 `transform` 屬性

### 新增專案

按照既有的 HTML 結構模式新增：

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
		<!-- 專案詳細內容 -->
	</div>
</div>
```

## 📝 授權條款

本專案採用 MIT 授權條款。

## 👤 作者

**林書賢 (Jerry Lin)**

- 軟體開發工程師
- 全端開發 | 專案管理

---

💡 **提示**: 查看 `.github/copilot-instructions.md` 了解更詳細的開發指導原則。
