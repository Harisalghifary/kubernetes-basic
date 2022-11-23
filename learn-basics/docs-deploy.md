# Deployment

## Objectives

- Learn about application Deployments.
- Deploy app on Kubernetes with kubectl.
- Learn about a Service in Kubernetes
- Understand how labels and LabelSelector objects relate to a Service
- Expose an application outside a Kubernetes cluster using a Service

### Using kubectl to Create a Deployment

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

### Kubernetes Services

> Kubernetes Pods are mortal, when worker node dies, the Pods running on the Node are also lost. A service is defined using YAML or JSON. A Kubernetes Service is an abstraction layer which defines a logical set of Pods and enables external traffic exposure, load balancing and service discovery for those Pods.

Service can be exposed in different ways by specifying a `type` in the ServiceSpec:

- ClusterIP(default) -> Exposes the Service on an internal IP in the cluster. This type makes the Service only reachable from within the cluster.
- NodePort -> Exposes the Service on the same port of each selected Node in the cluster using NAT.
  - Using `<NodeIP>:<NodePort>`. Superset of ClusterIP, makes a Service accessible from outside the cluster.
- Load Balancer -> Creates an external load balancer in the current cloud (if supported) and assigns a fixed external IP to the Service. Superset of NodePort.
- ExternalName -> Maps the Service to the contents of the `externalName` field.

Service and Label</br>
-> a grouping primitive that allows logical operation on objects in Kubernetes. Labels are key/value pairs attached to objects and can be used in any number of ways:

- Designate objects for development, test, and production
- Embed version tags
- Classify an object using tags

![label-and-selector](/img/module_04_labels.svg)
