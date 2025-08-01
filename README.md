# Jenkins Triggers on EC2

This project showcases the implementation of four different **Jenkins triggers** for automating pipeline execution. All configurations are performed on a Jenkins instance hosted on an **AWS EC2** machine.

> ⚠️ **Note**: The *Remote Build Trigger* is excluded due to security concerns related to exposing credentials.

---

## 🧩 Triggers Implemented

### 1. GitHub Webhook Trigger
- Automatically starts the Jenkins job when changes are pushed to a GitHub repository.
- Configured via GitHub Webhooks and Jenkins Git plugin.
- ✅ Ideal for real-time CI/CD pipelines.

-

https://github.com/user-attachments/assets/9bb3c155-9807-4709-a49d-94a54c55eb91


### 2. Poll SCM Trigger
- Periodically checks the Git repository for changes using CRON syntax.
- Triggers a build **only if changes are found**.
- 🕒 Useful when webhooks are not permitted by network policy.

- 

https://github.com/user-attachments/assets/f843bf3e-ddad-4f31-9ac0-7a5448d9642d





### 3. Scheduled Trigger
- Uses Jenkins' built-in CRON feature to run jobs at fixed times.
- Example: Daily at midnight or every 5 minutes.
- 📅 Ideal for routine tasks like backups, reports, or cleanup scripts.

-

https://github.com/user-attachments/assets/3a74b902-b386-4771-9814-f56ab9bbe639


### 4. One Job After Another (Post-Build Trigger)
- Automatically runs a downstream job after the upstream job finishes.
- ⛓️ Helps in maintaining a **sequential flow of dependent jobs**.
- Configured using **Post-build Actions → Build other projects**.

- 

https://github.com/user-attachments/assets/e4593d01-f1a9-49ee-a2ee-4cd2b0bbd2ba


---

## 🧾 Environment Setup

- **Jenkins Version**: *Version 2.516.1*  
- **OS**: Ubuntu (AWS EC2)  
- **Tools Used**: Jenkins, GitHub, Cron, webhook  
---

## 🔐 Why Remote Trigger Was Skipped?

The Remote Build Trigger was not implemented because:
- It requires exposing an API token or Jenkins user credentials.
- If not properly secured, it can lead to unauthorized job exe.
- but i have added doc decribing how to do it.
