---
name: linear
description: "Linear CLI - manage issues, teams, projects, and cycles from the terminal. Use when user mentions 'linear', 'linear issues', or wants to interact with Linear project management."
category: productivity
install_command: "npm i -g @linear/cli"
binary: linear
---

# linear

## Setup

```bash
npm i -g @linear/cli
```

Verify installation:
```bash
linear --version
```

## Authentication

Set the `LINEAR_API_KEY` environment variable with a personal API key from Linear settings.

## Resources

### Issues

| Command | Description |
|---------|-------------|
| `linear issue list` | List issues assigned to you |
| `linear issue list --team <team>` | List issues for a specific team |
| `linear issue list --state "In Progress"` | List issues by state |
| `linear issue create --title "Bug fix" --team <team>` | Create a new issue |
| `linear issue create --title "Feature" --team <team> --priority urgent` | Create issue with priority |
| `linear issue update <id> --state "Done"` | Update issue state |
| `linear issue update <id> --assignee <user>` | Assign an issue |

### Teams

| Command | Description |
|---------|-------------|
| `linear team list` | List all teams |

### Projects

| Command | Description |
|---------|-------------|
| `linear project list` | List all projects |

### Cycles

| Command | Description |
|---------|-------------|
| `linear cycle list` | List all cycles |
| `linear cycle list --team <team>` | List cycles for a specific team |
