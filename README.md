EC2 Apache / Nginx Web Server Deployment on AWS

📌 Project Overview

This project demonstrates how to deploy a production-ready web server on Amazon EC2 using Apache HTTP Server (httpd) or Nginx.
The objective is to gain hands-on experience with EC2 provisioning, security groups, SSH access, Linux server administration, and static website hosting.
A live static website is hosted and publicly accessible via the EC2 instance’s public IP address.

🌍 Live Demo

Website URL:
http://18.116.81.164


🏗️ Architecture Overview

Infrastructure Components:
* Compute: Amazon EC2 (t3.micro – Free Tier eligible)
* Operating System: Amazon Linux
* Web Server: Apache HTTP Server (httpd) / Nginx
* Protocol: HTTP (Port 80)
* Remote Access: SSH (Port 22)


Architecture Flow:
User Browser → Public IP → EC2 Instance → Apache/Nginx → Static HTML Website

🛠️ Tech Stack

AWS EC2
Amazon Linux
Apache (httpd) / Nginx
SSH & Linux CLI
Git & GitHub

📁 Repository Structure
ec2-apache-web-server/
├── index.html
├── README.md
├── setup-commands.txt
└── screenshots/

⭐ Key Features

EC2 instance provisioning
Secure SSH access using key pairs
Apache/Nginx web server installation & configuration
Static website hosting
AWS Security Group configuration (HTTP & SSH)
Web server auto-start on reboot

🚀 Step-by-Step Deployment Guide

1. Launch an EC2 Instance
Created an EC2 instance using Amazon Linux AMI
Selected instance type: t3.micro (Free Tier eligible)
Created and downloaded an SSH key pair
Configured Security Group inbound rules:
SSH → Port 22
HTTP → Port 80

2. Connect to EC2 via SSH
ssh -i my-key.pem ec2-user@18.116.81.164

3. Install Apache Web Server
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
sudo systemctl status httpd


Expected Output:
active (running)

(Optional) Install Nginx
sudo yum install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx

4. Deploy Website Content
sudo echo "<h1>Welcome to My EC2 Web Server</h1>" > /var/www/html/index.html

5. Access Website

Open browser:
http://18.116.81.164
If successful, the welcome message will display.

🔐 Security Configuration

AWS Security Group allows inbound:
HTTP (80)
SSH (22)
Secure SSH authentication using EC2 key pairs
Public access restricted to required ports only
Least-privilege access approach applied

✅ Verification Checklist

EC2 instance state: Running
Apache service status: Active (running)
Port 80 allowed in inbound rules
Website accessible via browser using public IP

📸 Project Screenshots

### EC2 Instance Running
![EC2 Running](screenshots/ec2-instance-running.png)

### Security Group Inbound Rules
![Security Group](screenshots/security-group-inbound-rules.png)

### SSH Connection to EC2
![SSH Login](screenshots/ssh-connection.png)

### Apache Service Status
![Apache Status](screenshots/apache-status.png)

### Website Output
![Website Output](screenshots/webpage-output.png)



📚 Learning Outcomes

Real-world AWS EC2 deployment experience
Linux web server installation & management
Cloud networking & security fundamentals
Git & GitHub version control best practices
Hands-on DevOps infrastructure exposure


🌍 Real-World Use Cases

Hosting static websites
Deploying backend services
Reverse proxy configuration
Entry-level DevOps infrastructure projects


🎯 Interview-Ready Summary

I deployed a public web server on AWS EC2 by provisioning infrastructure, configuring security groups, installing Apache/Nginx, hosting a static website, and enabling service persistence across reboots. This project demonstrates cloud infrastructure management, Linux server administration, and production-ready deployment skills.


🔮 Future Enhancements

Assign Elastic IP
Add custom domain using Amazon Route 53
Enable HTTPS with SSL/TLS
Configure Application Load Balancer (ALB)
Automate deployment using EC2 User Data or Shell Scripts
Add CI/CD pipeline (GitHub Actions)

👩‍💻 Author

Jaishree Chaure