# Project 1: AWS E-commerce Architecture

## Overview
This project demonstrates a **3-tier AWS architecture** designed to be:
- **Secure** (AWS WAF, private subnets, IAM, CloudTrail)
- **Resilient** (RDS Multi-AZ, Auto Scaling, ALB health checks)
- **High-Performing** (CloudFront, ALB, caching)
- **Cost-Optimized** (S3 lifecycle rules, single NAT, right-sizing)

This type of architecture could support an e-commerce or business web application.

---

## Architecture Diagram (Mermaid)
The diagram below is written in Mermaid code. GitHub automatically renders it when viewed in a README:

```mermaid
flowchart TB
  %% Clients
  U[Users]

  %% Edge + Security
  CF[Amazon CloudFront]
  WAF[AWS WAF attached to CloudFront]

  %% Static content
  S3[S3 Bucket for static assets]

  %% Logging / Audit
  S3L[S3 Bucket for logs]
  CT[AWS CloudTrail]

  %% VPC
  subgraph VPC[VPC 10.0.0.0/16]
    direction LR

    subgraph Public[Public subnets]
      IGW[Internet Gateway]
      NAT[NAT Gateway]
      ALB[Application Load Balancer]
    end

    subgraph App[Private app subnets]
      ASG[EC2 Auto Scaling Group]
    end

    subgraph DB[Private DB subnets]
      RDS[RDS Multi AZ]
    end
  end

  %% Traffic flow
  U --> CF
  WAF -. attached .- CF
  CF -->|/static| S3
  CF -->|/api/*| ALB
  ALB --> ASG
  ASG --> RDS

  %% Egress & internet
  NAT --> IGW
  ALB --> IGW

  %% Logs / audit
  CF -. access logs .-> S3L
  ALB -. access logs .-> S3L
  CT -. audit logs .-> S3L
