# Project 3: S3 Static Website Hosting with CloudFront

## Overview
This project demonstrates how to host a **static website** on AWS using **S3** (with **CloudFront** for CDN and HTTPS).

- **Secure**: Private S3 bucket + CloudFront Origin Access Control (OAC)
- **Resilient**: AWS-managed infra, highly available
- **High-Performing**: Global edge cache via CloudFront
- **Cost-Optimized**: Pay only for storage + requests

---

## Architecture Diagram (Mermaid)

```mermaid
flowchart TB
  U[User Browser] -->|HTTPS Request| CF[CloudFront]
  CF -->|Origin| S3[S3 Static Website Bucket]
  U -->|HTTP fallback| S3

