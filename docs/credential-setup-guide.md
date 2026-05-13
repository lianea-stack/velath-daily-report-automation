# Credential Setup Guide

This document explains how clients can reconnect required credentials after deploying the project on a fresh **Windows 11** machine.

---

## Part A — Google Sheets Credential Setup

### Step 1: Open Google Cloud Console

Go to:
[https://console.cloud.google.com/](https://console.cloud.google.com/)

Login using the Google account that owns the spreadsheet.

---

### Step 2: Create a Project

* Click project dropdown
* Click **New Project**
* Project name: `Velath Daily Report`
* Click **Create**

---

### Step 3: Enable Google Sheets API

Go to:
[https://console.cloud.google.com/apis/library](https://console.cloud.google.com/apis/library)

Search:
`Google Sheets API`

Click **Enable**

---

### Step 4: Configure OAuth Consent Screen

Navigate to:
`APIs & Services → OAuth consent screen`

Choose:
`External`

Fill in:

* App name → Velath Daily Report
* User support email → your email
* Developer email → your email

Save and continue.

---

### Step 5: Create OAuth Credentials

Navigate to:
`APIs & Services → Credentials`

Click:
`Create Credentials`

Choose:
`OAuth Client ID`

Application type:
`Web Application`

---

### Step 6: Add Redirect URI

Use:
`http://localhost:5678/rest/oauth2-credential/callback`

Add this under:
`Authorized redirect URIs`

Save.

---

### Step 7: Copy Client ID + Secret

Save:

* Client ID
* Client Secret

These will be used inside n8n.

---

## Part B — SMTP Credential Setup

### Step 1: Open n8n

Open:
`http://localhost:5678`

---

### Step 2: Open Credentials

* Click **Credentials**
* Click **Create Credential**
* Search `SMTP`

---

### Step 3: Enter SMTP Details

Host:
`smtp.office365.com`

Port:
`587`

User:
`liane.a@velath.com`

Password:
`your password or app password`

---

### Step 4: Advanced Settings

Set:

* SSL/TLS → OFF
* Disable STARTTLS → OFF
* Client Host Name → localhost

---

### Step 5: Save Credential

Click **Save**

Recommended credential name:
`Velath SMTP`

---

## Part C — Connect Credentials to Workflow

After both credentials are created:

### Google Sheets Node

Select:
`Google Sheets account`

### Send Email Node

Select:
`Velath SMTP`

Save workflow.

---

## Validation Checklist

* Preview webhook works
* Send webhook works
* Google Sheets reads rows
* SMTP sends email
* Schedule trigger active
