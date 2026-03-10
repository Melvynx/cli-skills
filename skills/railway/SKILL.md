---
name: railway
description: "Deploy and manage Railway services via CLI - projects, services, deployments, variables, volumes. Use when user mentions 'railway', 'railway deploy', or wants to deploy on Railway."
category: devtools
install_command: "npm i -g @railway/cli"
---

# railway

## Setup

```bash
npm i -g @railway/cli
```

Verify installation:
```bash
railway --version
```

Always use `--json` flag when calling commands programmatically (where supported).

## Authentication

```bash
railway login
```

Check auth status:
```bash
railway whoami
```

## Resources

### Projects

| Command | Description |
|---------|-------------|
| `railway init` | Create a new Railway project |
| `railway link` | Link current directory to an existing project |
| `railway unlink` | Unlink current directory from a project |
| `railway status` | Show current project and environment status |

### Deployments

| Command | Description |
|---------|-------------|
| `railway up` | Deploy current directory |
| `railway deploy` | Deploy with build logs |
| `railway logs` | View deployment logs |
| `railway logs --follow` | Stream deployment logs |

### Variables

| Command | Description |
|---------|-------------|
| `railway variables` | List all environment variables |
| `railway variables set KEY=value` | Set an environment variable |
| `railway variables delete KEY` | Delete an environment variable |

### Services

| Command | Description |
|---------|-------------|
| `railway service` | Select a service in the current project |
| `railway domain` | Generate or show a service domain |

### Run

| Command | Description |
|---------|-------------|
| `railway run <command>` | Run a command with Railway environment variables injected |
| `railway shell` | Open a shell with Railway environment variables |

## Global Flags

| Flag | Description |
|------|-------------|
| `--json` | Output result as JSON |
| `--environment <name>` | Specify environment |
| `--service <name>` | Specify service |
