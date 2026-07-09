# AWS EC2 Nginx Website

## Project Overview

This project demonstrates how to launch an Ubuntu EC2 instance on AWS, install Nginx, and host a simple HTML website.

---

## Technologies Used

- AWS EC2
- Ubuntu Linux
- Nginx
- Git
- GitHub

---

## EC2 Setup Steps

1. Login to AWS Console.
2. Launch Ubuntu EC2 Instance.
3. Create Security Group.
4. Allow:
   - SSH (22)
   - HTTP (80)
5. Download Key Pair.
6. Connect using SSH.

---

## SSH Command

```bash
ssh -i "intern-key.pem" ubuntu@<EC2_PUBLIC_IP>
```

---

## Update Packages

```bash
sudo apt update
```

---

## Install Nginx

```bash
sudo apt install nginx -y
```

---

## Check Status

```bash
sudo systemctl status nginx
```

---

## Restart Nginx

```bash
sudo systemctl restart nginx
```

---

## Disk Usage

```bash
df -h
```

---

## Memory Usage

```bash
free -h
```

---

## Running Processes

```bash
ps -ef
```

---

## Website Location

```text
/var/www/html/index.html
```

---

## Deployment

Open browser

```
http://<EC2_PUBLIC_IP>
```

---

## Author

Name: Saurav Kumar

Branch: Computer Science Engeering