# Automated S3 Backup & Restore

This repository contains the **technical documentation** for the project **Automated S3 Backup & Restore**, which securely backs up local files to **Amazon S3** and restores them when needed.

📄 The complete documentation is available in this repo as [`Automated S3 Backup & Restore (Anurag Prasad).pdf`](./Automated%20S3%20Backup%20%26%20Restore%20(Anurag%20Prasad).pdf).  

---

## 📘 Project Overview
This project implements an **automated backup and restore system** using **AWS CLI** and **Bash scripting**. It allows incremental backups of a local directory to Amazon S3 with support for automation, logging, and optional encryption.

**Key Features:**
- Automated **incremental backups** to S3 using `aws s3 sync`.  
- **Restore script** to retrieve full backups.  
- **Logging** of backup and restore operations.  
- **Cron jobs** for scheduling automated backups.  
- **Optional encryption** (AES256 server-side encryption).  

---

## 🏗 Architecture and Approach
The system is built around the following components:
- **Source Directory**: `~/data`  
- **S3 Bucket**: `project-backup.bucket`  
- **Backup Script**: Automates backup via AWS CLI.  
- **Restore Script**: Retrieves data from S3.  
- **Logging**: Tracks operation outcomes.  
- **Cron Job**: Automates backups on schedule.  

---

## 🔄 Backup Flow
1. User triggers backup script or cron runs it automatically.  
2. Script verifies the source directory.  
3. Data is synced to S3 with incremental updates.  
4. Logs are stored for reference.  

---

## 🔁 Restore Flow
1. User manually runs the restore script.  
2. Data is copied from S3 to the restore directory.  
3. Logs capture the restoration steps.  

---

## ⚡ Challenges Faced
- Permission issues → solved by logging in the home directory.  
- Missing directories → solved by auto-creating them.  
- S3 access issues → solved via proper AWS CLI configuration.  
- Script execution errors → solved with correct permissions and paths.  

---

## 📌 Assumptions & Trade-offs
- AWS CLI is configured with valid credentials.  
- Default backup frequency is **twice a week via cron** (adjustable).  
- Encryption is optional but supported.  
- Optimized bandwidth usage with `aws s3 sync`.  

---

## 🚀 How to Use
1. Create an **S3 bucket** in your AWS account.  
2. Install and configure **AWS CLI** on your system.  
3. Add backup and restore scripts (see documentation PDF).  
4. Test backup manually to confirm functionality.  
5. Set up a **cron job** for automated periodic backups.  

---

## 🛠 Tech Stack
- **AWS S3** (Cloud storage)  
- **AWS CLI** (Command-line interface)  
- **Bash Scripting** (Automation)  
- **Cron Jobs** (Scheduling)  

---

## 👨‍💻 Author
**Anurag Prasad**   
🔗 https://www.linkedin.com/in/anurag-prasad1611/
