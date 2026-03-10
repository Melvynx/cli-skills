---
name: planetscale
description: "PlanetScale database CLI - manage databases, branches, deploy requests, and connections. Use when user mentions 'planetscale', 'pscale', or wants to manage PlanetScale databases."
category: devtools
install_command: "brew install planetscale/tap/pscale"
binary: pscale
---

# pscale

## Setup

```bash
brew install planetscale/tap/pscale
```

Verify installation:
```bash
pscale version
```

Use `--format json` for machine-readable output.

## Authentication

```bash
pscale auth login
```

## Resources

### Databases

| Command | Description |
|---------|-------------|
| `pscale database list` | List all databases |
| `pscale database create <name>` | Create a new database |
| `pscale database create <name> --region us-east` | Create a database in a specific region |
| `pscale database show <name>` | Show database details |
| `pscale database delete <name>` | Delete a database |

### Branches

| Command | Description |
|---------|-------------|
| `pscale branch list <database>` | List all branches for a database |
| `pscale branch create <database> <branch>` | Create a new branch |
| `pscale branch show <database> <branch>` | Show branch details |
| `pscale branch delete <database> <branch>` | Delete a branch |
| `pscale branch diff <database> <branch>` | Show schema diff for a branch |
| `pscale branch schema <database> <branch>` | Show branch schema |

### Deploy Requests

| Command | Description |
|---------|-------------|
| `pscale deploy-request list <database>` | List all deploy requests |
| `pscale deploy-request create <database> <branch>` | Create a deploy request |
| `pscale deploy-request deploy <database> <number>` | Deploy a deploy request |
| `pscale deploy-request show <database> <number>` | Show deploy request details |
| `pscale deploy-request diff <database> <number>` | Show deploy request diff |
| `pscale deploy-request close <database> <number>` | Close a deploy request |

### Connections

| Command | Description |
|---------|-------------|
| `pscale connect <database> <branch>` | Connect to a database branch on a local port |
| `pscale connect <database> <branch> --port 3306` | Connect on a specific port |

### Passwords

| Command | Description |
|---------|-------------|
| `pscale password list <database> <branch>` | List all passwords for a branch |
| `pscale password create <database> <branch> <name>` | Create a new password |
| `pscale password delete <database> <branch> <id>` | Delete a password |

### Shell

| Command | Description |
|---------|-------------|
| `pscale shell <database> <branch>` | Open a MySQL shell to a branch |

## Global Flags

| Flag | Description |
|------|-------------|
| `--format json` | Output as JSON |
| `--org <name>` | Specify organization |
| `--service-token <token>` | Use service token for authentication |
| `--service-token-id <id>` | Service token ID |
