# EC2 Apache / Nginx Web Server Deployment

## Overview

This project demonstrates how to deploy a **production-ready web server** on **AWS EC2** using **Apache (httpd)** or **Nginx**. The server hosts a static website and is publicly accessible via HTTP.

This project highlights hands-on experience in **cloud infrastructure provisioning, Linux server administration, web server configuration, and security best practices**.

---

## Live Architecture Flow

User Browser → Public IP → AWS EC2 → Apache/Nginx → Static Website

---

## Tech Stack

* AWS EC2
* Amazon Linux / Ubuntu
* Apache (httpd) or Nginx
* SSH & Linux CLI
* Git & GitHub

---

## Repository Structure

```
ec2-apache-web-server/
├── index.html
├── README.md
└── setup-commands.txt
```

---

## Key Features

* EC2 instance provisioning
* Secure SSH access using key pairs
* Apache/Nginx web server setup
* Static website hosting
* Security Group configuration (HTTP & SSH)
* Auto-start configuration on reboot

---

## Step-by-Step Deployment Guide

### 1. Launch an EC2 Instance

* AMI: Amazon Linux 2 or Ubuntu
* Instance Type: t2.micro (Free Tier eligible)
* Security Group Rules:

  * SSH → Port 22
  * HTTP → Port 80

---

### 2. Connect to EC2 via SSH

```bash
ssh -i your-key.pem ec2-user@<EC2-PUBLIC-IP>
```

(Use `ubuntu` user for Ubuntu AMI)

---

### 3. Install Apache Web Server

```bash
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```

### OR Install Nginx

```bash
sudo yum install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
```

---

### 4. Deploy Website Content

```bash
sudo echo "<h1>Welcome to My EC2 Web Server</h1>" | sudo tee /var/www/html/index.html
```

For Nginx:

```bash
sudo echo "<h1>Welcome to My EC2 Web Server</h1>" | sudo tee /usr/share/nginx/html/index.html
```

---

### 5. Access Website

```
http://<EC2-PUBLIC-IP>
```

---

## Security Configuration

* AWS Security Group allows inbound HTTP (80) and SSH (22)
* IAM and EC2 key pairs ensure secure access
* Public access restricted to required ports only

---

## Learning Outcomes

* Real-world AWS EC2 deployment
* Linux web server administration
* Git & GitHub project version control
* Cloud networking & security fundamentals

---

## Real-World Use Cases

* Hosting static websites
* Deploying backend services
* Reverse proxy configuration
* Entry-level DevOps infrastructure projects

---

## Interview-Ready Summary

I deployed a public web server on AWS EC2 by configuring security groups, installing Apache/Nginx, hosting a static webpage, and ensuring service persistence across reboots. This project demonstrates cloud infrastructure provisioning, Linux system management, and production-ready deployment skills.

---

## Author

**Jaishree Chaure**

---

## Future Enhancements

* Add Elastic IP
* Enable HTTPS with SSL
* Configure Nginx reverse proxy
* Add Load Balancer (ALB)
* CI/CD deployment pipeline
