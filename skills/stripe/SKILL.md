---
name: stripe
description: "Manage Stripe payments via CLI - listen for webhooks, trigger events, manage resources, view logs. Use when user mentions 'stripe', 'stripe cli', 'webhook testing', or wants to interact with Stripe API."
category: finance
install_command: "brew install stripe/stripe-cli/stripe"
---

# stripe

## Setup

macOS:
```bash
brew install stripe/stripe-cli/stripe
```

Or download from https://stripe.com/docs/stripe-cli for other platforms.

Verify installation:
```bash
stripe --version
```

Always use `--json` flag when calling commands programmatically (where supported).

## Authentication

```bash
stripe login
```

## Resources

### Webhooks

| Command | Description |
|---------|-------------|
| `stripe listen --forward-to localhost:3000/api/webhooks` | Forward webhook events to local server |
| `stripe listen --events payment_intent.succeeded,checkout.session.completed --forward-to localhost:3000/api/webhooks` | Listen for specific events only |
| `stripe trigger payment_intent.succeeded` | Trigger a test webhook event |
| `stripe trigger checkout.session.completed` | Trigger a checkout session event |
| `stripe webhook_endpoints list` | List registered webhook endpoints |

### Customers

| Command | Description |
|---------|-------------|
| `stripe customers list` | List all customers |
| `stripe customers list --limit 5` | List customers with limit |
| `stripe customers create --email user@test.com` | Create a customer |
| `stripe customers retrieve <id>` | Get a customer by ID |
| `stripe customers delete <id>` | Delete a customer |

### Payments

| Command | Description |
|---------|-------------|
| `stripe payments list` | List all payment intents |
| `stripe charges list --limit 5` | List recent charges |
| `stripe payment_intents create --amount 2000 --currency usd` | Create a payment intent |
| `stripe refunds create --charge <charge_id>` | Refund a charge |

### Products and Prices

| Command | Description |
|---------|-------------|
| `stripe products list` | List all products |
| `stripe products create --name "My Product"` | Create a product |
| `stripe prices list` | List all prices |
| `stripe prices create --product <id> --unit-amount 2000 --currency usd --recurring[interval]=month` | Create a recurring price |

### Subscriptions

| Command | Description |
|---------|-------------|
| `stripe subscriptions list` | List all subscriptions |
| `stripe subscriptions create --customer <id> --price <id>` | Create a subscription |
| `stripe subscriptions cancel <id>` | Cancel a subscription |

### Events and Logs

| Command | Description |
|---------|-------------|
| `stripe events list` | List recent events |
| `stripe events retrieve <id>` | Get event details |
| `stripe logs tail` | Tail API request logs in realtime |

### Resources

| Command | Description |
|---------|-------------|
| `stripe resources` | List all available API resources |

### Config

| Command | Description |
|---------|-------------|
| `stripe config --list` | Show current configuration |

## Global Flags

| Flag | Description |
|------|-------------|
| `--json` | Output result as JSON |
| `--api-key <key>` | Specify API key |
| `--stripe-account <id>` | Specify connected account |
| `--limit <n>` | Limit number of results |
| `--color off` | Disable colored output |
