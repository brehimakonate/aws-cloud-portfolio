# AWS Cloud Portfolio

A compact portfolio of 4 AWS projects, each with a clean **Mermaid** diagram that GitHub renders automatically.

## Projects

- **Project 1 — Static Web App on EC2**  
  – Simple EC2 + Nginx serving a static page.  
  📄 [Open README](project1/README.md)

- **Project 2 — Load Balanced Web App**  
  – ALB in front of two EC2 instances with a shared DB.  
  📄 [Open README](project2/README.md)

- **Project 3 — Auto Scaling Group**  
  – ALB -> ASG for resilient, scalable compute; shared DB.  
  📄 [Open README](project3/README.md)

- **Project 4 — Multi-AZ, Production-grade**  
  – Route 53, ALBs in two AZs, EC2 in each AZ, RDS Multi-AZ.  
  – Includes a small demo site at `project4/site/index.html`.  
  📄 [Open README](project4/README.md)

## Notes

- Diagrams are fenced like this so GitHub renders them:

  ```mermaid
  flowchart TD
    A[Client] --> B[Service]

