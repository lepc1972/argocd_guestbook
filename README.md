# Argo CD Guestbook

This is a simple **Guestbook** application to demonstrate the capabilities of **Argo CD** for continuous deployment and GitOps. The application consists of two main components:

- **Guestbook UI**: A frontend application that allows users to sign the guestbook.
- **Redis Database**: A backend for storing guestbook entries.

This repo provides the necessary Kubernetes manifests to deploy the application using Argo CD.

## Prerequisites

Before you begin, make sure you have the following tools installed:

- **kubectl**: Command-line tool for interacting with your Kubernetes cluster.
- **Argo CD CLI**: Command-line tool for interacting with Argo CD.
- **Helm** (optional): For managing complex deployments.

## Setup

1. **Install Argo CD**: Follow the [Argo CD installation guide](https://argo-cd.readthedocs.io/en/stable/getting_started/) to set up Argo CD in your Kubernetes cluster.

2. **Clone the Repository**:
   ```bash
   git clone https://github.com/lepc1972/argocd_guestbook.git
   cd argocd_guestbook

3. **Deploy the Application**

argocd login <ARGOCD_SERVER> --username <YOUR_USERNAME> --password <YOUR_PASSWORD>
argocd app create guestbook \
  --repo https://github.com/lepc1972/argocd_guestbook.git \
  --path . \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace default

4. **Sync Application**:
   ```bash
   argocd app sync guestbook

5. **Access the guestbook UI**:
   ```bash
   kubectl get svc -n default

## Components

-guestbook-ui-deployment.yaml: Kubernetes deployment manifest for the frontend application      
-guestbook-ui-svc.yaml: Kubernetes service manifest for exposing the frontend.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgements

-Argo CD: A declarative continuous delivery tool for Kubernetes.
-Redis: In-memory database used to store guestbook entries.


This README provides a basic overview of the project, setup instructions, and details on the components of your `argocd_guestbook` repo. Feel free to expand or modify the information based on additional features or changes in your repository.






