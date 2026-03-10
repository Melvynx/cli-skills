---
name: figma
description: "Figma Code Connect CLI - connect design components to code, publish connections, parse Figma files. Use when user mentions 'figma', 'code connect', 'figma cli', or wants to link Figma designs to code."
category: devtools
install_command: "npm i -g @figma/code-connect"
binary: figma
---

# figma

## Setup

```bash
npm i -g @figma/code-connect
```

Or use as a dev dependency:
```bash
npm i -D @figma/code-connect
npx figma
```

## Authentication

Set the `FIGMA_ACCESS_TOKEN` environment variable with a personal access token from Figma account settings.

## Resources

### Code Connect

| Command | Description |
|---------|-------------|
| `figma connect` | Interactive setup for Code Connect in a project |
| `figma connect create <figma-url>` | Create a Code Connect file for a Figma component |
| `figma connect publish` | Publish all Code Connect files to Figma |
| `figma connect publish --dry-run` | Preview what would be published |
| `figma connect unpublish` | Remove published Code Connect data |

### Parsing

| Command | Description |
|---------|-------------|
| `figma connect parse` | Parse Code Connect files in the project |
| `figma connect parse --dir <path>` | Parse files in a specific directory |

## Global Flags

| Flag | Description |
|------|-------------|
| `--dir <path>` | Specify project directory |
| `--config <path>` | Path to configuration file |
| `--verbose` | Enable verbose output |
