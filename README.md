# 🕓 Daily Commit Workflow

This repository contains a GitHub Actions workflow that **automatically makes a daily commit** to this repository. It is useful for maintaining GitHub contribution streaks or simply experimenting with GitHub Actions and cron jobs.

---

## 📋 Features

- 🔁 **Scheduled Commit** once every day
- 📧 Includes a step labeled with email `23f2004781@ds.study.iitm.ac.in`
- 🕒 Runs daily at **4:15 AM UTC** (⏰ 9:45 AM IST)
- 📄 Appends a timestamped line to `daily-log.txt`
- ✅ Uses `actions/checkout@v3` with persistent credentials to push commits

---

## 📂 Workflow File

Location: `.github/workflows/daily-commit.yml`

```yaml
name: Daily Commit

on:
  schedule:
    - cron: '15 4 * * *'  # Daily at 4:15 AM UTC
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
📈 Result
Each time the workflow runs, you will see:

A new commit in the repo

A new line in daily-log.txt with the current UTC date and time

A successful Action run visible in the Actions tab

📌 Usage
You can manually run the workflow from the Actions tab

It will also run automatically every day via the cron schedule

🧑‍💻 Maintainer
✉️ 23f2004781@ds.study.iitm.ac.in
🔗 github.com/dewanggandhi01

📜 License
This project is licensed under the MIT License (if you want to add one).

yaml
Copy code

---

### ✅ How to Add It

1. Go to your repo
2. Click **Add file → Create new file**
3. Name it: `README.md`
4. Paste the above content
5. Click **Commit new file**

Let me know if you want me to add badges or change the style!
