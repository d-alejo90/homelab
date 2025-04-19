---
id: deployments
aliases:
  - Deployments
tags:
  - kubernetes
  - devops
---

# Deployments

When you want an application with multiple instances, it is when we use deployments.
Deployments use replica sets to manage the number of replicas.
Replicasets are used to manage the number of pods you want running.
The Docs recommend using deployments instead of replicaset directly.

## Common Commands

- Deployments create help
  - `k create deployment -h | less` We pipe to less to scroll through the help.
- Aliases: deployment, deploy
- `--replicas=[number]`: the `replicas` flag is used to specify the number of replicas for the deployment.
- `k get deployments`: it gets the list of deployments.
- `k edit deployment [name]`: it allows you to edit the deployment via yaml file.
- `k describe deployment [name]`: it describes the deployment.
- `k describe replicaset [name]`: it describes the replicaset.
- `k apply deploy -f [file]`: it applies the deployment from the yaml file.

- **Scaling**: you can scale the deployment by changing the number of replicas.

  - `k scale deploy [name] --replicas=[number]`: it scales the deployment to the specified number of replicas.
  - `k scale deploy [name] --replicas=0`: it scales the deployment to zero replicas, effectively stopping it.

- **Strategy:** specifies the strategy used to replace old pods by new ones.
  - RollingUpdate: the default strategy. It gradually replaces pods pods with new ones.
    - maxUnavailable: the maximum number of pods that can be unavailable during the update.
    - maxSurge: the maximum number of pods that can be created above the desired number of pods.
  - Recreate: it terminates all old pods before creating new ones.

[[devops]]
[[kubernetes]]

Links:

202504191220
