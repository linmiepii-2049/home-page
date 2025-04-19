---
title: "本地code上傳至github指令"
date: 2025-04-17T08:00:00+08:00
draft: false
tags: ["git", "github","git pages"]
categories: ["網站開發"]
---

將本地專案上傳到 GitHub 的完整指令流程，並附上每步的說明：

---

### 🛠️ 前提條件
1. 你已經安裝好 [Git](https://git-scm.com/)。
2. 你已經有一個 GitHub 帳號。
3. 你已經在 GitHub 上建立了一個 repository（儲存庫）。

---

### 📁 假設你的資料夾結構如下
你的專案資料夾名稱為 `my-project`。

---

### 🧾 上傳指令與解釋

```bash
cd my-project
```
➡️ 進入你的專案資料夾。

---

```bash
git init
```
➡️ 初始化一個 git 倉庫，讓這個資料夾變成可以被 Git 管理。

---

```bash
git add .
```
➡️ 將所有檔案加入 Git 暫存區，準備提交。

---

```bash
git commit -m "Initial commit"
```
➡️ 提交這次變更，訊息為 “Initial commit”。

---

```bash
git branch -M main
```
➡️ 將分支名稱改為 `main`（新版 GitHub 預設使用 `main` 作為主要分支）。

---

```bash
git remote add origin https://github.com/你的帳號名稱/你的repo名稱.git
```
➡️ 將遠端 GitHub 儲存庫與你的本地專案連接。這行需要換成你的實際 GitHub 連結。

例如：

```bash
git remote add origin https://github.com/johnsmith/my-project.git
```

---

```bash
git push -u origin main
```
➡️ 將 `main` 分支推送到 GitHub，並設定 `origin` 作為預設遠端分支。

---

### ✅ 完成！
現在你的專案已經成功上傳到 GitHub 上了！

---


