# 文件結構說明

```
project/
├── index.html                  # 前台首頁 (語言選擇)
├── shop.html                   # 商品瀏覽頁面
├── product.html                # 商品詳情 + 訂單表單
├── README.md                   # 完整項目說明文件
├── QUICKSTART.md               # 快速開始指南
│
├── admin/                      # 後台管理目錄
│   ├── index.html             # 登入頁面
│   ├── dashboard.html         # 儀表板
│   ├── products.html          # 商品管理
│   ├── orders.html            # 訂單管理
│   ├── affiliates.html        # 聯盟成員管理
│   └── settings.html          # 系統設定
│
└── js/                         # JavaScript 目錄
    ├── affiliate-tracker.js   # 聯盟追蹤核心邏輯
    ├── shop.js                # 商品瀏覽邏輯
    ├── product.js             # 商品詳情 + 訂單邏輯
    ├── admin-auth.js          # 後台認證系統
    ├── dashboard.js           # 儀表板邏輯
    ├── orders.js              # 訂單管理邏輯 (含CSV匯出)
    ├── affiliates.js          # 聯盟管理邏輯 (含QR Code)
    ├── products.js            # 商品管理邏輯
    └── settings.js            # 系統設定邏輯
```

## 📁 目錄說明

### 前台文件

| 檔案 | 功能 | 主要特色 |
|------|------|---------|
| `index.html` | 語言選擇首頁 | 4國語言旗幟選擇 |
| `shop.html` | 商品列表 | 分類篩選、圖片展示 |
| `product.html` | 商品詳情 | 訂單表單、LINE 跳轉 |

### 後台文件

| 檔案 | 功能 | 主要特色 |
|------|------|---------|
| `admin/index.html` | 登入頁 | 簡易前端認證 |
| `admin/dashboard.html` | 儀表板 | 統計數據、最新訂單 |
| `admin/products.html` | 商品管理 | CRUD、多語言圖片 |
| `admin/orders.html` | 訂單管理 | 狀態更新、CSV 匯出 |
| `admin/affiliates.html` | 聯盟管理 | QR Code、業績統計 |
| `admin/settings.html` | 系統設定 | LINE URL、分類管理 |

### JavaScript 文件

| 檔案 | 功能 | 說明 |
|------|------|------|
| `affiliate-tracker.js` | 聯盟追蹤 | URL 參數捕捉、Cookie 管理 |
| `shop.js` | 商品瀏覽 | 多語言、圖片 Fallback |
| `product.js` | 訂單處理 | 表單驗證、訂單送出 |
| `admin-auth.js` | 認證系統 | SessionStorage 管理 |
| `dashboard.js` | 儀表板 | 統計數據載入 |
| `orders.js` | 訂單管理 | 搜尋、篩選、CSV 匯出 |
| `affiliates.js` | 聯盟管理 | CRUD、QR Code 生成 |
| `products.js` | 商品管理 | CRUD、圖片管理 |
| `settings.js` | 系統設定 | LINE URL、分類管理 |

## 🗄️ 資料庫表格

系統使用 **RESTful Table API** 作為資料儲存:

### 資料表

1. **categories** - 商品分類
2. **products** - 商品資料
3. **orders** - 訂單資料
4. **affiliates** - 聯盟成員
5. **settings** - 系統設定

### API 端點

所有資料表皆支援標準 RESTful API:

```
GET    /tables/{table}           - 列表查詢
GET    /tables/{table}/{id}      - 單筆查詢
POST   /tables/{table}           - 新增記錄
PUT    /tables/{table}/{id}      - 完整更新
PATCH  /tables/{table}/{id}      - 部分更新
DELETE /tables/{table}/{id}      - 刪除記錄
```

## 🎨 使用的 CDN 資源

### Tailwind CSS
```html
<script src="https://cdn.tailwindcss.com"></script>
```

### Font Awesome
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.4.0/css/all.min.css">
```

### QRCode.js
```html
<script src="https://cdn.jsdelivr.net/npm/qrcodejs@1.0.0/qrcode.min.js"></script>
```

## 📝 代碼風格

### HTML
- 語意化標籤
- 清晰的 id/class 命名
- 響應式設計優先

### CSS
- Tailwind CSS Utility Classes
- 自訂 Gradient 漸層
- Hover/Focus 動畫效果

### JavaScript
- ES6+ 語法
- Async/Await 處理非同步
- 模組化函數設計
- 詳細註解說明

## 🔐 安全性考量

### 當前實作
- ✅ 前端 SessionStorage 認證
- ✅ Cookie 追蹤機制
- ✅ 輸入驗證

### 生產環境建議
- 🔸 使用後端 API 認證
- 🔸 JWT Token 機制
- 🔸 HTTPS 加密傳輸
- 🔸 API Rate Limiting
- 🔸 IP 白名單限制

## 📦 無需安裝的依賴

所有依賴皆透過 CDN 載入,無需 npm install!

## 🚀 部署方式

### 方法一: 使用 Publish 標籤
1. 點擊 Publish 標籤
2. 一鍵部署
3. 取得線上網址

### 方法二: 手動部署
1. 下載所有文件
2. 上傳到任何靜態網站主機
3. 開啟 index.html

## 🎯 核心功能檔案對應

| 功能 | 前台檔案 | 後台檔案 | JavaScript |
|------|---------|---------|-----------|
| 語言選擇 | index.html | - | - |
| 商品瀏覽 | shop.html | products.html | shop.js, products.js |
| 下單流程 | product.html | orders.html | product.js, orders.js |
| 聯盟追蹤 | 全站 | affiliates.html | affiliate-tracker.js, affiliates.js |
| 數據統計 | - | dashboard.html | dashboard.js |
| 系統設定 | - | settings.html | settings.js |

## 📊 文件大小統計

- **HTML 文件**: ~50 KB
- **JavaScript 文件**: ~60 KB
- **總計**: ~110 KB (不含 CDN 資源)

## ⚡ 效能優化

### 已實作
- ✅ CDN 加速載入
- ✅ 圖片延遲載入
- ✅ 最小化 DOM 操作
- ✅ LocalStorage 快取

### 可改進
- 🔸 圖片壓縮
- 🔸 Code Splitting
- 🔸 Service Worker 離線支援

---

**版本**: v1.0.0  
**檔案總數**: 18 個  
**代碼行數**: ~2000+ 行
