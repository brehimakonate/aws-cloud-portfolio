# Project 2: EC2 + Nginx Demo

## Overview
This project demonstrates how to deploy a simple web server on AWS using an EC2 instance with **Nginx** installed.  

- **Secure**: Security Group configured to allow only HTTP (port 80) and SSH (port 22)  
- **Resilient**: EC2 instance running in a public subnet with Elastic IP (can easily be scaled or replaced)  
- **High-Performing**: Lightweight Nginx server serving static content  
- **Cost-Optimized**: Uses t2.micro (Free Tier eligible)  

The result is a simple static webpage (`index.html`) that introduces me as an aspiring Cloud Architect.

---

## Architecture Diagram (Mermaid)

flowchart LR
  U[User Browser]

  subgraph AWS
    EC2[(EC2: Amazon Linux 2<br/>Nginx)]
    SG((Security Group))
    EIP[(Elastic IP)]
  end

  U -->|HTTP :80| EC2
  U -.->|SSH :22 (admin only)| EC2
  SG --- EC2
  EIP -. optional .-> EC2
---

## Steps

1. Launch an EC2 instance (Amazon Linux 2).  
2. Install Nginx:
   ```bash
   sudo yum update -y
   sudo amazon-linux-extras install nginx1 -y
   sudo systemctl start nginx
   sudo systemctl enable nginx

