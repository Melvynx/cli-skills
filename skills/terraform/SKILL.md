---
name: terraform
description: "Infrastructure as Code CLI - plan, apply, destroy infrastructure, manage state and workspaces. Use when user mentions 'terraform', 'infrastructure as code', 'IaC', or wants to manage cloud infrastructure declaratively."
category: devtools
install_command: "brew install terraform"
---

# terraform

## Setup

```bash
brew install terraform
```

Verify installation:
```bash
terraform --version
```

## Resources

### Workflow

| Command | Description |
|---------|-------------|
| `terraform init` | Initialize working directory and download providers |
| `terraform init -upgrade` | Upgrade providers to latest allowed versions |
| `terraform plan` | Preview changes without applying |
| `terraform plan -out=tfplan` | Save plan to a file |
| `terraform apply` | Apply changes with confirmation prompt |
| `terraform apply -auto-approve` | Apply changes without confirmation |
| `terraform apply tfplan` | Apply a saved plan file |
| `terraform destroy` | Destroy all managed infrastructure |
| `terraform destroy -auto-approve` | Destroy without confirmation |
| `terraform destroy -target=aws_instance.example` | Destroy a specific resource |

### Validation and Formatting

| Command | Description |
|---------|-------------|
| `terraform fmt` | Format configuration files |
| `terraform fmt -recursive` | Format files in all subdirectories |
| `terraform fmt -check` | Check formatting without modifying |
| `terraform validate` | Validate configuration syntax |

### State Management

| Command | Description |
|---------|-------------|
| `terraform show` | Show current state or a saved plan |
| `terraform show -json` | Show state as JSON |
| `terraform state list` | List all resources in state |
| `terraform state show <resource>` | Show details of a resource in state |
| `terraform state mv <source> <destination>` | Move a resource in state |
| `terraform state rm <resource>` | Remove a resource from state |
| `terraform state pull` | Pull remote state to stdout |
| `terraform state push` | Push local state to remote |

### Import and Output

| Command | Description |
|---------|-------------|
| `terraform import <resource> <id>` | Import existing infrastructure into state |
| `terraform output` | Show all output values |
| `terraform output <name>` | Show a specific output value |
| `terraform output -json` | Show outputs as JSON |

### Workspaces

| Command | Description |
|---------|-------------|
| `terraform workspace list` | List all workspaces |
| `terraform workspace show` | Show current workspace |
| `terraform workspace new <name>` | Create a new workspace |
| `terraform workspace select <name>` | Switch to a workspace |
| `terraform workspace delete <name>` | Delete a workspace |

### Other

| Command | Description |
|---------|-------------|
| `terraform graph` | Generate a visual dependency graph |
| `terraform providers` | Show required providers |
| `terraform refresh` | Refresh state against real infrastructure |
| `terraform taint <resource>` | Mark a resource for recreation |
| `terraform untaint <resource>` | Remove taint from a resource |

## Global Flags

| Flag | Description |
|------|-------------|
| `-var 'key=value'` | Set a variable value |
| `-var-file=<file>` | Load variables from a file |
| `-target=<resource>` | Target a specific resource |
| `-parallelism=<n>` | Limit concurrent operations |
| `-json` | Output in JSON format |
| `-no-color` | Disable colored output |
