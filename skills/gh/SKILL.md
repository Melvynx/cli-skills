---
name: gh
description: "Manage GitHub via CLI - repos, issues, PRs, releases, gists, workflows. Use when user mentions 'gh', 'github cli', 'pull request', or wants to interact with GitHub."
category: devtools
install_command: "brew install gh"
---

# gh

## Setup

macOS:
```bash
brew install gh
```

Linux:
```bash
apt install gh
```

Verify installation:
```bash
gh --version
```

Always use `--json <fields>` flag when calling commands programmatically.

## Authentication

```bash
gh auth login
```

Check auth status:
```bash
gh auth status
```

## Resources

### Repos

| Command | Description |
|---------|-------------|
| `gh repo list` | List your repositories |
| `gh repo list <owner>` | List repos for a user or org |
| `gh repo create <name> --public` | Create a new public repo |
| `gh repo create <name> --private` | Create a new private repo |
| `gh repo clone <owner/repo>` | Clone a repository |
| `gh repo view <owner/repo>` | View repo details |
| `gh repo fork <owner/repo>` | Fork a repository |
| `gh repo delete <owner/repo> --yes` | Delete a repository |

### Pull Requests

| Command | Description |
|---------|-------------|
| `gh pr list` | List open pull requests |
| `gh pr list --state all` | List all pull requests |
| `gh pr create --title "Fix" --body "Description"` | Create a pull request |
| `gh pr view <number>` | View pull request details |
| `gh pr checkout <number>` | Check out a pull request locally |
| `gh pr merge <number>` | Merge a pull request |
| `gh pr merge <number> --squash` | Squash merge a pull request |
| `gh pr close <number>` | Close a pull request |
| `gh pr review <number> --approve` | Approve a pull request |
| `gh pr diff <number>` | View pull request diff |
| `gh pr checks <number>` | View CI checks status |

### Issues

| Command | Description |
|---------|-------------|
| `gh issue list` | List open issues |
| `gh issue create --title "Bug" --body "Description"` | Create an issue |
| `gh issue view <number>` | View issue details |
| `gh issue close <number>` | Close an issue |
| `gh issue reopen <number>` | Reopen an issue |
| `gh issue comment <number> --body "Comment"` | Add a comment |
| `gh issue edit <number> --add-label bug` | Add label to issue |

### Releases

| Command | Description |
|---------|-------------|
| `gh release list` | List releases |
| `gh release create v1.0.0` | Create a release |
| `gh release create v1.0.0 --generate-notes` | Create release with auto-generated notes |
| `gh release view <tag>` | View release details |
| `gh release download <tag>` | Download release assets |
| `gh release delete <tag>` | Delete a release |

### Workflows and Runs

| Command | Description |
|---------|-------------|
| `gh workflow list` | List workflows |
| `gh workflow run <name>` | Trigger a workflow |
| `gh run list` | List recent workflow runs |
| `gh run view <id>` | View run details |
| `gh run watch <id>` | Watch a run in progress |
| `gh run rerun <id>` | Rerun a workflow run |

### Gists

| Command | Description |
|---------|-------------|
| `gh gist list` | List your gists |
| `gh gist create file.txt` | Create a gist from a file |
| `gh gist create --public file.txt` | Create a public gist |
| `gh gist view <id>` | View a gist |
| `gh gist edit <id>` | Edit a gist |

### API

| Command | Description |
|---------|-------------|
| `gh api repos/{owner}/{repo}` | Make a GET request to the GitHub API |
| `gh api repos/{owner}/{repo}/issues --method POST --field title="Bug"` | Make a POST request |
| `gh api graphql -f query='{ viewer { login } }'` | Make a GraphQL query |

## Global Flags

| Flag | Description |
|------|-------------|
| `--json <fields>` | Output specific fields as JSON |
| `--jq <expression>` | Filter JSON output with jq |
| `--repo <owner/repo>` | Specify target repository |
| `--limit <n>` | Limit number of results |
| `--web` | Open in browser |
