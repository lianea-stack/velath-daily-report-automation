# Velath Daily Report Automation

Automated daily reporting system built using :contentReference[oaicite:1]{index=1}, :contentReference[oaicite:2]{index=2}, and SMTP email.

---

## Features

- Pulls daily tasks from Google Sheets
- Generates HTML report table
- Sends automated email reports
- Manual preview mode
- Manual send mode
- Scheduled daily automation

---

## Client Setup (Windows 11)

### 1. Install Docker Desktop

Download and install:

[Docker Desktop](https://www.docker.com/products/docker-desktop/?utm_source=chatgpt.com)

---

### 2. Download Project

Clone repository:

```bash
git clone https://github.com/lianea-stack/velath-daily-report-automation.git
```

OR download ZIP manually from GitHub.

---

### 3. Start n8n

Open terminal inside project folder:

```bash
docker compose up -d
```

---

### 4. Open n8n

Open browser:

http://localhost:5678

---

### 5. Import Workflow

Import:

daily-report-workflow.json

Located in:

workflows/

---

### 6. Configure Credentials

Add:

- Google Sheets credentials
- SMTP credentials

---

### 7. Test Workflow

Preview mode:

http://localhost:5678/webhook/daily-report?mode=preview

Send mode:

http://localhost:5678/webhook/daily-report?mode=send

---

## Schedule

Runs Monday–Saturday at 5PM UAE time

Cron:

0 17 * * 1-6

---

## Project Structure

velath-daily-report-automation/
├── workflows/
├── docs/
├── n8n_data/
├── README.md
├── docker-compose.yml
├── .gitignore
└── .env.example
