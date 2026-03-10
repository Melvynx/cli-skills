---
name: wrangler
description: "Manage Cloudflare Workers via CLI - deploy, dev, kv, r2, d1, queues, secrets. Use when user mentions 'wrangler', 'cloudflare workers', 'workers', or wants to deploy to Cloudflare."
category: devtools
install_command: "npm i -g wrangler"
---

# wrangler

## Setup

```bash
npm i -g wrangler
```

Verify installation:
```bash
wrangler --version
```

Always use `--json` flag when calling commands programmatically (where supported).

## Authentication

```bash
wrangler login
```

Check auth status:
```bash
wrangler whoami
```

## Resources

### Workers

| Command | Description |
|---------|-------------|
| `wrangler init` | Initialize a new Worker project |
| `wrangler dev` | Start local development server |
| `wrangler deploy` | Deploy Worker to Cloudflare |
| `wrangler publish` | Publish Worker (alias for deploy) |
| `wrangler tail` | Stream realtime logs from deployed Worker |
| `wrangler delete` | Delete a deployed Worker |

### Secrets

| Command | Description |
|---------|-------------|
| `wrangler secret put SECRET_NAME` | Set a secret (prompts for value) |
| `wrangler secret list` | List all secrets |
| `wrangler secret delete SECRET_NAME` | Delete a secret |

### KV (Key-Value Storage)

| Command | Description |
|---------|-------------|
| `wrangler kv namespace list` | List all KV namespaces |
| `wrangler kv namespace create <name>` | Create a KV namespace |
| `wrangler kv namespace delete --namespace-id <id>` | Delete a KV namespace |
| `wrangler kv key put --namespace-id <id> <key> <value>` | Put a key-value pair |
| `wrangler kv key get --namespace-id <id> <key>` | Get a value by key |
| `wrangler kv key delete --namespace-id <id> <key>` | Delete a key |
| `wrangler kv key list --namespace-id <id>` | List all keys in a namespace |

### R2 (Object Storage)

| Command | Description |
|---------|-------------|
| `wrangler r2 bucket list` | List all R2 buckets |
| `wrangler r2 bucket create <name>` | Create an R2 bucket |
| `wrangler r2 bucket delete <name>` | Delete an R2 bucket |
| `wrangler r2 object get <bucket>/<key>` | Download an object |
| `wrangler r2 object put <bucket>/<key> --file <path>` | Upload an object |
| `wrangler r2 object delete <bucket>/<key>` | Delete an object |

### D1 (SQLite Database)

| Command | Description |
|---------|-------------|
| `wrangler d1 list` | List all D1 databases |
| `wrangler d1 create <name>` | Create a D1 database |
| `wrangler d1 delete <name>` | Delete a D1 database |
| `wrangler d1 execute <name> --command "SELECT * FROM users"` | Run SQL command |
| `wrangler d1 execute <name> --file schema.sql` | Execute SQL from file |
| `wrangler d1 info <name>` | Show database details |

### Pages

| Command | Description |
|---------|-------------|
| `wrangler pages deploy <directory>` | Deploy a Pages project |
| `wrangler pages project list` | List Pages projects |
| `wrangler pages project create <name>` | Create a Pages project |
| `wrangler pages deployment list --project-name <name>` | List deployments |

## Global Flags

| Flag | Description |
|------|-------------|
| `--json` | Output result as JSON |
| `--config <path>` | Path to wrangler.toml config file |
| `--env <name>` | Specify environment |
| `--compatibility-date <date>` | Set compatibility date |
