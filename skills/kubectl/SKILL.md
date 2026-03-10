---
name: kubectl
description: "Kubernetes CLI - manage pods, deployments, services, config contexts. Use when user mentions 'kubectl', 'kubernetes', 'k8s', 'pods', or wants to manage Kubernetes clusters."
category: devtools
install_command: "brew install kubectl"
---

# kubectl

## Setup

```bash
brew install kubectl
```

Verify installation:
```bash
kubectl version --client
```

Use `-o json` or `-o yaml` for machine-readable output.

## Authentication

```bash
kubectl config use-context <context-name>
```

## Resources

### Viewing Resources

| Command | Description |
|---------|-------------|
| `kubectl get pods` | List all pods in current namespace |
| `kubectl get pods -A` | List pods across all namespaces |
| `kubectl get pods -o wide` | List pods with additional details |
| `kubectl get services` | List all services |
| `kubectl get deployments` | List all deployments |
| `kubectl get nodes` | List cluster nodes |
| `kubectl get namespaces` | List all namespaces |
| `kubectl get all` | List all resources in current namespace |
| `kubectl get ingress` | List all ingress resources |
| `kubectl get configmaps` | List all config maps |
| `kubectl get secrets` | List all secrets |

### Describing Resources

| Command | Description |
|---------|-------------|
| `kubectl describe pod <name>` | Show detailed pod info |
| `kubectl describe service <name>` | Show detailed service info |
| `kubectl describe deployment <name>` | Show detailed deployment info |
| `kubectl describe node <name>` | Show detailed node info |

### Creating and Applying

| Command | Description |
|---------|-------------|
| `kubectl apply -f <file.yaml>` | Apply a configuration from file |
| `kubectl apply -f <directory>/` | Apply all configs from a directory |
| `kubectl apply -k <directory>/` | Apply a kustomize configuration |
| `kubectl create namespace <name>` | Create a namespace |
| `kubectl create secret generic <name> --from-literal=key=value` | Create a secret |

### Deleting Resources

| Command | Description |
|---------|-------------|
| `kubectl delete pod <name>` | Delete a pod |
| `kubectl delete -f <file.yaml>` | Delete resources defined in file |
| `kubectl delete deployment <name>` | Delete a deployment |
| `kubectl delete namespace <name>` | Delete a namespace and all its resources |

### Logs and Debugging

| Command | Description |
|---------|-------------|
| `kubectl logs <pod>` | View pod logs |
| `kubectl logs -f <pod>` | Follow pod logs |
| `kubectl logs <pod> -c <container>` | View logs for a specific container |
| `kubectl logs --tail=100 <pod>` | View last 100 lines of logs |
| `kubectl exec -it <pod> -- bash` | Open a shell in a pod |
| `kubectl exec <pod> -- <command>` | Run a command in a pod |
| `kubectl port-forward <pod> 8080:80` | Forward local port to pod |
| `kubectl port-forward svc/<service> 8080:80` | Forward local port to service |

### Scaling and Rollouts

| Command | Description |
|---------|-------------|
| `kubectl scale deployment <name> --replicas=3` | Scale a deployment |
| `kubectl rollout status deployment <name>` | Check rollout status |
| `kubectl rollout history deployment <name>` | View rollout history |
| `kubectl rollout undo deployment <name>` | Rollback to previous revision |
| `kubectl rollout restart deployment <name>` | Restart a deployment |

### Context and Config

| Command | Description |
|---------|-------------|
| `kubectl config get-contexts` | List all contexts |
| `kubectl config current-context` | Show current context |
| `kubectl config use-context <name>` | Switch to a context |
| `kubectl config set-context --current --namespace=<ns>` | Set default namespace for current context |

## Global Flags

| Flag | Description |
|------|-------------|
| `-n <namespace>` | Specify namespace |
| `-o json` | Output as JSON |
| `-o yaml` | Output as YAML |
| `-o wide` | Output with additional info |
| `--dry-run=client` | Preview without applying |
| `-l <key>=<value>` | Filter by label |
| `--all-namespaces` or `-A` | Across all namespaces |
