# Jenkins Triggers on EC2

This project showcases the implementation of four different **Jenkins triggers** for automating pipeline execution. All configurations are performed on a Jenkins instance hosted on an **AWS EC2** machine.

> ⚠️ **Note**: The *Remote Build Trigger* is excluded due to security concerns related to exposing credentials.

---

## 🧩 Triggers Implemented

### 1. GitHub Webhook Trigger
- Automatically starts the Jenkins job when changes are pushed to a GitHub repository.
- Configured via GitHub Webhooks and Jenkins Git plugin.
- ✅ Ideal for real-time CI/CD pipelines.

- https://github.com/user-attachments/assets/9bb3c155-9807-4709-a49d-94a54c55eb91



### 2. Poll SCM Trigger
- Periodically checks the Git repository for changes using CRON syntax.
- Triggers a build **only if changes are found**.
- 🕒 Useful when webhooks are not permitted by network policy.

### 3. Scheduled Trigger
- Uses Jenkins' built-in CRON feature to run jobs at fixed times.
- Example: Daily at midnight or every 5 minutes.
- 📅 Ideal for routine tasks like backups, reports, or cleanup scripts.

### 4. One Job After Another (Post-Build Trigger)
- Automatically runs a downstream job after the upstream job finishes.
- ⛓️ Helps in maintaining a **sequential flow of dependent jobs**.
- Configured using **Post-build Actions → Build other projects**.

---

## 📹 Demo Videos

Short demo clips showing each trigger in action:

| Trigger Type           | Demo Link |
|------------------------|-----------|
| GitHub Webhook         | [Watch Video](./Untitled%20video%20-%20Made%20with%20Clipchamp.mp4) |
| Poll SCM               | [Watch Video](./Untitled%20video%20-%20Made%20with%20Clipchamp%20(1).mp4) |
| Scheduled Trigger      | [Watch Video](./scheduled%20-%20Made%20with%20Clipchamp.mp4) |
| One Job After Another  | [Watch Video](./oneafterother%20-%20Made%20with%20Clipchamp.mp4) |

> 💡 *You can rename the video files to more readable names like `github_webhook.mp4` or `poll_scm.mp4` for better clarity.*

---

## 🧾 Environment Setup

- **Jenkins Version**: *Version 2.516.1*  
- **OS**: Ubuntu (AWS EC2)  
- **Tools Used**: Jenkins, GitHub, Cron, webhook  
---

## 🔐 Why Remote Trigger Was Skipped?

The Remote Build Trigger was not implemented because:
- It requires exposing an API token or Jenkins user credentials.
- If not properly secured, it can lead to unauthorized job exe
