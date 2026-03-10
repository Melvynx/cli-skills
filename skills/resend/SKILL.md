---
name: resend
description: "Send and manage emails via Resend CLI - send emails, manage domains, api keys. Use when user mentions 'resend', 'send email', or wants to use Resend email API."
category: communication
install_command: "npm i -g resend"
---

# resend

## Setup

```bash
npm i -g resend
```

Verify installation:
```bash
resend --version
```

## Authentication

```bash
resend login
```

## Resources

### Emails

| Command | Description |
|---------|-------------|
| `resend emails send --from onboarding@resend.dev --to user@example.com --subject "Hello" --html "<p>Hi</p>"` | Send an email with HTML body |
| `resend emails send --from hi@example.com --to user@example.com --subject "Hello" --text "Plain text"` | Send a plain text email |
| `resend emails get <id>` | Get email details by ID |

### Domains

| Command | Description |
|---------|-------------|
| `resend domains list` | List all domains |
| `resend domains create --name example.com` | Add a domain |
| `resend domains verify <id>` | Verify a domain |
| `resend domains delete <id>` | Remove a domain |
| `resend domains get <id>` | Get domain details |

### API Keys

| Command | Description |
|---------|-------------|
| `resend api-keys list` | List all API keys |
| `resend api-keys create --name "My Key"` | Create a new API key |
| `resend api-keys delete <id>` | Delete an API key |

## Global Flags

| Flag | Description |
|------|-------------|
| `--api-key <key>` | Use a specific API key |
