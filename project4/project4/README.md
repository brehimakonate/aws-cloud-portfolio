
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


flowchart LR
  U[User Browser] --> CF[CloudFront]
  WAF[AWS WAF] -. attached .-> CF
  CF -->|/static| S3[S3 for static assets]
  CF -. access logs .-> LGBKT[(S3 log bucket)]

  %% API path
  U -->|/api/*| API[API Gateway]
  API --> L[Lambda]
  L --> DB[(DynamoDB)]
  L -. logs .-> CW[(CloudWatch Logs)]

  CT[CloudTrail] -. audit logs .-> LGBKT
  COG[(Cognito)] -. optional auth .- U

[
](https://abcd1234.execute-api.us-east-1.amazonaws.com/hello
)
