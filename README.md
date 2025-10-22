#  MySQL on Kubernetes

This project demonstrates how to **deploy a MySQL database** inside a **Kubernetes cluster** using essential Kubernetes objects such as **Secrets**, **PersistentVolumeClaim (PVC)**, **Deployment**, and **Service**.

---

## Project Structure

mysql-kubernetes/
     │
     ├── secret.yaml                            # Stores MySQL root password securely using Kubernetes Secrets
     ├── pvc.yaml                               # Defines PersistentVolumeClaim for data persistence
     ├── deployment.yaml                        # Deploys MySQL 5.7 container with persistent storage and secrets
     ├── service.yaml                           # Exposes MySQL using NodePort for external access


---

## Features

-  Secure password management with **Kubernetes Secrets**
-  **Persistent storage** using PVC to retain MySQL data
-  Deploys **MySQL 5.7** container via Deployment manifest
-  **NodePort Service** to expose MySQL outside the cluster
-  Easy to scale and manage using Kubernetes declarative configs

---

##  Deployment Steps

### Apply the manifests
Run the following commands in order:

```bash
kubectl apply -f secret.yaml
kubectl apply -f pvc.yaml
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml


Verify resources

kubectl get pods
kubectl get svc
kubectl get pvc

Access the MySQL database

mysql -h <NodeIP> -P 30036 -u root -p
