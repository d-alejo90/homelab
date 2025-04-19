---
id: networking
aliases:
  - kubernetes networking
tags:
  - kubernetes
  - devops
  - networking
---

# Kubernetes Networking

## Pods

- Networking on Pod level.
- Each Pod gets its own IP address.
- By default, pods can connect to all pods on all nodes.
  - You can restrict this using Network Policies.
- Containers in pods can communicate with each other using `localhost`.

## CNI Plugin

Container Network Interface (CNI)
It allows Kubernetes to manage networking for containers.

- Provides network connectivity to containers.
- Configures network interfaces in containers.
- Assigns IP addresses and sets up routes -> IPTables on nodes
- Implemented by CNI Plugins:
  - Cilium
  - Calico
  - Flannel: this is used by default in rancher desktop.

[[devops]]
[[kubernetes]]

Links:

202504191618
