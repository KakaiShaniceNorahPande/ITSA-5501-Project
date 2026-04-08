# ITSA-5501 Project by Shanice Kakai_n10001739

Project Milestone One.
# ITSA-5501 Project - Milestone 1

## Project Overview
This repository will be used for this course project which will incorporate Git commands, functions and different version control features.

In the project, I added an experiment branch where i psuhed a README file and new placeholders in the subfolders docker and k8s.

I have merged the experiment branch into the main branch.

## Git Workflow
main branch holds initial code
experiment branch used for testing new features
Changes are merged via Pull Requests
Conflicts are resolved manually before merge

## Workflow Steps
Initialized the repository
Created a feature branch
Committed incremental changes
Pushed branch to GitHub
Opened Pull Request

## Versioning
Annotated Git tags are used and the current version: v1.0

## Tools Used
Git & GitHub
Docker, Kubernetes, Infrastructure as Code(as the subfolders)

Project Milestone Two.
# ITSA-5501 Project - Milestone 2

## Project Overview
This project demonstrates Docker Compose orchestration of a multi-container environment including a frontend, MongoDB, PostgreSQL, Redis, and Prometheus.

## Repository Structure
ITSA-5501-Project/
frontend/index.html
docker/docker-compose.yml
prometheus.yml
README.md(updated)
these were the files/folders that were added to the repository.

## Services
- Frontend: nginx:alpine
- User Database: MongoDB
- Product Database: PostgreSQL
- Cache: Redis
- Monitoring: Prometheus

## Commands Used
these following commands were used in docker to start containers, view running containers, and scale the frontend service.
docker compose up -d
docker ps
docker compose up -d --scale frontend=3

## Verification.
I verified using the follwing for frontend and prometheus.
Frontend: http://localhost:9090
Prometheus: http://localhost:9091

Project Milestone Three.
# ITSA-5501 Project - Milestone 3

## Overview
This milestone covers Kubernetes deployment with shared persistent storage, scaling and rolling updates, and Infrastructure as Code using Terraform on Azure

## Project Structure
ITSA-5501-Project/
k8s/pvc.yml
/deployment.yml
/service.yml
IaC/main.tf
/variables.tf
/outputs.tf
README.md(updated)

## Kubernetes Operations
I created a PersistentVolumeClaim named `shared-pvc` with `ReadWriteOnce` and `500Mi`, created a deployment with 2 replicas and each pod contained:
- nginx-container using `nginx:latest`
- sidecar-container using `busybox`
Then both containers shared the same PVC-backed volume, exposed the deployment using a NodePort service, scaled the deployment from 2 replicas to 5 replicas, updated nginx image from `nginx:latest` to `nginx:1.21`, verified shared data access between containers, and then cleaned up the resources.

## Terraform Operations
I configured the Azure provider with Terraform then created:
- Resource Group
- Virtual Network
- Subnet
- Public IP
- Network Interface
- Linux Virtual Machine
I used variables for:
- resource_group_name
- location
- vm_size
- admin_username
Then added tags with `Environment = Dev`, ran commands and destroyed resources after completion.

## Commands Used
I used the following commands to run the k8s files and the iac files
then changed directory to work on both of them
cd ../k8s
minikube start
kubectl get nodes
kubectl apply -f pvc.yml
kubectl apply -f deployment.yml
kubectl apply -f service.yml
kubectl get pvc
kubectl get deployments
kubectl get pods
kubectl get svc
minikube service nginx-sidecar-service --url
kubectl scale deployment nginx-sidecar-deployment --replicas=5
kubectl get pods
kubectl get deployment
kubectl get pods
kubectl exec -it pod-name -c nginx-container -- /bin/sh#picked one pod name to use for this command
cat /usr/share/nginx/html/log.txt
kubectl delete -f service.yml
kubectl delete -f deployment.yml
kubectl delete -f pvc.yml
cd ../iac
az login
az ad sp create-for-rbac --name terraform-sp --role Contributor --scopes /subscriptions/your-subscription-id#used my subscription id
terraform init
terraform validate
terraform apply
terraform state list
terraform destroy
