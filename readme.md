Votin🧩 Project Overview

This project demonstrates the full DevOps lifecycle on Azure — from code commit to automatic deployment — using modern GitOps principles.
It connects Continuous Integration (CI) with Continuous Deployment (CD) by combining:

Azure DevOps Pipelines for building and pushing container images

Azure Container Registry (ACR) for artifact management

Argo CD (GitOps) for declarative, automated deployments

Azure Kubernetes Service (AKS) + VM Scale Sets (VMSS) for hybrid application scaling

🎯 Goal: Automate the entire pipeline where pushing code to Git triggers a full build + deploy flow — with the cluster self-managing deployments via Argo.

🏗️ Architecture Diagram

(You can upload your existing flowchart-style diagram here and link it like this)

Architecture Flow:

Developer commits code → triggers Azure DevOps CI Pipeline

Code is built, containerized, and pushed to Azure Container Registry (ACR)

Argo CD continuously monitors a Git repository containing Kubernetes manifests

Once new manifests or image tags are pushed, Argo automatically syncs with the AKS cluster

Kubernetes deploys updated pods or services

VMSS auto-scales to handle larger workloads if required

🧰 Tools & Technologies

Category	Tool / Service	Purpose
Version Control	
Azure Repos	Source Code Repository
CI (Build)	Azure Pipelines	Automate build, test, and image creation
Container Registry	Azure Container Registry (ACR)	Stores Docker images
CD (Deploy)	Argo CD (GitOps)	Manages deployments via Git synchronization
Orchestration	Kubernetes (AKS)	Manages containerized applications
Scaling	VMSS (Virtual Machine Scale Sets)	Provides elasticity for workloads

Continuous Integration (CI) — Day 10

Created a CI pipeline in Azure DevOps to:

Fetch source code from GitHub

Build the Docker image of the microservice app

Push the image to Azure Container Registry (ACR)

Configured triggers for automatic builds on code changes (trigger: in YAML)

Verified successful build and image tagging in ACR

2️⃣ Continuous Deployment (CD) — Day 11

Deployed Argo CD in the AKS cluster using kubectl manifests

Configured Argo to monitor a separate Git repo with Kubernetes YAML files: manifest.yaml

Set auto-sync and self-healing modes in Argo

Integrated VMSS to scale workloads that are not containerized

Verified deployment rollout from Git → Argo → Kubernetes → Running Pods


<img width="1840" height="1046" alt="nodes ip" src="https://github.com/user-attachments/assets/56509e7d-97e0-4860-a6be-13cfb27f2264" />
<img width="1840" height="1046" alt="secrets" src="https://github.com/user-attachments/assets/11706c27-43c1-48b4-9f10-b4a4db9efff7" />
<img width="1840" height="1046" alt="Screenshot from 2025-10-16 14-51-20" src="https://github.com/user-attachments/assets/e1412654-b7b1-433d-9790-7734a5868e74" />
<img width="1840" height="1046" alt="jobsucces" src="https://github.com/user-attachments/assets/f56356d3-ce1f-4472-8c0a-6793e7d39162" />
<img width="1840" height="1046" alt="5" src="https://github.com/user-attachments/assets/32bcdc71-9b90-4a36-9965-3141b2f51c0b" />
<img width="1840" height="1046" alt="4" src="https://github.com/user-attachments/assets/28bbfe8d-20f6-4115-a0e1-d4994c4a9281" />
![Uploading 4.png…]()
<img width="1840" height="1046" alt="3" src="https://github.com/user-attachments/assets/5babc98d-b620-4f79-b398-ed4a17e8f5a7" />
<img width="1840" height="1046" alt="3reposit" src="https://github.com/user-attachments/assets/d482459d-c590-4648-b483-45b33104c6a9" />
<img width="1840" height="1046" alt="1container" src="https://github.com/user-attachments/assets/2e42facd-cd83-4a74-815e-d051ecdfa854" />
<img width="1840" height="1046" alt="2azuredevops" src="https://github.com/user-attachments/assets/90842a67-3183-4329-8a90-9f968b5c4e9d" />
<img width="1840" height="1046" alt="1container" src="https://github.com/user-attachments/assets/31158c09-9bce-4e03-b9b7-90e3306262ee" />
<img width="813" height="723" alt="11" src="https://github.com/user-attachments/assets/66f9158e-fb25-4b3e-91e0-9e2bd01e26d0" />
<img width="1840" height="1046" alt="10jobs tun" src="https://github.com/user-attachments/assets/518069a7-aca6-4627-9e75-e7b943169284" />
<img width="1840" height="1046" alt="9ssh" src="https://github.com/user-attachments/assets/b04f5e68-8f52-42ae-8587-0dcb9a781eef" />
<img width="1840" height="1046" alt="8docker" src="https://github.com/user-attachments/assets/7c82b7b1-a5b3-4c65-a9c2-aaac8618f322" />
<img width="1840" height="1046" alt="7config" src="https://github.com/user-attachments/assets/4b7807c7-5bed-426d-aab2-0c3404f56a2d" />
<img width="1840" height="1046" alt="1" src="https://github.com/user-attachments/assets/8b043165-664b-40ce-9438-26fbd34ed4e4" />
<img width="1840" height="1046" alt="instalargocd" src="https://github.com/user-attachments/assets/a672abc3-34c3-474e-8ac8-7c9bd9ffae77" />
<img width="1840" height="1046" alt="7" src="https://github.com/user-attachments/assets/38d3f995-5cd8-41fc-a2dd-02c6f074a203" />
<img width="1840" height="1046" alt="6" src="https://github.com/user-attachments/assets/6c245299-71da-4fa1-beb1-723f45d99436" />

🧠 Key Learnings

GitOps Simplifies CD: Argo CD automatically reconciles live and desired states, eliminating manual deployment.

Full Traceability: Every change is versioned and auditable in Git.

Hybrid Scaling: VMSS complements Kubernetes for non-container workloads or hybrid scenarios.

Declarative Infrastructure: Everything — from pipeline to deployment — defined as YAML-as-code.

Rollback Simplicity: Reverting Git commits = automatic rollback in deployment.


Knowledge Source : https://youtu.be/HyTIsLZWkZg?si=DysBLqfNhtiNW-zg
