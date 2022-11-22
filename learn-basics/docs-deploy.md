## Using kubectl to Create a Deployment

### Objectives

- Learn about application Deployments.
- Deploy app on Kubernetes with kubectl.

Kubernetes Deployments

- Create a Kubernetes Deployment configuration
  - Instruct kubernetes how to create and update instances of your application.
  - Kubectl schedules the application instances included in that Deployment to run on individual Nodes in the cluster.
  - Provide a self-healing mechanism to address machine failure or maintenance.

Basic Syntax :

- Create a Deployment that manages a Pod
  - `kubectl create` , pods runs a container based on the provided Docker image.
    - `kubectl create deployement`
    - ` kubectl expose deployment <name>`
- View the Deployement
  - `kubectl get deployments`
- View the Pod
  - `kubectl get pods`
- View cluster events
  - `kubectl get events`
- View the kubectl configuration
  - `kubectl config view`

Further information check this [documentation](https://kubernetes.io/docs/reference/kubectl/) overview.
