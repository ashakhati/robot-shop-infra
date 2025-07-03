# robot-shop-infra

Project Title & Badge
markdown
Copy
Edit
# 🚀 Robot Shop Infra (AWS EKS via Terraform)
[![Terraform Version](https://img.shields.io/badge/terraform-v1.3.0-blue)]()
[![AWS](https://img.shields.io/badge/aws-eks-orange)]()
b) Problem Statement & Value
One or two sentences:
“This repo provisions a production-ready AWS EKS cluster for the Robot Shop microservices app, showcasing best practices in IaC, security, and observability.”

c) Architecture Diagram
Embed your visual here:

markdown
Copy
Edit
![EKS Architecture](diagrams/eks-architecture.png)
d) Tech Stack Table
Component	Tool/Service
Infrastructure	Terraform
Container Orchestration	AWS EKS - managed K8s
Networking	VPC, subnets, IGW
IAM Roles	Node and Service roles
Monitoring	(if enabled) CloudWatch / Prometheus
Deployment	Helm, kubectl, ArgoCD

e) Setup Instructions
Clone & initialize Terraform

Configure AWS credentials

Terraform apply to provision cluster

Post-deployment steps (e.g., aws eks update-kubeconfig)

App deployment (Helm/ArgoCD)

Accessing services

Add concrete code snippets for each.

f) Inputs & Outputs
Document key variables.tf, and explain major outputs.tf values (e.g., VPC ID, cluster endpoint, kubeconfig data).

g) Security & Best Practices
Use least-privilege IAM roles

Version pinning (required_providers, terraform)

State storage (mention remote backend usage: S3 + DynamoDB for lock and resilience)

h) Optional Enhancements
Autoscaling (node_group, cluster_autoscaler)

Monitoring: add Prometheus/Grafana integration in Terraform (or instructions to install via Helm)

CI/CD trigger: automating terraform apply via GitHub Actions

3. 🛠 Terraform Module Hygiene
Use terraform fmt and terraform validate

Split into modules: vpc/, eks/, etc., each with clear main.tf, variables, and outputs

Use versions.tf to pin Terraform and provider versions

Suggest using remote backend like terraform { backend "s3" … } for real-world workflows

4. ✅ Example Code Snippet
In terraform/modules/eks/main.tf:

hcl
Copy
Edit
resource "aws_eks_cluster" "robot_shop" {
  name     = var.cluster_name
  role_arn = aws_iam_role.eks_cluster.arn

  vpc_config {
    subnet_ids = var.private_subnets
  }

  tags = var.tags
}
It’s helpful to keep README explanations close to real code.

5. 🚧 Scripts & Automation
Add a scripts/ folder containing bash scripts for:

setup_kubeconfig.sh: runs aws eks update-kubeconfig …

deploy_app.sh: applies Helm chart to the cluster

Link them in README:

bash
Copy
Edit
./scripts/setup_kubeconfig.sh
./scripts/deploy_app.sh


