# kube-demo

# 📘 VIM Quick Reference Guide

Vim is a powerful text editor available on most UNIX systems. Below is a concise guide to get started and be productive.

---

## 📝 Modes in Vim

## Vim has **three primary modes**:

| Mode    | Description                          |
|---------|--------------------------------------|
| Normal  | Default mode for navigation & editing |
| Insert  | For inserting text                   |
| Command | For saving, quitting, etc.           |

---

## 🚀 Getting Started

### Open/Create a File
```bash
vim filename
```

### ✍️ Insert Mode

| Key | Action            |
| --- | ----------------- |
| `i` | Enter Insert Mode |

### ⌨️ Return to Normal Mode

| Key   | Action                |
| ----- | --------------------- |
| `ESC` | Return to Normal mode |

### ✂️ Editing in Normal Mode

| Key      | Action              |
| -------- | ------------------- |
| `x`      | Delete character    |
| `dd`     | Delete current line |
| `yy`     | Copy (yank) line    |
| `p`      | Paste below         |
| `P`      | Paste above         |
| `u`      | Undo                |
| `Ctrl+r` | Redo                |

### 💾 Save & Quit

| Command | Description         |
| ------- | ------------------- |
| `:w`    | Save                |
| `:q`    | Quit                |
| `:wq`   | Save and quit       |
| `:q!`   | Quit without saving |

### 🔄 Navigation

| Key | Action     |
| --- | ---------- |
| `h` | Move left  |
| `j` | Move down  |
| `k` | Move up    |
| `l` | Move right |