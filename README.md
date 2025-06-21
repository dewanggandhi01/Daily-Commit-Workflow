# 🕓 Daily Commit Workflow

This repository uses **GitHub Actions** to run a workflow that automatically commits a new line to a log file every day. It's a great way to explore scheduled automation on GitHub.

---

## 🚀 Features

- 📅 Runs every day at `4:15 AM UTC` (9:45 AM IST)
- 🧠 Uses `cron` expression in GitHub Actions
- 📄 Modifies `daily-log.txt` on every run
- ✍️ Step includes email `23f2004781@ds.study.iitm.ac.in`
- 🔄 Supports manual triggering (`workflow_dispatch`)
- 🔐 Pushes commits with bot credentials

---

## 🧾 Workflow File: `.github/workflows/daily-commit.yml`

This workflow performs these actions:
- Checks out the repo
- Appends the current UTC time to `daily-log.txt`
- Commits and pushes the changes

> You can find the full workflow in `.github/workflows/daily-commit.yml`

---

## 📄 File: `daily-log.txt`

A simple text file in the root directory that stores the log of each commit.  
Each workflow run appends a line like this:


---

## ✅ How to Use

1. **Fork or clone this repository**
2. Keep or customize `daily-log.txt`
3. Ensure your default branch is **`main`**
4. GitHub Actions will:
   - Run automatically every day
   - Allow manual triggering from the **Actions** tab

---

## 🧑 Maintainer

- **Email**: `23f2004781@ds.study.iitm.ac.in`
- **GitHub**: [@dewanggandhi01](https://github.com/dewanggandhi01)

---

## 📜 License

This project is open-source and available under the [MIT License](LICENSE).

---

### 🛠 How to Add This README

1. Go to your repository  
2. Click `Add file` → `Create new file`  
3. Name it: `README.md`  
4. Paste this Markdown content  
5. Click **Commit new file**

---


