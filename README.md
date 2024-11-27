CI/CD Pipeline
This project uses a CI/CD pipeline configured with GitHub Actions to automate the build, test, and deployment process.

Steps in the Pipeline:
Build: The application is built using Node.js, and its dependencies are installed.
Test: (Skipped in this case, as no tests are defined yet).
Deploy: The application is deployed to a Kubernetes cluster using Helm charts.
The pipeline is defined in the .github/workflows/ci-cd-pipeline.yml file.

How to Trigger the Pipeline:
Push to the main branch: Automatically triggered on every push to the main branch.
Manual Trigger: You can manually trigger the pipeline from the GitHub Actions UI.

Helm Chart
This project uses a Helm chart to manage the Kubernetes deployment.

Helm Chart Files:
Chart.yaml: Contains metadata for the Helm chart.
values.yaml: Defines the default configuration values (e.g., Docker image tag, replicas, etc.).
templates/: Contains Kubernetes manifests such as deployment.yaml, service.yaml, and ingress.yaml.
How to Install the Helm Chart:
Ensure that Helm is installed on your machine.
Add the repository (if needed).
Install or upgrade the chart with the following command:

helm upgrade --install my-app ./helm/my-app --set image.tag=latest
For detailed Helm usage, refer to the official Helm documentation:

Kubernetes and Helm Deployment
This project is a Node.js API application running on Kubernetes. The deployment is managed using Helm, a package manager for Kubernetes. The necessary Kubernetes resources are defined in the manifest files for both the application and the database.

Steps to Deploy:
Set Up Kubernetes Cluster
Deploy Using Helm
Alternative: Deploy Using Kubectl
1. Setting Up the Kubernetes Cluster
Before deploying your application, you need to have a Kubernetes cluster set up. Below are the setup instructions for some popular options:

Minikube (Local Kubernetes Cluster):
Minikube allows you to run a local Kubernetes cluster on your machine. This is useful for testing and development purposes.

To set up Minikube, run the following command:


# Install and start Minikube
minikube start
This command will start a local Kubernetes cluster using Minikube.

Google Kubernetes Engine (GKE) or Other Managed Solutions:
If you're using a managed Kubernetes service, such as GKE (Google Kubernetes Engine), you can connect to your cluster by running:


# Get credentials for your GKE cluster
gcloud container clusters get-credentials my-cluster --zone us-central1-a --project my-project
This will allow you to interact with your GKE cluster using kubectl.
2. Deploy Using Helm
Once your Kubernetes cluster is up and running, you can use Helm to deploy your application. Helm simplifies the deployment process by packaging Kubernetes resources into charts.

Installing Helm:
If you don't have Helm installed, you can install it by running the following command:


# Install Helm
curl https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 | bash
Deploying the Application Using Helm:
Ensure that you have the Helm chart for your application. It is located in the helm/my-app/ directory.

You can install or upgrade the application with this command:

helm upgrade --install my-app ./helm/my-app --set image.tag=latest
This command will deploy the application to the Kubernetes cluster using the Helm chart. The image.tag parameter specifies which Docker image to use, which can be updated for each deployment.

3. Alternative: Deploy Using Kubectl
If you prefer not to use Helm, you can deploy your application using kubectl directly with Kubernetes manifest files.

Kubernetes Manifest Files:
deployment.yaml: Defines the Kubernetes Deployment resource.
service.yaml: Defines the Kubernetes Service resource (exposes the application).
ingress.yaml: Defines the Kubernetes Ingress resource (optional, for handling external traffic).
Deploying with Kubectl:
If you choose not to use Helm, you can apply the manifest files directly to your Kubernetes cluster with kubectl:


# Apply the Kubernetes manifest files
kubectl apply -f k8s/manifests/deployment.yaml
kubectl apply -f k8s/manifests/service.yaml
kubectl apply -f k8s/manifests/ingress.yaml
These commands will create the necessary resources on the Kubernetes cluster.

Verifying the Deployment:
Once the application is deployed, you can verify that it is running correctly by using the following commands:

# Check the status of the pods
kubectl get pods

# Check the status of the services
kubectl get svc

# View the logs of a specific pod
kubectl logs <pod-name>
Conclusion
This project provides a simple Node.js API application that can be deployed to Kubernetes using Helm. Helm simplifies the management of Kubernetes resources by packaging them into charts, making deployment and updates easier. If you prefer, you can also deploy the application using kubectl commands with the Kubernetes manifest files.
