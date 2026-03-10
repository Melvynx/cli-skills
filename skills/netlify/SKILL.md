---
name: netlify
description: "Deploy and manage Netlify sites via CLI - deploy, env, functions, sites, build. Use when user mentions 'netlify', 'netlify deploy', or wants to manage Netlify sites."
category: devtools
install_command: "npm i -g netlify-cli"
---

# netlify

## Setup

```bash
npm i -g netlify-cli
```

Verify installation:
```bash
netlify --version
```

Always use `--json` flag when calling commands programmatically (where supported).

## Authentication

```bash
netlify login
```

Check auth status:
```bash
netlify status
```

## Resources

### Sites

| Command | Description |
|---------|-------------|
| `netlify sites:list` | List all sites |
| `netlify sites:create` | Create a new site |
| `netlify sites:create --name <name>` | Create a site with a specific name |
| `netlify sites:delete <site-id>` | Delete a site |
| `netlify link` | Link current directory to a site |
| `netlify unlink` | Unlink current directory |
| `netlify open` | Open site in browser |
| `netlify open:admin` | Open site admin in browser |

### Deploy

| Command | Description |
|---------|-------------|
| `netlify deploy` | Create a draft deploy |
| `netlify deploy --prod` | Deploy to production |
| `netlify deploy --dir <path>` | Deploy a specific directory |
| `netlify deploy --prod --dir <path>` | Deploy specific directory to production |

### Environment Variables

| Command | Description |
|---------|-------------|
| `netlify env:list` | List all environment variables |
| `netlify env:set KEY value` | Set an environment variable |
| `netlify env:unset KEY` | Remove an environment variable |
| `netlify env:get KEY` | Get value of an environment variable |
| `netlify env:import .env` | Import variables from a .env file |

### Functions

| Command | Description |
|---------|-------------|
| `netlify functions:list` | List all functions |
| `netlify functions:create <name>` | Create a new function |
| `netlify functions:invoke <name>` | Invoke a function locally |
| `netlify functions:serve` | Serve functions locally |

### Local Development

| Command | Description |
|---------|-------------|
| `netlify dev` | Start local development server |
| `netlify dev --port 8888` | Start dev server on specific port |
| `netlify build` | Build the project locally |
| `netlify init` | Initialize a new Netlify project |

## Global Flags

| Flag | Description |
|------|-------------|
| `--json` | Output result as JSON |
| `--auth <token>` | Netlify auth token |
| `--site <id>` | Specify site ID |
| `--debug` | Enable debug output |
| `--httpProxy <url>` | Use HTTP proxy |
