# Kubernetes Project: User Management with MySQL Backend

This project demonstrates the creation of a Kubernetes (K8s) deployment on AWS EKS, featuring a frontend user management system and a backend MySQL database to store user information. The project is designed to be easily implemented by others. All the necessary manifest files and resources are shared here for you to explore and deploy yourself.

## Project Overview

- **Frontend**: User management system
- **Backend**: MySQL database to store all user information
- **Testing**: Postman was used for testing the functionality

## Steps to Implement

1. **Set up AWS EKS Cluster**:
   - Create an IAM OIDC provider to allow your pods to access AWS services.
   
2. **Storage Configuration**:
   - Install the EBS CBI driver to use AWS Elastic Block Store (EBS) as persistent storage for your K8s pods.
   
3. **IAM Role Policy**:
   - Create a policy and attach it to the IAM role for your EKS nodes to grant the necessary permissions.
   
4. **Kubernetes Manifests**:
   - Created manifest files for various K8s resources including services, deployments, user management, and config settings.

5. **Testing**:
   - Used Postman to test the API endpoints.

6. **Namespace and Domain Setup**:
   - Set up namespaces and added domains to organize resources in your cluster.

7. **Optional TLS Certificate**:
   - You can add a TLS certificate using Certbot. Follow the instructions here to set up the certificate:
   [Certbot Instructions](https://certbot.eff.org/instructions?ws=nginx&os=snap)

8. **Reference Files**:
   - Screenshots and manifest files are provided for reference.

## Commands Used

- **Associate IAM OIDC provider with the cluster**:
  ```bash
  eksctl utils associate-iam-oidc-provider \
      --region <region-code> \
      --cluster <cluster-name> \
      --approve

- **Apply all YAML manifest files**:
To apply all the Kubernetes manifest files in the `manifests` directory, use the following command:
```bash
kubectl apply -f manifests

