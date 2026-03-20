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