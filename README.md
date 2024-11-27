## CI/CD Pipeline

This project uses a CI/CD pipeline configured with GitHub Actions to automate the build, test, and deployment process.

### Steps in the Pipeline:
1. **Build**: The application is built using Node.js and its dependencies are installed.
2. **Test**: (Skipped in this case, as no tests are defined yet).
3. **Deploy**: The application is deployed to a Kubernetes cluster using Helm charts.


The pipeline is defined in the `.github/workflows/ci-cd-pipeline.yml` file.

### How to Trigger the Pipeline:
- **Push to main branch**: Automatically triggered on every push to the `main` branch.
- **Manual Trigger**: You can manually trigger the pipeline from GitHub Actions UI.


## Helm Chart

This project uses a Helm chart for Kubernetes deployment.

### Helm Chart Files:
- `Chart.yaml`: Contains metadata for the Helm chart.
- `values.yaml`: Defines the default configuration values (e.g., Docker image tag, replicas, etc.).
- `templates/`: Contains Kubernetes manifests such as `deployment.yaml`, `service.yaml`, and `ingress.yaml`.

### How to Install the Helm Chart:
1. Ensure that Helm is installed.
2. Add the repository (if needed).
3. Install or upgrade the chart:
   ```bash
   helm upgrade --install my-app ./helm/my-app --set image.tag=latest


Helm documentation: https://helm.sh/docs/
Kubernetes documentation: https://kubernetes.io/docs/



## Kubernetes and Helm Deployment

This project is a Node.js API application running on Kubernetes. The deployment is managed using **Helm**, a package manager for Kubernetes. The required Kubernetes resources are defined in the manifest files for both the application and the database.

### Steps to Deploy:
1. **Set Up Kubernetes Cluster**
2. **Deploy Using Helm**
3. **Alternative: Deploy Using Kubectl**

---

### 1. **Setting Up the Kubernetes Cluster**

Before running your application on Kubernetes, you need to have a **Kubernetes cluster** set up. Below are the setup instructions for some popular options:

#### Minikube (Local Kubernetes Cluster):

- **Minikube** allows you to run a Kubernetes cluster locally on your machine.
- To set up Minikube, run the following command:
  
  ```bash
  # Install and start Minikube
  minikube start

  
---

### **Explanation:**

1. **Kubernetes Cluster Setup**: Explains how to set up Kubernetes using either **Minikube** (local Kubernetes) or a managed service like **GKE**.
2. **Helm Chart Explanation**: Describes the contents of a **Helm chart** and how it simplifies the deployment of Kubernetes resources. The **`Chart.yaml`**, **`values.yaml`**, and **`templates/`** folder are discussed.
3. **Kubectl Deployment**: Provides an alternative for those who prefer to avoid Helm by using **kubectl** commands to deploy the application with manifest files.
4. **Verification**: Offers commands to verify that the deployment is successful and how to check Kubernetes resources.

By including this information in your **README.md** file, you'll help others understand how to set up and deploy the application using either **Helm** or **kubectl**. This will make it easier for anyone reviewing or testing your project to follow the setup instructions.

If you need any further help or clarification, feel free to ask! 😊

