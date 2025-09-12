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

```mermaid
flowchart TB
    U[Client Browser] -->|HTTP Request| Nginx[(EC2 + Nginx)]
    Nginx -->|Serve index.html| U

