---
name: drizzle-kit
description: "Drizzle ORM toolkit CLI - generate migrations, push schema, introspect databases, run studio. Use when user mentions 'drizzle', 'drizzle-kit', or wants to manage database schema with Drizzle ORM."
category: devtools
install_command: "npm i -g drizzle-kit"
---

# drizzle-kit

## Setup

```bash
npm i -g drizzle-kit
```

Or use as a dev dependency:
```bash
npm i -D drizzle-kit
npx drizzle-kit
```

Verify installation:
```bash
drizzle-kit --version
```

Requires a `drizzle.config.ts` file in the project root.

## Resources

### Migrations

| Command | Description |
|---------|-------------|
| `drizzle-kit generate` | Generate SQL migration files from schema changes |
| `drizzle-kit generate --name init` | Generate a named migration |
| `drizzle-kit migrate` | Apply pending migrations |
| `drizzle-kit drop` | Drop a previously generated migration |
| `drizzle-kit up` | Upgrade previously generated migrations to a newer format |
| `drizzle-kit check` | Check for consistency between schema and migration files |

### Database Operations

| Command | Description |
|---------|-------------|
| `drizzle-kit push` | Push schema changes directly to the database without generating migrations |
| `drizzle-kit pull` | Introspect the database and generate schema files |

### Studio

| Command | Description |
|---------|-------------|
| `drizzle-kit studio` | Open Drizzle Studio GUI for database browsing |
| `drizzle-kit studio --port 3001` | Open studio on a custom port |

## Global Flags

| Flag | Description |
|------|-------------|
| `--config <path>` | Path to drizzle config file |
| `--dialect <dialect>` | Database dialect (postgresql, mysql, sqlite) |
| `--verbose` | Enable verbose output |
