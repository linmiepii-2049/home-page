---
title: "如何找到HuggingFace下載的模型位置並刪除"
date: 2025-04-19T07:00:00+08:00
draft: false
tags: ["hugging face", "model", "terminal", "cmd"]
categories: ["AI開發"]
---



## 📦 從HuggingFace下載下來的模型放在哪？
✅ 1. 如果你是用 Hugging Face 下載（像是 Bark 用 from transformers import ...）
Hugging Face 模型會存在這個資料夾下：

🖥 預設路徑

系統    路徑
Linux/macOS    ~/.cache/huggingface/hub
Windows    C:\Users\你的名字\.cache\huggingface\hub



---

## 📦 查看資料夾大小指令：

```bash
du -sh 資料夾路徑
```

### ✅ 例子：
```bash
du -sh ~/Downloads
```

這會顯示 `Downloads` 資料夾的總大小（例如 `2.3G`）。

---

### 📌 說明：

| 參數 | 意義                         |
|------|------------------------------|
| `-s` | summary：只顯示總大小         |
| `-h` | human-readable：用 KB/MB/GB 顯示 |

---

### 🔍 如果你想看資料夾裡**每個子資料夾的大小**：

```bash
du -h -d 1 資料夾路徑
```

### ✅ 例子：
```bash
du -h -d 1 ~/Downloads
```

這會列出 `Downloads` 裡每個子資料夾的大小，方便你找出佔空間的來源。

---

### 💡 補充（用 `sort` 排序）：

如果你想從大到小排列資料夾大小，可以這樣寫：

```bash
du -h -d 1 ~/Downloads | sort -hr
```


---

## 🗑️ 找到目前所在的資料夾位置：

你可以用以下指令查詢**目前所在的資料夾位置** 👇

```bash
pwd
```

---

### 📌 `pwd` 是什麼意思？

> `pwd` = **Print Working Directory**  
> （顯示目前工作目錄）

---

### ✅ 例子：

```bash
jason@Mac-mini ~ % pwd
/Users/jason
```

這表示你現在所在的位置是 `/Users/jason` 資料夾。

---

### 🧭 小補充：怎麼移動資料夾？

如果你想去別的資料夾，可以用：
```bash
cd 資料夾路徑
```

例如：
```bash
cd ~/Downloads
```

然後再打 `pwd` 看看你是否真的切到那裡了。

---



---

## 🗑️ 移除資料夾的指令：

```bash
rm -rf 路徑/資料夾名稱
```

### 📌 範例：
```bash
rm -rf ~/Downloads/test_folder
```

這會**強制（`-f`）遞迴（`-r`）刪除** `test_folder` 資料夾及其中的所有內容。

---

## ⚠️ 注意事項：
- **請務必小心使用 `rm -rf`！** 它不會詢問你是否確認刪除，一旦執行就無法復原。
- 刪錯整個系統資料夾會造成系統損壞（例如 `rm -rf /` ← 千萬別執行）

---

## ✅ 建議流程：

1. 先「確認」你要刪除的資料夾存在：
   ```bash
   ls 路徑
   ```

2. 如果要更安全一點，可以改用這個：
   ```bash
   rm -ir 路徑/資料夾名稱
   ```
   `-i` 會一個一個問你是否刪除，更安全些。

---

有特定資料夾你想刪掉嗎？你可以貼給我完整路徑，我幫你確認指令是否正確（保險一點 👀）。
