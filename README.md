# robot-shop-infra

Project Title & Badge
markdown
Copy
Edit
# 🚀 Robot Shop Infra (AWS EKS via Terraform)

This repo provisions a production-ready AWS EKS cluster for the Robot Shop microservices app, showcasing best practices in IaC, security, and observability.



Component	Tool/Service
Infrastructure	Terraform
Container Orchestration	AWS EKS - managed K8s
Networking	VPC, subnets, IGW
IAM Roles	Node and Service roles
Monitoring	(if enabled) CloudWatch / Prometheus
Deployment	Helm, kubectl, ArgoCD

Setup Instructions
1. Clone & initialize Terraform

2. Configure AWS credentials

3. Terraform apply to provision cluster

4. Post-deployment steps (e.g., aws eks update-kubeconfig)

5. App deployment (Helm/ArgoCD)

6. Accessing services



Inputs & Outputs
Document key variables.tf, and explain major outputs.tf values (e.g., VPC ID, cluster endpoint, kubeconfig data).

Security & Best Practices
Use least-privilege IAM roles



State storage (Used remote backend usage: S3 + DynamoDB for lock and resilience)




