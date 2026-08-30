# 🚀 AWS EC2 Nginx Website Deployment

A beginner-friendly DevOps project demonstrating how to launch an Ubuntu EC2 instance on AWS, configure networking, install and manage the Nginx web server, deploy a custom HTML website, and maintain the project using Git & GitHub.

---

# ☁️ Complete AWS EC2 Deployment Architecture

```mermaid
flowchart TB

%%=============================
%% Developer
%%=============================

subgraph DEV["👨💻 Developer Machine"]

VS["💻 VS Code"]
GIT["📂 Local Git"]
GH["🐙 GitHub Repository"]

VS -->|"Write Code"| GIT
GIT -->|"git add"| GIT
GIT -->|"git commit"| GIT
GIT -->|"git push"| GH

end

%%=============================
%% AWS Cloud
%%=============================

subgraph AWS["☁️ Amazon Web Services (AWS)"]

direction TB

IG["🌍 Internet Gateway"]

subgraph SG["🛡️ Security Group"]

SSH["🔐 SSH (Port 22)"]
HTTP["🌐 HTTP (Port 80)"]

end

subgraph EC2["🖥️ Ubuntu EC2 Instance"]

OS["🐧 Ubuntu Server"]

NGINX["⚙️ Nginx Web Server"]

HTML["📄 index.html"]

FILES["📁 /var/www/html"]

OS --> NGINX
NGINX --> FILES
FILES --> HTML

end

IG --> SG
SG --> SSH
SG --> HTTP

SSH --> OS
HTTP --> NGINX

end

%%=============================
%% User
%%=============================

subgraph CLIENT["🌍 End User"]

Browser["🖥️ Web Browser"]

end

%%=============================
%% Connections
%%=============================

VS -. SSH Login .-> SSH

GH -. Source Code Backup .-> VS

Browser -->|"HTTP Request"| IG

HTML -->|"HTML Response"| Browser
```

---

# 🚀 Deployment Workflow

```mermaid
flowchart LR

A["📝 Create index.html"]

-->B["📂 Initialize Git"]

-->C["📤 Push Code to GitHub"]

-->D["☁️ Launch AWS EC2"]

-->E["🔐 Connect using SSH"]

-->F["📦 sudo apt update"]

-->G["⚙️ Install Nginx"]

-->H["📄 Replace Default index.html"]

-->I["🔄 Restart Nginx"]

-->J["🌐 Access Website via Public IP"]

-->K["✅ Website Live"]
```

---

# 🌐 Client Request Lifecycle

```mermaid
sequenceDiagram

actor User

participant Browser
participant Internet
participant AWS
participant SecurityGroup
participant Ubuntu
participant Nginx
participant HTML

User->>Browser: Enter EC2 Public IP

Browser->>Internet: HTTP Request (Port 80)

Internet->>AWS: Route Request

AWS->>SecurityGroup: Validate Rules

SecurityGroup->>Ubuntu: Allow Traffic

Ubuntu->>Nginx: Forward Request

Nginx->>HTML: Read index.html

HTML-->>Nginx: HTML Content

Nginx-->>Browser: HTTP Response

Browser-->>User: Render Website
```

---

# 🔐 Network Architecture

```mermaid
flowchart LR

User["👤 User"]

Internet["🌍 Internet"]

SG["🛡️ AWS Security Group"]

SSH["🔐 Port 22"]

HTTP["🌐 Port 80"]

EC2["🖥️ Ubuntu EC2"]

NGINX["⚙️ Nginx"]

WEB["📄 HTML Website"]

User --> Internet

Internet --> SG

SG --> SSH

SG --> HTTP

SSH --> EC2

HTTP --> NGINX

EC2 --> NGINX

NGINX --> WEB

WEB --> User
```

---

## 📌 Project Overview

This project covers the complete workflow of:

* Launching an Ubuntu EC2 Instance
* Configuring Security Groups
* Connecting through SSH
* Installing and managing Nginx
* Hosting a custom HTML website
* Uploading the project to GitHub with documentation

---

# 🛠️ Technology Stack

| Technology   | Purpose               |
| ------------ | --------------------- |
| AWS EC2      | Cloud Virtual Machine |
| Ubuntu Linux | Operating System      |
| Nginx        | Web Server            |
| Git          | Version Control       |
| GitHub       | Source Code Hosting   |
| HTML5        | Static Website        |

---

# 📂 Project Structure

```text
aws-ec2-nginx-website/
│
├── index.html
├── README.md
│
└── screenshot/
    ├── Ec2.png
    ├── sshconnect.png
    ├── aptupdate.png
    ├── installnginx.png
    ├── running-nginx.png
    ├── restartnginx.png
    ├── diskuses.png
    ├── memoryuses.png
    ├── runningprocess.png
    ├── htmlwebsitecmd.png
    ├── htmlpage.png
    └── websitenginx.png
```

---

# ✅ Task 1 — AWS EC2 Instance Setup

### Steps Performed

* Logged in to AWS Management Console
* Launched an Ubuntu EC2 Instance
* Created a Security Group
* Allowed inbound traffic:

  * SSH (Port 22)
  * HTTP (Port 80)
* Generated and downloaded the SSH Key Pair
* Connected securely using SSH

### SSH Command

```bash
ssh -i "intern-key.pem" ubuntu@<EC2_PUBLIC_IP>
```

---

## 📷 EC2 Dashboard

![EC2 Dashboard](screenshot/Ec2.png)

---

## 📷 SSH Login

![SSH Connection](screenshot/sshconnect.png)

---

# ✅ Task 2 — Linux Basics & Nginx Installation

## Update Packages

```bash
sudo apt update
```

![Update Packages](screenshot/aptupdate.png)

---

## Install Nginx

```bash
sudo apt install nginx -y
```

![Install Nginx](screenshot/installnginx.png)

---

## Check Nginx Status

```bash
sudo systemctl status nginx
```

![Nginx Status](screenshot/running-nginx.png)

---

## Restart Nginx

```bash
sudo systemctl restart nginx
```

![Restart Nginx](screenshot/restartnginx.png)

---

## Check Disk Usage

```bash
df -h
```

![Disk Usage](screenshot/diskuses.png)

---

## Check Memory Usage

```bash
free -h
```

![Memory Usage](screenshot/memoryuses.png)

---

## Running Processes

```bash
ps -ef
```

![Running Processes](screenshot/runningprocess.png)

---

# ✅ Task 3 — Host a Simple Website

### Website Deployment Steps

* Created a custom `index.html`
* Added:

  * Name
  * College
  * Branch
  * Email
  * Current Date
* Replaced the default Nginx page
* Restarted the Nginx service
* Verified the deployment using the EC2 Public IP

---

## HTML Configuration

![HTML Commands](screenshot/htmlwebsitecmd.png)

---

## HTML Source Code

![HTML Page](screenshot/htmlpage.png)

---

## 🌐 Live Website

![Website](screenshot/websitenginx.png)

---

# ✅ Task 4 — Git & GitHub

The complete project has been uploaded to GitHub.

### Repository

**https://github.com/Saurav6200907210/aws-ec2-nginx-website**

---

# 💻 Commands Used

```bash
sudo apt update
sudo apt install nginx -y
sudo systemctl status nginx
sudo systemctl restart nginx
df -h
free -h
ps -ef
```

---

# 🎯 Learning Outcomes

Through this project, I learned how to:

* Launch and configure an AWS EC2 instance
* Configure Security Groups
* Connect to a Linux server using SSH
* Install and manage the Nginx web server
* Host a static website on AWS
* Work with essential Linux commands
* Use Git and GitHub for version control
* Document a deployment project professionally

---

# 👨💻 Author

**Gurajapu Vinay Teja**

**College:** Sathyabama University (Chennai)

**Branch:** CSE

**Email:** [Vinayteja8885@gmail.com](mailto:vinayteja8885@gmail.com)

**Deployment Date:** 09 July 2026

---

⭐ If you found this project useful, consider giving the repository a star.
