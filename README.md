# 🕓 Daily Commit Workflow

This repository uses **GitHub Actions** to run a workflow that automatically commits a new line to a log file every day. It's a simple way to learn how scheduled workflows work, and it's also useful for keeping your GitHub contribution graph green!

---

## 🚀 Features

- 📅 **Daily Scheduled Commit** using `cron`
- ✅ **Commit created automatically** by GitHub Actions
- 📩 **Identifiable step** named with your email: `23f2004781@ds.study.iitm.ac.in`
- 📁 Appends a new line to `daily-log.txt` every day
- 📌 Uses `actions/checkout@v3` with push support
- 🔄 Manual trigger supported via `workflow_dispatch`

---

## 🛠 Workflow Details

- **Location**: `.github/workflows/daily-commit.yml`
- **Schedule**: Daily at `4:15 AM UTC` → `9:45 AM IST`
- **Main File Modified**: `daily-log.txt`

---

## 🧾 Workflow Code

```yaml
name: Daily Commit

on:
  schedule:
    - cron: '15 4 * * *'  # Runs daily at 4:15 AM UTC (9:45 AM IST)
  workflow_dispatch:

jobs:
  commit:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v3
        with:
          persist-credentials: true

      - name: Commit step - 23f2004781@ds.study.iitm.ac.in
        run: |
          echo "TDSFU Daily run: $(date -u) TDSFU" >> daily-log.txt

      - name: Git Commit and Push
        run: |
          git config user.name "github-actions[bot]"
          git config user.email "github-actions[bot]@users.noreply.github.com"
          git add daily-log.txt
          git commit -m "Auto commit at $(date -u)" || echo "No changes to commit"
          git push origin main

## 📄 File: `daily-log.txt`

A simple text file in the root directory that stores the log of each commit.  
Each workflow run appends a line like this:


---

## ✅ How to Use

1. **Fork or clone this repository**  
2. Modify or keep `daily-log.txt` as your log file  
3. Ensure the default branch is **`main`**  
4. GitHub Actions will handle the rest:
   - It will **automatically run daily**
   - You can also **manually trigger** the workflow from the **Actions** tab

---

## 🧑 Maintainer

- **Email**: `23f2004781@ds.study.iitm.ac.in`  
- **GitHub**: [@dewanggandhi01](https://github.com/dewanggandhi01)

---

## 📜 License

This project is open-source and available under the [MIT License](LICENSE).

---

### 🛠 To Add This README

1. Go to your repository  
2. Click `Add file` → `Create new file`  
3. Name the file: `README.md`  
4. Paste the content from this markdown  
5. Click **Commit new file**

---


