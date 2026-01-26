Ultimate Cost-Optimized AWS Lab Project — README
# Cost-Optimized AWS Lab — Production Web App

![AWS Free Tier](https://img.shields.io/badge/Free%20Tier-Enabled-green)
![Status](https://img.shields.io/badge/Status-Lab%20Complete-brightgreen)
![Budget](https://img.shields.io/badge/Budget-%241%20monthly-red)

## 🔥 Project Overview
This lab builds a **production-style AWS web application** using only **cost-optimized resources**, designed to stay within AWS Free Tier and prevent unexpected charges.

---

## 🧩 Architecture (Cost-Optimized)



Internet
|
v
[ALB (MyALB)]
|
v
[Target Group (Web-TG)]
|
v
[Auto Scaling Group (Web-ASG)]
|
v
[t3.micro EC2 Instances]


---

## 🚀 What This Project Includes
### ✅ Cost-Optimized Infrastructure
- **ALB** (free tier eligible)
- **Target Group**
- **Auto Scaling Group**
- **2 × t3.micro EC2 instances**
- **Apache web server**

### ✅ Production Monitoring (Low Cost)
- CloudWatch Dashboard
- CloudWatch Alarms:
  - ALB Unhealthy Targets
  - ASG Instance Loss

### ✅ Cost Governance
- **AWS Budget $1 monthly**
- Alerts at **80% and 100%**

---

## 🔧 Health Check (Optimized)
- Path: `/health.php`
- Interval: **15 seconds**
- Success code: **200**

---

## 📌 Verification Checklist
✅ ALB DNS accessible  
✅ Target Group: **2 Healthy**  
✅ ASG: **2 InService**  
✅ CPU target tracking enabled  
✅ CloudWatch Dashboard created  
✅ Budget alert configured  

---



## 🧪 Minimal Deployment Steps
1. Create ALB + Target Group  
2. Create Launch Template  
3. Create ASG (2 × t3.micro)  
4. Install Apache  
5. Create `/health.php`  
6. Configure CloudWatch  
7. Set AWS Budget  

---

## 🛠️ Health Page Script
```bash
echo "<h1>OK - Web Server Healthy</h1>" | sudo tee /var/www/html/health.php
sudo chown -R apache:apache /var/www
sudo chmod -R 755 /var/www
sudo chmod 644 /var/www/html/health.php
sudo systemctl restart httpd

📈 Monitoring
CloudWatch Dashboard

CPUUtilization

RequestCount

UnHealthyHostCount

Alarms

ALB Unhealthy Targets

ASG Instance Loss

💰 Cost Governance

Budget: $1 monthly

Alerts at 80% / 100%

Ensures zero unexpected charges

🔐 Security

ALB SG: HTTP 80 open to the world

Web SG: HTTP 80 from ALB only

SSH only for maintenance (temporary)

🧾 Final Result

A production-style, cost-optimized AWS environment that stays within free tier limits and prevents budget overruns.
