## Architecture Diagram (Mermaid)

```mermaid
flowchart TD
    U[User] --> CF[CloudFront]
    CF --> S3[S3 Static Website]
    S3 -.-> API[API Gateway]
    API --> L[Lambda]
    L --> DB[DynamoDB]
    U --> Auth[Cognito]
    L --> CW[CloudWatch Logs]





