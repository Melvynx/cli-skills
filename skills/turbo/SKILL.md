---
name: turbo
description: "Turborepo CLI - run tasks across monorepo packages, prune dependencies, generate packages. Use when user mentions 'turbo', 'turborepo', 'monorepo build', or wants to manage a Turborepo monorepo."
category: devtools
install_command: "npm i -g turbo"
---

# turbo

## Setup

```bash
npm i -g turbo
```

Verify installation:
```bash
turbo --version
```

Requires a `turbo.json` configuration file in the project root.

## Authentication

```bash
turbo login
```

Link to a Vercel team for remote caching:
```bash
turbo link
```

## Resources

### Running Tasks

| Command | Description |
|---------|-------------|
| `turbo run build` | Run build task across all packages |
| `turbo run test` | Run test task across all packages |
| `turbo run lint` | Run lint task across all packages |
| `turbo run build test lint` | Run multiple tasks |
| `turbo run build --filter=<package>` | Run task for a specific package |
| `turbo run build --filter=<package>...` | Run task for a package and its dependencies |
| `turbo run build --filter=...<package>` | Run task for a package and its dependents |
| `turbo run build --filter='[HEAD~1]'` | Run task only for changed packages |
| `turbo run build --dry-run` | Preview which tasks would run |
| `turbo run build --graph` | Generate a task dependency graph |
| `turbo run build --force` | Force execution, ignoring cache |
| `turbo run build --concurrency=4` | Limit parallel task execution |
| `turbo run build --continue` | Continue running even if a task fails |

### Pruning

| Command | Description |
|---------|-------------|
| `turbo prune <package>` | Generate a sparse monorepo for a specific package |
| `turbo prune <package> --docker` | Generate pruned output optimized for Docker |

### Code Generation

| Command | Description |
|---------|-------------|
| `turbo gen` | Run a generator |
| `turbo gen workspace` | Generate a new workspace package |
| `turbo gen workspace --name <name>` | Generate a named workspace package |

### Daemon

| Command | Description |
|---------|-------------|
| `turbo daemon status` | Show daemon status |
| `turbo daemon start` | Start the turbo daemon |
| `turbo daemon stop` | Stop the turbo daemon |

### Remote Caching

| Command | Description |
|---------|-------------|
| `turbo login` | Login to remote cache provider |
| `turbo link` | Link project to remote cache |
| `turbo unlink` | Unlink project from remote cache |

## Global Flags

| Flag | Description |
|------|-------------|
| `--filter=<pattern>` | Filter packages to run tasks on |
| `--force` | Ignore cache and force execution |
| `--dry-run` | Preview tasks without executing |
| `--concurrency=<n>` | Set max parallel tasks |
| `--graph` | Generate a dependency graph |
| `--output-logs=<mode>` | Control log output (full, hash-only, new-only, none) |
| `--env-mode=<mode>` | Control environment variable handling (strict, loose) |
