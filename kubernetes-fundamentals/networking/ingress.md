---
id: ingress
aliases:
  - ingress
tags:
  - kubernetes
  - devops
  - kubernetes-networking
---

# Ingress

It exposes HTTP and HTTPS routes from outside the cluster to services within the cluster. An Ingress is a collection of rules that allow inbound connections to reach the cluster services.

## Features

- SSL/TLS termination
- External URLs
- PATH-based routing

## Implemented By

- Ingress Controller:
  - NGINX
  - Traefik: This is used by Rancher Desktop
  - Cilium
  - Cloud: AGIC
- Ingress Resource (YAML)
  - `k create ingress`

[[kubernetes]]
[[devops]]
[[kubernetes-networking]]

Links:

202504191740
