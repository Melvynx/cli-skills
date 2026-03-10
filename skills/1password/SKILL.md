---
name: 1password
description: "1Password CLI - manage secrets, vaults, items, inject credentials into commands. Use when user mentions '1password', 'op', 'secrets management', or wants to manage passwords and secrets via CLI."
category: productivity
install_command: "brew install 1password-cli"
binary: op
---

# op

## Setup

```bash
brew install 1password-cli
```

Verify installation:
```bash
op --version
```

Use `--format json` for machine-readable output.

## Authentication

```bash
op signin
```

For service accounts, set the `OP_SERVICE_ACCOUNT_TOKEN` environment variable.

## Resources

### Items

| Command | Description |
|---------|-------------|
| `op item list` | List all items |
| `op item list --vault <vault>` | List items in a specific vault |
| `op item get <name-or-id>` | Get an item by name or ID |
| `op item get <name> --fields label=password` | Get a specific field from an item |
| `op item create --category login --title <title> --vault <vault>` | Create a new item |
| `op item edit <name> password=newvalue` | Edit an item field |
| `op item delete <name>` | Delete an item |

### Vaults

| Command | Description |
|---------|-------------|
| `op vault list` | List all vaults |
| `op vault get <name>` | Get vault details |
| `op vault create <name>` | Create a new vault |
| `op vault delete <name>` | Delete a vault |

### Documents

| Command | Description |
|---------|-------------|
| `op document list` | List all documents |
| `op document get <name>` | Download a document |
| `op document create <file> --title <title>` | Upload a document |
| `op document delete <name>` | Delete a document |

### Secrets Injection

| Command | Description |
|---------|-------------|
| `op inject -i template.env -o .env` | Inject secrets from a template into a file |
| `op run -- <command>` | Run a command with secrets injected as env vars |
| `op run --env-file .env -- <command>` | Run with secrets from env file |
| `op read "op://vault/item/field"` | Read a single secret reference |

### Account

| Command | Description |
|---------|-------------|
| `op account list` | List configured accounts |
| `op account get` | Get current account details |
| `op whoami` | Show current signed-in user |

## Global Flags

| Flag | Description |
|------|-------------|
| `--format json` | Output as JSON |
| `--vault <vault>` | Specify vault |
| `--account <account>` | Specify account |
| `--cache` | Enable response caching |
| `--no-newline` | Do not append newline to output |
