# Task 5 – Kubernetes Cluster with Minikube

**Prepared by:** Ashok Jangid
**GitHub Repository:** [https://github.com/Aj4236/k8s-task5](https://github.com/Aj4236/k8s-task5)

---

## Description

This repository contains the complete setup and demonstration of **Task 5**, where a Kubernetes cluster is built locally on **AlmaLinux** using **Minikube**, **kubectl**, and **Docker**. The Nginx application is deployed, exposed via a service, and scaled to demonstrate pod management and logging.

---

## Tools Used

* Minikube v1.37.0
* kubectl (latest stable version)
* Docker CE
* Editor: vi
* AlmaLinux 9.5

---

## Repository Structure

```
k8s-task5/
├── deployment.yaml        # Nginx deployment manifest
├── service.yaml           # Nginx service manifest
├── screenshots/           # Captured outputs as terminal screenshots
│   ├── nodes.txt
│   ├── pods.txt
│   ├── pods_running.txt
│   ├── describe_pod.txt
│   ├── pod_logs.txt
│   └── nginx_page.txt
└── README.md              # This file
```

---

## Steps to Reproduce

### 1. Start Minikube Cluster

```bash
sudo minikube start --driver=none
kubectl get nodes
```

*Screenshot:* `screenshots/nodes.txt`

### 2. Create Deployment

```bash
kubectl apply -f deployment.yaml
kubectl get pods
```

*Screenshot:* `screenshots/pods.txt`

### 3. Expose Deployment via Service

```bash
kubectl apply -f service.yaml
kubectl get services
```

*Screenshot:* `screenshots/nginx_page.txt`

### 4. Scale Deployment

```bash
kubectl scale deployment nginx-deployment --replicas=4
kubectl get pods
```

*Screenshot:* `screenshots/pods_running.txt`

### 5. Inspect Pods & Capture Logs

```bash
kubectl describe pod <pod-name> > screenshots/describe_pod.txt
kubectl logs <pod-name> > screenshots/pod_logs.txt
```

*Screenshots:* `describe_pod.txt` and `pod_logs.txt`

---

## Notes

* Use **--driver=none** for low-resource AlmaLinux setups.
* Run commands as the same user who started Minikube.
* YAML files created using `vi`.
* Screenshots are saved as **text files** for submission purposes.

---

## Deliverables

* `deployment.yaml`
* `service.yaml`
* `screenshots/` folder containing terminal outputs for all steps.

