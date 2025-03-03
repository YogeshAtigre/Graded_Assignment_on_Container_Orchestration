Here's a **detailed step-by-step guide** to completing your assignment on Kubernetes deployment files, HELM charts, and Jenkins CI/CD for a MERN stack application. 🚀  

---

## **Step 1: Setup Your Environment**  
Before proceeding, ensure you have the following installed:  
- **Docker** 🐳 (for containerization)  
- **Minikube** or a Kubernetes Cluster (for local testing)  
- **Kubectl** (Kubernetes CLI)  
- **HELM** (for package management)  
- **Jenkins** (for CI/CD automation)  

---

## **Step 2: Create Dockerfiles for Frontend and Backend**  
Each service (Frontend & Backend) needs to be containerized using Docker.  

### **2.1 Backend Dockerfile (`backend/Dockerfile`)**
code shared in git repo 
---

### **2.2 Frontend Dockerfile (`frontend/Dockerfile`)**
code shared in git repo 
---

## **Step 3: Kubernetes Deployment & Service Files**  
code shared in git repo 
### **3.1 Backend Deployment (`kubernetes/backend-deployment.yaml`)**
code shared in git repo 

### **3.2 Frontend Deployment (`kubernetes/frontend-deployment.yaml`)**
code shared in git repo

### **3.3 MongoDB Deployment (`kubernetes/mongo-deployment.yaml`)**
code shared in git repo
---

## **Step 4: Create a HELM Chart**
### **4.1 Initialize HELM Chart**
```sh
helm create mern-chart
```

### **4.2 Modify `values.yaml`**  
Update `mern-chart/values.yaml` to include variables for images and ports.


### **4.3 Deploy Using HELM**
```sh
helm install mern-app ./mern-chart
```

---

## **Step 5: CI/CD Pipeline with Jenkins**
### **5.1 Install Required Jenkins Plugins**
- **Pipeline**  
- **Kubernetes CLI**  
- **Docker Pipeline**  

### **5.2 Create Jenkinsfile**
code shared in git repo
---

## **Step 6: Testing and Validation**
### **6.1 Verify Pods and Services**
```sh
kubectl get pods
kubectl get services
```

### **6.2 Check Application Logs**
```sh
kubectl logs -f deployment/backend
kubectl logs -f deployment/frontend
```

### **6.3 Access the Application**
- Get the external IP of the frontend service:
```sh
kubectl get service frontend-service
```
- Open the browser:  
  ```
  http://<EXTERNAL-IP>
  ```
---

## 🎯 **Final Notes**
✅ You now have a fully deployed MERN stack on Kubernetes with a Helm chart and a Jenkins CI/CD pipeline! 🚀  
