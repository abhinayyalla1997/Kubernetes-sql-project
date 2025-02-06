# Kubernetes-sql-project
deployment of frontend usermanagement and backend with sql 

# Kubernetes Project with Frontend User Management and MySQL Backend

## Project Overview

This project sets up a Kubernetes (K8s) environment with a frontend user management system and a backend MySQL database to store user information. Postman is used to test the API endpoints. All necessary manifest files are provided for easy implementation.

## Steps to Implement

1. **IAM OIDC Provider Setup**  
   As I am using AWS EKS, I created an IAM OIDC provider to grant access to my pods for AWS services.

2. **EBS Storage Setup**  
   Installed the EBS CBI driver to enable the use of AWS EBS as storage for Kubernetes pods.

3. **IAM Role Policy Creation**  
   Created a policy and attached it to the IAM role for EKS nodes to ensure proper permissions.

4. **Manifest Files**  
   Created the following Kubernetes manifest files:
   - **Service**
   - **Deployment**
   - **User Management**
   - **Config**

5. **Postman Testing**  
   Used Postman to test API endpoints and ensure the system works as expected.

6. **References**  
   Included screenshots and manifest files for reference.

## Main Commands Used in This Project

```bash
# Associate IAM OIDC provider to EKS
eksctl utils associate-iam-oidc-provider \
    --region <region-code> \
    --cluster <cluster-name> \
    --approve

# Apply all manifest files in the 'manifests' folder
kubectl apply -f manifests/

# Get information about all services, namespaces, pods, and PVCs
kubectl get svc,ns,pods,pvc

# Get detailed information about nodes
kubectl get nodes -o wide

# Test MySQL connection with a MySQL client pod
kubectl run -it --rm --image=mysql:5.6 --restart=Never mysql-client -- mysql -h mysql -pdbpassword11
