# AWS EC2 Nginx Website Deployment

This project demonstrates how to launch an Ubuntu EC2 instance on AWS, install Nginx, and host a custom HTML website as part of the assignment.

---

## Task 1: Create an AWS EC2 Instance

### Steps:
1. Logged into the AWS Management Console.
2. Launched an Ubuntu EC2 Instance.
3. Created a Security Group allowing:
   - **SSH (Port 22)** for remote access.
   - **HTTP (Port 80)** for web traffic.
4. Downloaded the key pair (`intern-key.pem`).
5. Connected to the instance via SSH:
   ```bash
   ssh -i "intern-key.pem" ubuntu@<EC2_PUBLIC_IP>
   ```

### Deliverables & Screenshots:

#### 1. EC2 Instance Dashboard
Below is the screenshot of the active EC2 instance running in the AWS Dashboard:
![EC2 Dashboard](screenshot/Ec2.png)

#### 2. SSH Connection Status
Below is the screenshot showing a successful connection to the EC2 instance via SSH:
![SSH Connection](screenshot/sshconnect.png)

---

## Task 2: Linux Basics & Nginx Configuration

### Commands Executed:

1. **Update system packages:**
   ```bash
   sudo apt update
   ```
   ![Update Packages](screenshot/aptupdate.png)

2. **Install Nginx:**
   ```bash
   sudo apt install nginx -y
   ```
   ![Install Nginx](screenshot/installnginx.png)

3. **Check Nginx Service Status:**
   ```bash
   sudo systemctl status nginx
   ```
   ![Nginx Status](screenshot/running-nginx.png)

4. **Restart Nginx Service:**
   ```bash
   sudo systemctl restart nginx
   ```
   ![Restart Nginx](screenshot/restartnginx.png)

5. **Check Disk Usage:**
   ```bash
   df -h
   ```
   ![Disk Usage](screenshot/diskuses.png)

6. **Check Memory Usage:**
   ```bash
   free -h
   ```
   ![Memory Usage](screenshot/memoryuses.png)

7. **Check Running Processes:**
   ```bash
   ps -ef
   ```
   ![Running Processes](screenshot/runningprocess.png)

---

## Task 3: Host a Simple Website

### Steps:
1. Created a custom `index.html` containing Name, College, Branch, Email, and current Date.
2. Replaced the default Nginx page with the custom page at `/var/www/html/index.html`.
3. Verified the website using the EC2 Public IP.

### Deliverables & Screenshots:

#### 1. HTML Configuration & File Replacement:
![HTML Configuration Commands](screenshot/htmlwebsitecmd.png)
![HTML Code Preview](screenshot/htmlpage.png)

#### 2. Live Website Accessible via Browser:
![Website Live](screenshot/websitenginx.png)

---

## Task 4: Git & GitHub

The complete project files, including this documentation and configuration screenshots, have been uploaded to GitHub.

- **GitHub Repository:** [AWS-EC2-Nginx-Website](https://github.com/Saurav6200907210/aws-ec2-nginx-website)

---

## Author Information

- **Name:** Sonu Singh
- **College:** Rajkiya Engineering College, Tekari, Gaya
- **Branch:** Information Technology
- **Email:** sonukumarteg245@gmail.com
- **Date:** 09 July 2026