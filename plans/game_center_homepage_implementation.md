# 遊戲中心主頁實施計劃

## 項目概述
創建一個結合明亮/黑暗模式的遊戲中心主頁，整合三個現有遊戲的連結。

## 現有檔案分析

### 遊戲檔案
1. **`game1.html`** - 2048經典版
   - 完整遊戲功能
   - 響應式設計
   - 本地存儲分數

2. **`game2.html`** - 3D森林打獵遊戲
   - Three.js 3D遊戲
   - 射擊遊戲機制
   - 計分系統

3. **`game3.html`** - AR手部打地鼠
   - MediaPipe手部追蹤
   - AR互動遊戲
   - 現代化UI設計

### 主頁設計
1. **明亮模式設計** (`遊戲中心首頁_明亮模式/code.html`)
   - 現代簡潔設計
   - 卡片式佈局
   - 移動優先設計

2. **黑暗模式設計** (`遊戲中心首頁_黑暗模式/code.html`)
   - 科技感設計
   - 玻璃態效果
   - 漸變背景

## 技術規格

### 功能需求
1. **模式切換功能**
   - 明亮/黑暗模式切換
   - 本地存儲用戶偏好
   - 平滑過渡動畫

2. **遊戲卡片整合**
   - 三個遊戲的卡片展示
   - 點擊跳轉到對應遊戲
   - 遊戲資訊顯示（分數、評分）

3. **響應式設計**
   - 桌面端優化
   - 移動端適配
   - 平板電腦支援

4. **用戶體驗**
   - 加載動畫
   - 懸停效果
   - 視覺反饋

### 技術棧
- **HTML5** - 語義化標記
- **Tailwind CSS** - 樣式框架
- **JavaScript** - 交互功能
- **Google Fonts** - 字體
- **Material Icons** - 圖標

## 實施步驟

### 步驟1：創建主頁HTML結構
```html
<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <!-- 元標籤、標題、CSS、JS -->
</head>
<body class="light-mode">
    <!-- 漸變背景 -->
    <!-- 頁首區域 -->
    <!-- 歡迎區 -->
    <!-- 遊戲卡片區 -->
    <!-- 底部導航 -->
    <!-- JavaScript代碼 -->
</body>
</html>
```

### 步驟2：實現模式切換功能
```javascript
// 模式切換邏輯
const themeToggle = document.getElementById('theme-toggle');
const themeIcon = document.getElementById('theme-icon');
const themeText = document.getElementById('theme-text');

// 檢查本地存儲
const currentTheme = localStorage.getItem('theme') || 'light';

// 應用主題
function applyTheme(theme) {
    document.documentElement.classList.toggle('dark', theme === 'dark');
    themeIcon.textContent = theme === 'dark' ? 'light_mode' : 'dark_mode';
    themeText.textContent = theme === 'dark' ? '明亮模式' : '黑暗模式';
    localStorage.setItem('theme', theme);
}

// 切換主題
themeToggle.addEventListener('click', () => {
    const newTheme = document.documentElement.classList.contains('dark') ? 'light' : 'dark';
    applyTheme(newTheme);
});
```

### 步驟3：創建遊戲卡片組件
每個遊戲卡片包含：
- 遊戲圖標
- 遊戲標題
- 遊戲描述
- 最高分顯示
- 評分
- 開始按鈕（連結到遊戲）

### 步驟4：響應式設計實現
使用Tailwind CSS的響應式類：
- `grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3`
- 移動端單列，平板雙列，桌面三列
- 字體大小調整
- 間距優化

### 步驟5：視覺效果增強
1. **懸停效果** - 卡片懸浮、陰影變化
2. **漸變背景** - 動態漸變圓圈
3. **玻璃態效果** - 半透明背景
4. **過渡動畫** - 平滑狀態變化

## 檔案結構
```
遊戲中心主頁/
├── index.html              # 主頁檔案
├── game1.html              # 2048遊戲
├── game2.html              # 森林打獵遊戲
├── game3.html              # AR打地鼠遊戲
├── assets/                 # 資源檔案
│   ├── images/             # 圖片
│   └── icons/              # 圖標
└── plans/                  # 計劃文件
    └── game_center_homepage_implementation.md
```

## 測試計劃

### 功能測試
1. **模式切換測試**
   - 點擊切換按鈕
   - 檢查本地存儲
   - 驗證視覺變化

2. **遊戲連結測試**
   - 點擊每個遊戲的開始按鈕
   - 驗證正確跳轉
   - 返回主頁功能

3. **響應式測試**
   - 桌面瀏覽器測試
   - 移動設備測試
   - 不同屏幕尺寸測試

### 兼容性測試
- Chrome, Firefox, Safari
- iOS, Android
- 不同分辨率

## 部署指南

### 本地部署
1. 將所有檔案放在同一目錄
2. 使用本地服務器運行（如Live Server）
3. 訪問 `http://localhost:5500/index.html`

### 生產部署
1. 上傳到靜態網站託管（GitHub Pages, Netlify, Vercel）
2. 確保所有相對路徑正確
3. 測試所有功能

## 時間線
1. **設計階段** - 已完成
2. **開發階段** - 需要切換到Code模式實現
3. **測試階段** - 功能驗證
4. **部署階段** - 上線運行

## 注意事項
1. 確保遊戲檔案路徑正確
2. 測試所有外部資源（CDN）的可訪問性
3. 考慮性能優化（圖片壓縮、緩存）
4. 添加適當的錯誤處理

## 成功標準
1. 用戶可以無縫切換明亮/黑暗模式
2. 所有遊戲連結正常工作
3. 主頁在所有設備上顯示良好
4. 加載速度快，用戶體驗流暢
