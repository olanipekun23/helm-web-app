# 🚀 Deploying a Web Application Using Helm in Kubernetes

## 📖 Overview
In this project, we will deploy a **simple web application** into a Kubernetes cluster using **Helm**.  

The project covers:  
- 📦 Using **Helm Charts** to package Kubernetes applications  
- 🛠️ Customizing deployments with **templates** and **values**  
- ⚙️ Installing and running **Helm**  
- 🔄 Integrating Helm into a **basic CI/CD pipeline** for automated deployments  

By the end, you’ll understand how Helm simplifies application management in Kubernetes and how it fits into a DevOps workflow.

---

## 🎯 Objectives
1. Learn the fundamentals of Helm (charts, values, releases, repositories).  
2. Deploy a web application into Kubernetes using Helm.  
3. Customize configurations using `values.yaml`.  
4. Perform upgrades and rollbacks with Helm.  
5. Integrate Helm into a CI/CD pipeline for automated deployments.  

---

## 🏗️ Project Architecture


Developer → Git Repository → CI/CD Pipeline → Kubernetes Cluster
│
└── Uses Helm for deployment


- **Developer** pushes code changes.  
- **CI/CD Pipeline** builds and packages the application.  
- **Helm** deploys or updates the release in Kubernetes.  

---

## ⚙️ Prerequisites
- A running **Kubernetes cluster** (Minikube, Kind, or Cloud-managed like EKS/GKE/AKS).  
- **kubectl** installed and configured.  
- **Helm 3** installed.  
- Docker (for building application image).  
- A GitHub or GitLab account (if integrating with CI/CD).  

---

## 🔧 Setup & Installation

### 1. Install Helm
```bash
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
helm version
```

![helm installation](image-1.png)

![helm.tar](image-2.png)

![helm version](image-3.png)

![clean up](image-4.png)

![code .](image-5.png)

![code insider](image-6.png)

![helm version](image-7.png)

![helm dir](image-8.png)

![create](image-9.png)

![value.yml](image-10.png)

![chart.yml](image-11.png)

![git init](image-12.png)

![git push](image-13.png)

![values.yaml modify](image-14.png)

![deployment.yaml modify](image-15.png)

![git add .](image-16.png)

![kubectl install](image-17.png)

![minikube](image-18.png)

![kubectl config](image-19.png)

![minikube context](image-20.png)

![helm install](image-21.png)

![port forward](image-22.png)

![handling](image-23.png)

![welcome](image-24.png)



# Mini Project: Integrating Helm with Jenkins

Automate Kubernetes deployments with **Helm** via a **Jenkins** CI/CD pipeline.  
This guide walks you from setup to a working pipeline that upgrades/installs a Helm release on every git push.

---

## 🔭 What you’ll build

Developer → Git Push → Jenkins Pipeline → Helm upgrade --install → Kubernetes


- On each commit to your repo, Jenkins runs a pipeline that:
  1) connects to your cluster,
  2) lints and renders your chart,
  3) deploys with `helm upgrade --install`.

---

## ✅ Prerequisites

- A running Kubernetes cluster you can reach from your Jenkins agent (minikube/kind/EKS/GKE/AKS).
- `kubectl` + **Helm 3** installed on the Jenkins agent node.
- Jenkins (with default recommended plugins) and access to create a **Pipeline** job.
- A git repository with a Helm chart at `./webapp`:



webapp/
├─ Chart.yaml
├─ values.yaml
└─ templates/


- A kubeconfig that works with `kubectl` **from the Jenkins agent** (see “Provide cluster credentials to Jenkins”).

---

## 🧰 Prepare your environment

### 1) Verify cluster access (from a terminal that mirrors your Jenkins agent)


```bash
kubectl version --client
kubectl get nodes
```
### PROJECT STEPS

![which helm](image-25.png)

![systemctl](image-26.png)

![Jenkins Dash](image-27.png)

![Jenkinsfile](image-28.png)

![Jenkinsfile config](image-29.png)

![helm values.yaml](image-30.png)

![helm deployment.yaml](image-31.png)

![helm service.yaml](image-32.png)

![jenkins pipeline](image-33.png)

![config](image-34.png)

![trigger config](image-35.png)

![csript](image-36.png)

![webapp](image-37.png)

![start minikube](image-38.png)

![update minikube](image-39.png)

![pipeline fail](image-40.png)

![jenkins link to kubectl](image-41.png)

![chmod](image-42.png)

![pipeline update](image-43.png)

![success](image-44.png)

![dashboard](image-45.png)

![project executed](image-46.png)