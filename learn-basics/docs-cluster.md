## Create Cluster using Minikube

### Objectives :

- Learn what a Kubnernetes cluster is
- Learn what Minkube is
- Learn about Kubernetes Pods
- Learn about Kubernetes Nodes
- Troubleshoot deployed applications

Kubernetes is a production-ready opensource tool for orchestrates of application containers within and across computer clusters.

Kubernetes cluster consist of two types of resources:

- Control Plane : to coordinates the cluster (manage)
  - Scheduling applications
  - Maintaining applications
  - Scaling applications
  - Rolling out new updates
- Nodes : the workers that run applications
  - VM or a physical computer that serves as a worker machine in a kubernetes cluster
  - Each node has a Kubelet, agent for managing the node and communicating with control plane
  - Has tools for handling container operations, such as containerd or Docker
  - Using Kubernetes API to communicate with the control plane or to direct interact with the cluster

Minikube is a lightweight Kubernetes implementation that creates a VM on local machine and deploys a simple cluster containing only one node.

Basic Syntax :

- `minikube addons list`
- `minikube addons enable ingress`
- `minikube stop`
- `minikube delete`

Pod

> A pod is a group of one or more application containers (Such as Docker) and includes shared storage (volumes), IP address and information about how to run them (container image version or spesific ports to use).

- Each Pod has a unique IP address and not exposed outside the cluster without a Service.

Nodes

> A Pod always runs on a Node, a worker machine in Kubernetes and may be either a virtual or a physical machine, depending on the cluster.

- Each Node is managed by the control plane.
- A Node can have multiple pods
- Control Plane automatically handles scheduling the pods across the Nodes in the cluster.
- Run Kubelet and Container runtime (like docker)
  ![nodes](../img/module_03_nodes.svg)
  source : https://kubernetes.io/docs

Troubleshooting with kubectl

- `kubectl get`, list resources
- `kubectl describe`, show detailed information about a resource
- `kubectl logs`, print the logs from a container in a pod
- `kubectl exec`, execute a command on container in a pod
