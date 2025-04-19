---
id: services
aliases:
  - kubernetes services
tags:
  - kubernetes
  - services
  - devops
  - networking
---

# Kubernetes Services

A service offers a consistent address to access a set of pods.

## Why we need services?

- Pods are ephemeral and can be created and destroyed at any time.
- You should not expect a pod to have a long lifespan.
- Pods are constantly changing an being moved across nodes.
- How will the system keep track of the constantly changing IP addresses?

### Types of Services

- ClusterIP: Default service type. Exposes the service on a cluster-internal IP. Pods can communicate with each other using this IP.
- NodePort: Exposes the service on each node's IP at a static port. This allows external traffic to access the service.
- LoadBalancer: Exposes the service externally using a cloud provider's load balancer. This is typically used in cloud environments (can also be used in k3s/Rancher Desktop).

## Commands

- `k get services`: List all services in the current namespace.
- `k expose -h | less`: Get help on the expose command.
- `k expose deployment <deployment-name> --port=<port> --target-port=<target-port>`: Expose a deployment as a service.
- `k get svc -o yaml > service.yaml`: Export the service configuration to a YAML file.

  [[devops]]
  [[kubernetes]]
  [[kubernetes-networking]]

Links:

202504191637
