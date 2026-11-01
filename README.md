# DevOps Full-Stack Deployment: Flask + Express on AWS

End-to-end CI/CD and infrastructure automation for a Flask backend and an
Express frontend, deployed on Kubernetes (EKS) on AWS.

## Architecture
![Architecture](docs/architecture.png)

## Tech Stack
| Area | Tools |
|------|-------|
| Source control | Git, GitHub |
| CI/CD | Jenkins |
| Code quality | SonarQube |
| Artifacts | JFrog Artifactory, Amazon ECR |
| Containers | Docker |
| Orchestration | Kubernetes (EKS) |
| Infrastructure as Code | Terraform |
| Configuration | Ansible |
| Monitoring | CloudWatch |

## Pipeline Flow
1. Developer pushes code to GitHub
2. Webhook triggers the Jenkins pipeline
3. Build and unit tests
4. SonarQube quality gate
5. Docker image build, then push to ECR / Artifactory
6. Deploy to Kubernetes with kubectl
7. Monitor with Prometheus

## Infrastructure (Terraform)
Provisions: VPC, subnets, security groups, ALB, ECR, EKS.

```bash
cd terraform
terraform init
terraform plan
terraform apply
```

## How to Run
```bash
docker build -t backend ./backend
docker build -t frontend ./frontend
kubectl apply -f k8s/
```

## Results
- Reduced manual deployment effort by ~55%

## Project Structure
```
├── backend/        # Flask app
├── frontend/       # Express app
├── terraform/      # AWS infrastructure
├── k8s/            # Kubernetes manifests
├── ansible/        # Playbooks
├── Jenkinsfile
└── docs/architecture.png
```

## Author
Poorvitha K M | [LinkedIn](https://www.linkedin.com/in/poorvitha-k-m/)
