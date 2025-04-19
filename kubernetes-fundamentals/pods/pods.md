---
id: pods
aliases:
  - Pods
tags:
  - Kubernetes
---

# PODS

[[devops]]
[[kubernetes]]

A pod is the smallest element of a kubernetes cluster
A pod of Whales (A Group of Whales)
A pod is not a container
A pod is a collection of containers 1 to many containers + other resources

- Single container pod
- Multi container pod
- Initcontainer: Rules to run the pod (DB connection, etc.)
- Networking
- Storage

When control plane received a request via kubectl, to create a pod, it will schedule the creation of this pod and the scheduler is going to create the pod in the right node based on the needs of the pod to be run and the resources available in the node.

## Pods as Code - YAML

- Get pods
  - `k get pods`
- Create a pod and generate yaml

  - `k run nginx-yaml --image=nginx --dry-run=client -o yaml > nginx.yaml`

  - ```yaml
    apiVersion: v1
    kind: Pod
    metadata:
      creationTimestamp: null
      labels:
        run: nginx
      name: nginx
    spec:
      containers:
        - image: nginx
          name: nginx
          resources: {}
      dnsPolicy: ClusterFirst
      restartPolicy: Always
    status: {}
    ```

- Create a pod using a yaml file
  - `k apply -f pod.yaml` - This detects the changes between the current state and the desired state and applies the changes.
  - `k create -f pod.yaml` - This just creates the pod and does not check for changes.
  - `k apply -f pod.yaml --dry-run=client` (to check if the yaml is valid, it will output the yaml)
- Get pod info as yaml:
  - `k get pod nginx -o yaml`
  - We can pass less to improve readability in console `k get pod nginx -o yaml | less`
- Edit a pod:
  - `k edit pod nginx`
  - This will open the pod in the default editor (vim)
  - You can change the image of the pod and save it
  - The pod will be recreated with the new image
- Delete a pod:
  - `k delete pod nginx`
  - This will delete the pod and all its containers
    Links:

202504121852
