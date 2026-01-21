Project Title

Production-Like Multi-Tier Web App on AWS (Free Tier)

🧠 Project Summary

This project simulates a real production environment using AWS only within Free Tier limits, without CLI or Terraform.
It includes load balancing, auto-scaling, monitoring, alerting, and cost governance, delivering enterprise-grade architecture without generating real cost.

🏗️ Architecture Overview
🔹 Key Components
Layer	Service	Purpose
Web Tier	EC2 (t3.micro)	Hosts web app
Load Balancing	ALB	Distributes traffic
Scaling	Auto Scaling Group	Auto-healing & scaling
Monitoring	CloudWatch	Metrics, dashboard, alarms
Alerts	SNS	Notifications
Cost Control	AWS Budget	Prevents billing surprises
🧩 Architecture Diagram (Text)
Internet
   |
  ALB (public)
   |
Target Group (Web-TG)
   |
Auto Scaling Group
   |
EC2 Instances (private)
   |
(connected to RDS - reused existing free tier)

✅ What Makes This “Ultimate”?
1. Production-grade Security

EC2 is private

ALB is public

No inbound 0.0.0.0/0 to EC2

Proper Security Groups & separation

2. Auto-healing & Scaling

ASG maintains min 1 instance

Auto replaces failed instance

Scales up to 2 instances only (Free Tier safe)

3. Monitoring & Alerting

CloudWatch Dashboard

ALB Unhealthy Host Alarm

ASG Instance Loss Alarm

SNS notifications

4. Cost Governance

$1 monthly budget

Alerts at 80% & 100%

🔧 Full Feature List (Completed)
✔️ Infrastructure

ALB created and configured

Auto Scaling Group created

Launch Template configured

EC2 with Apache + PHP bootstrapped

Web tier isolated in private subnet

✔️ Monitoring

CloudWatch Dashboard created

CPU Utilization widget

Request Count widget

UnHealthy Host Count widget

✔️ Alarms

UnHealthy Targets Alarm

ASG Instance Loss Alarm

✔️ Auto Scaling Policy

CPU target tracking at 50%

Warm-up 300s

Scale-in enabled

✔️ Cost Control

Budget set to $1/month

Alerts set to 80% and 100%

🧾 Installation & Deployment (Click-by-Click)
Step 1 — Launch Template

Go to EC2 Console

Click Launch Templates

Click Create launch template

Name: webserver-prod-template

AMI: Amazon Linux 2023

Instance type: t3.micro

Add webserver-sg

Add User data script (Apache + PHP)

Save

Step 2 — Auto Scaling Group

Go to Auto Scaling Groups

Click Create Auto Scaling Group

Choose webserver-prod-template

Select all AZs

Set:

Min: 1

Desired: 1

Max: 2

Health check: EC2

Create

Step 3 — ALB & Target Group

Go to Load Balancers

Click Create ALB

Configure listener HTTP 80

Create target group: Web-TG

Attach ASG to target group

Step 4 — CloudWatch Dashboard

CloudWatch → Dashboards → Create

Add widgets:

CPUUtilization

RequestCount

UnHealthyHostCount

Step 5 — CloudWatch Alarms

CloudWatch → Alarms → Create

Create UnHealthyHostCount alarm

Create GroupInServiceInstances < 1 alarm

Connect to SNS

Step 6 — Auto Scaling Policy

Auto Scaling → Scaling policies

Add Target Tracking Policy

Metric: CPU

Target: 50%

Step 7 — Budget

AWS Budgets → Create Budget

Monthly Cost Budget: $1

Alerts: 80% & 100%

Output & Value

This project proves the ability to build production-grade cloud infrastructure while:

Staying within Free Tier limits

Using AWS Console only

Applying real enterprise standards

Demonstrating monitoring, security, and cost control
