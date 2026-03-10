---
name: az
description: "Azure CLI - manage VMs, web apps, functions, storage, AKS, and other Azure services. Use when user mentions 'az', 'azure', or wants to interact with Microsoft Azure."
category: devtools
install_command: "brew install azure-cli"
binary: az
---

# az

## Setup

```bash
brew install azure-cli
```

Verify installation:
```bash
az --version
```

Use `-o json` for machine-readable output.

## Authentication

```bash
az login
```

## Resources

### Account and Subscription

| Command | Description |
|---------|-------------|
| `az account show` | Show current subscription details |
| `az account list` | List all subscriptions |
| `az account set --subscription <id>` | Switch active subscription |

### Resource Groups

| Command | Description |
|---------|-------------|
| `az group list` | List all resource groups |
| `az group create --name <name> --location eastus` | Create a resource group |
| `az group delete --name <name>` | Delete a resource group |
| `az group show --name <name>` | Show resource group details |

### Virtual Machines

| Command | Description |
|---------|-------------|
| `az vm list` | List all VMs |
| `az vm list -d` | List VMs with details (IPs, power state) |
| `az vm create --resource-group <rg> --name <name> --image Ubuntu2204` | Create a VM |
| `az vm start --resource-group <rg> --name <name>` | Start a VM |
| `az vm stop --resource-group <rg> --name <name>` | Stop a VM |
| `az vm delete --resource-group <rg> --name <name>` | Delete a VM |
| `az vm show --resource-group <rg> --name <name>` | Show VM details |

### Web Apps

| Command | Description |
|---------|-------------|
| `az webapp list` | List all web apps |
| `az webapp create --resource-group <rg> --plan <plan> --name <name> --runtime "NODE:20-lts"` | Create a web app |
| `az webapp deploy --resource-group <rg> --name <name> --src-path <file>` | Deploy to a web app |
| `az webapp show --resource-group <rg> --name <name>` | Show web app details |
| `az webapp log tail --resource-group <rg> --name <name>` | Tail web app logs |
| `az webapp delete --resource-group <rg> --name <name>` | Delete a web app |

### Function Apps

| Command | Description |
|---------|-------------|
| `az functionapp list` | List all function apps |
| `az functionapp create --resource-group <rg> --consumption-plan-location eastus --runtime node --name <name> --storage-account <sa>` | Create a function app |
| `az functionapp show --resource-group <rg> --name <name>` | Show function app details |
| `az functionapp delete --resource-group <rg> --name <name>` | Delete a function app |

### Storage

| Command | Description |
|---------|-------------|
| `az storage account list` | List all storage accounts |
| `az storage account create --name <name> --resource-group <rg> --sku Standard_LRS` | Create a storage account |
| `az storage container list --account-name <name>` | List blob containers |
| `az storage blob upload --account-name <name> --container-name <c> --file <file> --name <blob>` | Upload a blob |

### AKS (Kubernetes)

| Command | Description |
|---------|-------------|
| `az aks list` | List all AKS clusters |
| `az aks create --resource-group <rg> --name <name> --node-count 3` | Create an AKS cluster |
| `az aks get-credentials --resource-group <rg> --name <name>` | Get cluster credentials for kubectl |
| `az aks show --resource-group <rg> --name <name>` | Show cluster details |
| `az aks delete --resource-group <rg> --name <name>` | Delete an AKS cluster |

## Global Flags

| Flag | Description |
|------|-------------|
| `-o json` | Output as JSON |
| `-o table` | Output as table |
| `-o tsv` | Output as tab-separated values |
| `--query <expression>` | JMESPath query for filtering output |
| `--subscription <id>` | Override active subscription |
| `--verbose` | Enable verbose output |
| `--debug` | Enable debug output |
