# Project 3: AWS S3 Static Website Hosting

## Overview
This project demonstrates how to host a **static website** on AWS using **S3** (with optional CloudFront for CDN and HTTPS).

- **Secure**: S3 bucket policies, optional CloudFront with HTTPS  
- **Resilient**: AWS-managed infrastructure, highly available  
- **High-Performing**: CloudFront cache for low-latency delivery  
- **Cost-Optimized**: Pay only for storage and requests  

---

## Architecture Diagram (Mermaid)

```mermaid
flowchart TB
    U[User Browser] -->|HTTPS Request| CF[CloudFront (optional)]
    CF -->|Origin| S3[(S3 Static Website Bucket)]
    U -->|HTTP (if no CloudFront)| S3

