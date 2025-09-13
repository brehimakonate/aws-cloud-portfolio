# Project 1 – Static Web App on EC2

This project deploys a static website (`index.html`) on a single EC2 instance with Nginx.

## Architecture Diagram (Mermaid)

```mermaid
flowchart TD
    Client -->|HTTP| EC2[(EC2 Instance)]
    EC2 -->|Serve static page| Client

