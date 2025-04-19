---
title: "明明已經安裝python，therminal還是找不到指令"
date: 2025-04-17T20:45:00+08:00
draft: false
tags: ["hugo", "web"]
categories: ["網站開發"]
---

 先說結論：即使已經安裝了 Python，**若 `.zshrc` 沒有正確把 Python 的安裝路徑加入 `PATH` 環境變數中**，Terminal 是找不到 `python` 或 `python3` 指令的。

---

## 🔍 為什麼會這樣？

終端機打開時會去找可執行的 `python` 指令，而它會根據環境變數 `PATH` 一個一個資料夾去找。

如果 Python 安裝的位置不在這些資料夾中，就會出現：

```
zsh: command not found: python
```

---

## 🧭 解決辦法：加入 Python 路徑到 `.zshrc`

### ✅ 步驟 1：找到 Python 安裝位置

你可以試試這個指令：

```bash
which python3
```

範例結果：

```
/opt/homebrew/bin/python3
```

---

### ✅ 步驟 2：把這個路徑加入 `.zshrc`

用你喜歡的編輯器（或內建的 nano）編輯 `.zshrc`：

```bash
nano ~/.zshrc
```

加上這行（根據你 `which` 出來的結果）：

```bash
export PATH="/opt/homebrew/bin:$PATH"
```

如果你用的是 Pyenv、Anaconda、Homebrew、或其他安裝方式，它們可能會有不同路徑，以下是常見範例：

#### 📦 Homebrew 安裝的 Python（macOS）
```bash
export PATH="/opt/homebrew/bin:$PATH"
```

#### 🐍 Pyenv 安裝的 Python
```bash
export PATH="$HOME/.pyenv/shims:$PATH"
```

#### 🧪 Anaconda
```bash
export PATH="$HOME/anaconda3/bin:$PATH"
```

---

### ✅ 步驟 3：讓 `.zshrc` 設定生效

```bash
source ~/.zshrc
```

---

## ✅ 檢查是否成功

```bash
python3 --version
```

或

```bash
which python3
```

---

