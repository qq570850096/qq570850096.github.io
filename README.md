# 清晏小站 v2.0

一個古風雅致的互動站點，包含寄語心語、錦書長信和節日賀卡三大核心功能模塊。

## ✨ 功能特色

### 🔐 密碼驗證
- 使用密碼 `0214` 解鎖網站
- 優雅的驗證動畫效果
- Session 持久化，刷新頁面無需重複輸入

### 🏠 轩窗（隨機寄語）
- 隨機展示古詩詞寄語
- 點擊「換一句」按鈕刷新內容
- 顯示出處和日期信息
- 包含 8 條精選師恩相關詩詞

### 📜 錦書（長信信箱）
- 信件列表按日期倒序展示
- 點擊查看完整信件內容
- **竭排版顯示**（`writing-mode: vertical-rl`），從右向左閱讀
- 支持 Markdown 格式渲染
- 上一封/下一封翻頁導航
- 移動端自動切換為橫排版

### 🎁 百寶閣（節日賀卡）
- 網格展示多張節日賀卡
- **3D 翻轉動畫效果**（點擊卡片翻轉）
- 根據節日主題區分配色（竹青、朱紅、月白）
- 包含教師節、中秋節、春節賀卡

## 🎨 視覺設計

### 配色方案
- 主色：大地色系 `#8c6b5d`、`#5c4033`
- 輔色：朱紅 `#c8372d`、竹青 `#5a8776`、月白 `#f5e6d3`
- 背景：宣紙質感漸變

### 字體
- 標題/書法：**Ma Shan Zheng**（馬善政楷書）
- 正文：**Noto Serif TC**（思源宋體繁體）
- 全站使用繁體中文

### 動畫效果
- 密碼錯誤抖動動畫
- Tab 切換淡入淡出效果
- 卡片翻轉 3D 動畫
- 懸停交互反饋

## 🛠️ 技術棧

- **原生 HTML5 / CSS3 / JavaScript (ES6+)**
- **Marked.js**：Markdown 解析
- **Google Fonts**：中文字體加載
- **靜態部署**：適用於 GitHub Pages

## 📁 目錄結構

```
/
├── index.html              # 核心入口文件（包含所有邏輯）
├── README.md               # 項目說明文檔
├── prd.md                  # 產品需求文檔
└── data/                   # 數據存儲目錄
    ├── messages.json       # 寄語數據（8 條）
    ├── cards.json          # 賀卡數據（3 張）
    ├── letters_index.json  # 信件索引
    └── letters/            # Markdown 信件文件夾
        └── 2025-09-10-chulin.md
```

## 🚀 快速開始

### 本地運行

由於使用了 `fetch` API 加載 JSON 數據，需要通過 HTTP 服務器運行：

```bash
# 使用 Python 3
python -m http.server 8000

# 或使用 Node.js 的 http-server
npx http-server -p 8000
```

然後訪問 `http://localhost:8000`

### GitHub Pages 部署

1. 將項目推送到 GitHub 倉庫
2. 進入倉庫設置 → Pages
3. Source 選擇 `main` 分支
4. 保存後等待部署完成

## 📝 數據維護

### 添加新寄語

編輯 [data/messages.json](data/messages.json)：

```json
{
  "content": "您的寄語內容",
  "author": "出處或作者",
  "date": "2025-09-10"
}
```

### 添加新信件

1. 在 `data/letters/` 創建 Markdown 文件（如 `2025-10-01-title.md`）
2. 在 [data/letters_index.json](data/letters_index.json) 添加索引：

```json
{
  "id": "2025-10-01-title",
  "title": "信件標題",
  "date": "2025-10-01",
  "file": "data/letters/2025-10-01-title.md",
  "preview": "信件摘要..."
}
```

### 添加新賀卡

編輯 [data/cards.json](data/cards.json)：

```json
{
  "id": "card-festival-year",
  "title": "賀卡標題",
  "festival": "節日名稱",
  "date": "2025-12-25",
  "style": "bamboo",  // 可選：bamboo, red, moon
  "content": "賀卡祝福內容"
}
```

## 🎯 核心功能實現

### 密碼驗證
- 密碼：`0214`
- 使用 `sessionStorage` 記住驗證狀態
- 密碼錯誤時觸發抖動動畫

### Tab 切換
- 使用 CSS `opacity` 實現淡入淡出
- 使用 `position: absolute` 實現面板切換
- 點擊導航項切換當前活動 Tab

### 數據加載
- 使用 `fetch` API 異步加載 JSON 數據
- `Promise.all` 並行加載所有數據
- 錯誤處理和降級顯示

### 竪排版實現
- CSS `writing-mode: vertical-rl`
- `text-orientation: upright`
- `direction: rtl` 實現從右向左閱讀
- 移動端響應式切換為橫排版

### 3D 卡片翻轉
- CSS `perspective` 和 `transform-style: preserve-3d`
- `backface-visibility: hidden` 隱藏背面
- `transform: rotateY(180deg)` 實現翻轉

## 📱 響應式設計

- 移動端自動調整字體大小
- 信件竪排版在移動端切換為橫排版
- 卡片網格在移動端變為單列
- 導航欄自動換行適配小屏幕

## 🔒 密碼

默認密碼：**0214**

可在 [index.html:708](index.html#L708) 修改驗證邏輯。

## 📄 許可

本項目為個人祝福網站，供學習和參考使用。

## 👨‍💻 作者

清晏小站 v2.0 - 2025

---

**祝使用愉快！** 🎉
