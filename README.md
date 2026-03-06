# Automated-Web-Deployment-Pipeline-Jenkins-Ansible-
This project demonstrates a complete CI/CD workflow to automate the deployment of a web application. It uses Jenkins to trigger builds and Ansible to manage remote server configurations and deployment tasks.

## 🚀 Workflow Overview
* **Code Commit:** Developer pushes changes to the GitHub repository.
* **Jenkins Trigger:** Jenkins detects the change (via Webhooks or Polling) and initiates the build.
* **Artifact Preparation:** Jenkins pulls the latest code and prepares it for deployment.
* **Ansible Orchestration:** Jenkins invokes an Ansible Playbook.
* **Remote Deployment:** Ansible securely connects to the production/remote server (via SSH) to:
    * Transfer the web source files.
    * Configure the web server (Apache/HTTPD).
    * Restart services to apply changes.
* **Notification:** Success or failure notifications are sent via email.

## 🛠️ Tech Stack
* **Jenkins:** CI/CD Automation Server.
* **Ansible:** Configuration Management and Deployment.
* **GitHub:** Version Control System.
* **Apache (HTTPD):** Web Server on the remote host.
* **Linux (CentOS/Ubuntu):** Operating system for the control and remote nodes.

## 📂 Project Structure
* `index.html`: The main web application file.
* `web-server-update.yml`: Ansible Playbook for managing the remote deployment.
* `Jenkinsfile`: (Optional) Pipeline script for the project.

## ⚙️ Setup & Configuration
* **SSH Setup:** Passwordless SSH authentication configured between the Jenkins server and the Remote node.
* **Jenkins Plugins:** Installed "Ansible" and "Publish Over SSH" plugins.
* **Sudo Permissions:** Configured `visudo` to allow the Jenkins user to execute Ansible tasks on the remote host.
