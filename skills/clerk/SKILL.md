---
name: clerk
description: "Clerk authentication CLI - set up auth, pull environment variables. Use when user mentions 'clerk', 'clerk auth', or wants to configure Clerk authentication."
category: devtools
install_command: "npm i -g @clerk/clerk-sdk-node"
---

# clerk

## Setup

```bash
npm i -g @clerk/clerk-sdk-node
```

Or use via npx:
```bash
npx @clerk/cli
```

## Resources

### Project Setup

| Command | Description |
|---------|-------------|
| `npx @clerk/cli setup` | Initialize Clerk in a project |
| `npx @clerk/cli env pull` | Pull environment variables from Clerk dashboard |
| `npx @clerk/cli env pull --env-file .env.local` | Pull env vars to a specific file |

### Development

| Command | Description |
|---------|-------------|
| `npx @clerk/cli dev` | Start development with Clerk |

## Environment Variables

After running `env pull`, the following variables are typically set:

- `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY` - Public key for frontend
- `CLERK_SECRET_KEY` - Secret key for backend
- `NEXT_PUBLIC_CLERK_SIGN_IN_URL` - Sign-in page URL
- `NEXT_PUBLIC_CLERK_SIGN_UP_URL` - Sign-up page URL
