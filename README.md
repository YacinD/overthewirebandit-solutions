# Bandit Wargame — Learning Log

A personal learning log documenting my progress through the **Bandit** wargame by OverTheWire.  
This repository focuses on *how* each problem was approached rather than just the final answer.

---

## 📌 Purpose of This Repo

Bandit is designed to introduce:
- Core Linux commands
- File system navigation
- Permissions and ownership
- Searching, filtering, and text processing
- Remote access using SSH

This repo acts as a reference and revision resource as I move through the levels.

---

## 🌍 Challenge Source

- Platform: OverTheWire
- Game: Bandit
- Difficulty: Beginner → Intermediate  
- Official link: https://overthewire.org/wargames/bandit/

---

## 🔧 Setup & Tools

| Tool | Usage |
|----|----|
| Terminal | Command execution |

---

## ▶️ Connecting to Bandit

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```
---

# Bandit Wargame — Level Guide

This document summarizes each Bandit level with **Task** and **Solution** for quick reference.

---

## Levels Overview

| Level | Task | Solution |
|-------|------|---------|
| 0 → 1 | Read the password from the `readme` file | `cat readme` |
| 1 → 2 | Read the file named `-` | `cat ./-` |
| 2 → 3 | Read the file with spaces: `spaces in this filename` | `cat "spaces in this filename"` or `cat spaces\ in\ this\ filename` |
| 3 → 4 | Find the password in a hidden file inside `inhere` | `ls -a inhere` then `cat inhere/.hidden_file` |
| 4 → 5 | Find the only human-readable file in `inhere` | `file inhere/*` → `cat <readable_file>` |
| 5 → 6 | Find a file under `inhere` that is human-readable, 1033 bytes, not executable | `find inhere -type f -size 1033c ! -executable` |
| 6 → 7 | Find the password owned by `bandit7`, group `bandit6`, size 33 bytes | `find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null` |
| 7 → 8 | Find the password next to the word `millionth` in `data.txt` | `grep "millionth" data.txt` (second word on the line) |
| 8 → 9 | Find the line in `data.txt` that occurs only once | `sort data.txt | uniq -u` |
| 9 → 10 | Find the human-readable password preceded by `=` in `data.txt` | `strings data.txt | grep "===="` |

---

**Tip:**  
You can use this table as a **quick cheat sheet** or expand it with **notes per level** inside VS Code.
