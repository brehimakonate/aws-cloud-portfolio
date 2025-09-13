# Project 1 – Static Web App on EC2

This project deploys a static website (`index.html`) on a single EC2 instance with Nginx.

## Architecture Diagram (Mermaid)

```mermaid
flowchart TD
    Client -->|HTTP| EC2[(EC2 Instance)]
    EC2 -->|Serve static page| Client


**Project 2**
```bash
cat > project2/README.md <<'EOF'
# Project 2 – Load Balanced Web App

This project adds a load balancer to distribute traffic.

## Architecture Diagram (Mermaid)

```mermaid
flowchart TD
    Client --> ALB[(Application Load Balancer)]
    ALB --> EC2A[(EC2 Instance A)]
    ALB --> EC2B[(EC2 Instance B)]
    EC2A --> DB[(Database)]
    EC2B --> DB


**Project 3**
```bash
cat > project3/README.md <<'EOF'
# Project 3 – Auto Scaling Group

This project introduces auto scaling to handle variable load.

## Architecture Diagram (Mermaid)

```mermaid
flowchart TD
    Client --> ALB[(Application Load Balancer)]
    ALB --> ASG[(Auto Scaling Group)]
    ASG --> EC2A[(EC2 Instance 1)]
    ASG --> EC2B[(EC2 Instance 2)]
    EC2A --> DB[(Database)]
    EC2B --> DB


**Project 4**
```bash
cat > project4/README.md <<'EOF'
# Project 4 – Highly Available Multi-AZ Architecture

This project builds a production-grade architecture across multiple Availability Zones.

## Architecture Diagram (Mermaid)

```mermaid
flowchart TD
    Client --> Route53[(Route 53 DNS)]
    Route53 --> ALB1[(ALB - AZ1)]
    Route53 --> ALB2[(ALB - AZ2)]
    ALB1 --> EC2A[(EC2 in AZ1)]
    ALB2 --> EC2B[(EC2 in AZ2)]
    EC2A --> RDS[(RDS Primary)]
    EC2B --> RDS[(RDS Standby)]


---

### 🔹 Step 2. Stage all files
```bash
git add project1/README.md project2/README.md project3/README.md project4/README.md project4/site/index.html

