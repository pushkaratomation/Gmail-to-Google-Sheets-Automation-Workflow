# 📊 Gmail-to-Google Sheets Automation Workflow (n8n)

An automated serverless data pipeline built with **n8n** that monitors incoming emails in **Gmail**, extracts structured information from the email body and headers, and automatically appends the records into **Google Sheets** in real time.

---

## 📌 Project Description

Handling incoming emails manually—such as logging customer leads, tracking support tickets, or recording invoice notifications—is repetitive and prone to human error. 

This workflow automates the entire process. By combining **n8n's Gmail Trigger** with **Google Sheets API**, incoming emails matching specific search filters (like subject keywords, labels, or sender addresses) are captured automatically. Key information such as `Sender Email`, `Received Date`, `Subject`, and `Message Body` is parsed and mapped directly into organized rows inside a designated Google Spreadsheet.

---

## ✨ Key Features

- 📩 **Real-Time Email Monitoring:** Uses Gmail Trigger or polling to detect new emails instantly based on custom search queries (e.g., `subject:Lead`, `label:Invoices`).
- 🔍 **Data Extraction & Parsing:** Extracts headers, body text, timestamps, and optional regex-based patterns (e.g., phone numbers, order IDs).
- 📈 **Automated Sheet Logging:** Appends clean, structured rows into Google Sheets without overwriting existing data.
- 🧹 **Data Sanitization:** Ensures multiline email bodies and raw text are cleaned before inserting into spreadsheet cells.

---

## ⚙️ Workflow Architecture

```text
[ 📩 Gmail Trigger ] ──► [ 🔄 Data Parser / Code Node ] ──► [ 📊 Google Sheets Node ]
 (New Email Arrives)       (Extracts Subject, Body, Date)      (Appends Row to Sheet)
