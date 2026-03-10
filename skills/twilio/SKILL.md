---
name: twilio
description: "Twilio CLI - send SMS, make calls, manage phone numbers, view logs. Use when user mentions 'twilio', 'send sms', 'twilio api', or wants to interact with Twilio communication services."
category: communication
install_command: "npm i -g twilio-cli"
binary: twilio
---

# twilio

## Setup

```bash
npm i -g twilio-cli
```

Verify installation:
```bash
twilio --version
```

## Authentication

```bash
twilio login
```

## Resources

### Profiles

| Command | Description |
|---------|-------------|
| `twilio profiles list` | List all configured profiles |
| `twilio profiles use <name>` | Switch to a profile |
| `twilio profiles create` | Create a new profile |
| `twilio profiles remove <name>` | Remove a profile |

### Phone Numbers

| Command | Description |
|---------|-------------|
| `twilio phone-numbers list` | List all phone numbers |
| `twilio phone-numbers buy --country-code US --type local` | Buy a phone number |
| `twilio phone-numbers update <sid> --sms-url <url>` | Update SMS webhook for a number |

### Messages

| Command | Description |
|---------|-------------|
| `twilio api core messages create --from <from> --to <to> --body "Hello"` | Send an SMS |
| `twilio api core messages list` | List recent messages |
| `twilio api core messages list --limit 10` | List messages with limit |
| `twilio api core messages fetch --sid <sid>` | Get a specific message |

### Calls

| Command | Description |
|---------|-------------|
| `twilio api core calls create --from <from> --to <to> --url <twiml-url>` | Make a phone call |
| `twilio api core calls list` | List recent calls |
| `twilio api core calls fetch --sid <sid>` | Get a specific call |

### Debugging

| Command | Description |
|---------|-------------|
| `twilio debugger logs list` | List recent debugging logs |
| `twilio debugger logs list --log-level error` | List only error logs |

### Plugins

| Command | Description |
|---------|-------------|
| `twilio plugins` | List installed plugins |
| `twilio plugins install <name>` | Install a plugin |
| `twilio plugins remove <name>` | Remove a plugin |

## Global Flags

| Flag | Description |
|------|-------------|
| `-o json` | Output as JSON |
| `--silent` | Suppress output |
| `--profile <name>` | Use a specific profile |
| `-l debug` | Enable debug logging |
