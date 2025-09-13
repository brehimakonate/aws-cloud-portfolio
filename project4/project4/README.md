
# Project 4: Simple Serverless Web App

## Overview
This project demonstrates a serverless architecture using AWS managed services:
- **S3 + CloudFront** for static hosting
- **API Gateway + Lambda** for backend logic
- **DynamoDB** for data persistence
- **Cognito** for authentication
- **CloudWatch** for logging & monitoring

---

## Architecture Diagram (Mermaid)


flowchart TD
  U[User] --> CF[CloudFront]
  CF --> S3[S3 Static Website]
  S3 -.calls API./.-> API[API Gateway]
  API --> L[Lambda]
  L --> DB[DynamoDB]
  U --> Auth[Cognito]
  L --> CW[CloudWatch Logs]

