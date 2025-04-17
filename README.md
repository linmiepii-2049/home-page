# 我的新網站

使用Hugo和PaperMod主題建立的個人網站專案。

## 專案結構

```
MyFreshWebsite/
├── archetypes/        # 內容模板目錄
├── assets/            # 需要處理的資源文件
├── content/           # 網站內容目錄
│   ├── posts/         # 博客文章
│   └── about.md       # 關於頁面
├── data/              # 配置數據
├── i18n/              # 國際化文件
├── layouts/           # 自定義布局模板
├── static/            # 靜態資源文件
├── themes/            # 主題目錄
│   └── PaperMod/      # PaperMod主題
├── hugo.yaml          # Hugo配置文件
└── README.md          # 專案說明文檔
```

## 功能特點

- 響應式設計，適配各種設備
- 支持深色/淺色模式自動切換
- 文章閱讀時間顯示
- 文章分享按鈕
- 文章導航鏈接
- 面包屑導航
- 代碼複製按鈕

## 安裝與運行

### 前置條件

- 安裝 [Hugo](https://gohugo.io/installation/) (建議使用最新版本)
- Git

### 本地開發

1. 克隆此倉庫
   ```bash
   git clone https://github.com/yourusername/MyFreshWebsite.git
   cd MyFreshWebsite
   ```

2. 啟動開發服務器
   ```bash
   hugo server -D
   ```

3. 在瀏覽器中訪問 http://localhost:1313/

### 建立靜態網站

```bash
hugo
```

生成的靜態網站將存放在 `public/` 目錄中。

## 內容管理

### 新增文章

```bash
hugo new content posts/my-new-post.md
```

### 文章格式

所有文章都應包含以下前置內容：

```yaml
---
title: "文章標題"
date: YYYY-MM-DDT00:00:00+08:00
draft: false
tags: ["標籤1", "標籤2"]
categories: ["分類"]
---
```

## 自定義

### 主題配置

主題配置參數位於 `hugo.yaml` 文件中的 `params` 部分。

### 菜單配置

菜單配置位於 `hugo.yaml` 文件中的 `menu` 部分。

## 版本歷史

### v1.0.0 (當前版本)
- 初始網站設置
- 添加PaperMod主題
- 創建基本頁面結構
- 建立首篇文章和關於頁面 