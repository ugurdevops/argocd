# Argo CD Declarative Setup

## Overview

This repository contains the necessary configurations and definitions for setting up and deploying applications using Argo CD Declarative Setup.

## Getting Started

To get started with this project, clone the repository to your local machine.

```
git clone https://github.com/ugurdevops/argocd
```

## Declarative Setup (`declarative-setup`)

The `declarative-setup` directory contains YAML files for setting up Argo CD applications and projects in a declarative manner.

### How to Use

1. **Install ArgoCD**
```
kubectl create namespace argocd

helm repo add argo https://argoproj.github.io/argo-helm -n argocd

helm install <release-name> argo/argo-cd  -n argocd
```

2.  **Project Setup**: Apply the `project.yaml` to create a new project in Argo CD.
    ```
    kubectl apply -f declarative-setup/project.yaml
    ```
3.  **Application Setup**: Apply the `applications.yaml` to register the applications with Argo CD under the created project.
    ```
    kubectl apply -f declarative-setup/applications.yaml
    ```

## Deployment (`deployment`)

The `deployment` directory includes YAML files for deploying a Node.js application on Kubernetes. Also check the [blogpost](https://medium.com/@ugurozkandev/demystifying-argocd-a-guide-to-declarative-setup-a43b609265db) about the deployment.


## License

This project is licensed under the [MIT License](LICENSE). See the LICENSE file for more details.
