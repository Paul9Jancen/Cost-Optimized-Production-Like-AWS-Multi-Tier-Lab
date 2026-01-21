Ultimate Cost-Optimized Production-Like AWS Lab
Objective

Build a production-like multi-tier web application on AWS using only Free Tier resources. Demonstrate secure architecture, auto-scaling, monitoring, alerting, and cost governance without incurring any charges.

Architecture Overview

ALB (Application Load Balancer) — public endpoint

Auto Scaling Group (ASG) — maintains 1–2 t3.micro EC2 instances

EC2 Instances (Web Tier) — private, only reachable through ALB

RDS (Database Tier) — reused Free Tier PostgreSQL instance

Security Groups

Web tier only allows traffic from ALB

DB only allows traffic from web tier

Features Implemented
✅ Auto Scaling & Resilience

ASG maintains minimum 1 instance

Max 2 instances (Free Tier limit)

CPU target tracking policy at 50%

Auto-healing: replaces failed instances automatically

Health checks ensure only healthy instances serve traffic

✅ Monitoring & Alerts

CloudWatch Dashboard:

EC2 CPUUtilization

ALB RequestCount

ALB UnHealthyHostCount

CloudWatch Alarms:

ALB-UnHealthy-Targets

ASG-Instance-Loss

SNS notifications configured (optional)

✅ Cost Governance

AWS Budget: $1/month

Alerts at 80% and 100%

Ensures zero unexpected charges

Security Best Practices

ALB is public; EC2 instances are private

RDS not publicly accessible

Security groups follow principle of least privilege

No direct SSH access (SSM recommended if needed)

Deployment Details

AMI: Amazon Linux 2023 (Free Tier)

Instance type: t3.micro

Web server: Apache + PHP

DB: PostgreSQL (Free Tier)

How to Validate

Open the ALB DNS name in a browser → web app loads

Terminate the EC2 instance → ASG launches a replacement

CloudWatch dashboard shows metrics

Alarms trigger if health degrades or ASG drops to 0 instances

AWS budget alerts if costs exceed threshold

Outcome

A fully production-like, resilient AWS web application built only within Free Tier limits, with complete monitoring, scaling, and cost controls.
