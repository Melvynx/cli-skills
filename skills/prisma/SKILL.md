---
name: prisma
description: "Database ORM CLI - manage migrations, generate client, introspect databases, seed data. Use when user mentions 'prisma', 'database migration', 'prisma schema', or wants to interact with Prisma ORM."
category: devtools
install_command: "npm i -g prisma"
---

# prisma

## Setup

```bash
npm i -g prisma
```

Verify installation:
```bash
prisma --version
```

## Resources

### Project Setup

| Command | Description |
|---------|-------------|
| `prisma init` | Initialize Prisma in a project |
| `prisma init --datasource-provider postgresql` | Initialize with a specific database provider |
| `prisma init --datasource-provider sqlite` | Initialize with SQLite |

### Client Generation

| Command | Description |
|---------|-------------|
| `prisma generate` | Generate Prisma Client from schema |
| `prisma generate --watch` | Watch schema and regenerate on changes |

### Migrations

| Command | Description |
|---------|-------------|
| `prisma migrate dev` | Create and apply a migration in development |
| `prisma migrate dev --name init` | Create a named migration |
| `prisma migrate dev --create-only` | Create migration file without applying |
| `prisma migrate deploy` | Apply pending migrations in production |
| `prisma migrate reset` | Reset database and apply all migrations |
| `prisma migrate status` | Check migration status |
| `prisma migrate resolve --applied <name>` | Mark a migration as applied |

### Database Management

| Command | Description |
|---------|-------------|
| `prisma db push` | Push schema changes without creating a migration |
| `prisma db pull` | Introspect database and update schema |
| `prisma db seed` | Run the seed script |
| `prisma db execute --file ./script.sql` | Execute raw SQL against the database |

### Studio

| Command | Description |
|---------|-------------|
| `prisma studio` | Open Prisma Studio GUI on port 5555 |
| `prisma studio --port 3001` | Open Prisma Studio on a custom port |

### Schema Tools

| Command | Description |
|---------|-------------|
| `prisma format` | Format the Prisma schema file |
| `prisma validate` | Validate the Prisma schema file |

## Global Flags

| Flag | Description |
|------|-------------|
| `--schema <path>` | Path to Prisma schema file |
| `--help` | Show help for a command |
