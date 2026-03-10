---
name: supabase
description: "Manage Supabase projects via CLI - projects, db, migrations, functions, storage, secrets. Use when user mentions 'supabase', 'supabase project', or wants to manage Supabase."
category: devtools
install_command: "npm i -g supabase"
---

# supabase

## Setup

```bash
npm i -g supabase
```

Verify installation:
```bash
supabase --version
```

Always use `--output json` flag when calling commands programmatically (where supported).

## Authentication

```bash
supabase login
```

## Resources

### Local Development

| Command | Description |
|---------|-------------|
| `supabase init` | Initialize a new Supabase project locally |
| `supabase start` | Start local Supabase stack (Postgres, Auth, Storage, etc.) |
| `supabase stop` | Stop local Supabase stack |
| `supabase status` | Show status of local Supabase services |

### Projects

| Command | Description |
|---------|-------------|
| `supabase projects list` | List all remote projects |
| `supabase link --project-ref <ref>` | Link local project to remote |

### Database

| Command | Description |
|---------|-------------|
| `supabase db push` | Push local migrations to remote database |
| `supabase db pull` | Pull remote schema changes into local migrations |
| `supabase db reset` | Reset local database to current migrations |
| `supabase db diff --schema public` | Diff local database against migrations |
| `supabase db lint` | Lint database for common issues |

### Migrations

| Command | Description |
|---------|-------------|
| `supabase migration new <name>` | Create a new migration file |
| `supabase migration list` | List all migrations and their status |
| `supabase migration repair --status applied <version>` | Repair migration history |

### Edge Functions

| Command | Description |
|---------|-------------|
| `supabase functions new <name>` | Create a new edge function |
| `supabase functions serve` | Serve functions locally |
| `supabase functions deploy <name>` | Deploy a function to remote |
| `supabase functions delete <name>` | Delete a remote function |
| `supabase functions list` | List all deployed functions |

### Type Generation

| Command | Description |
|---------|-------------|
| `supabase gen types typescript` | Generate TypeScript types from database schema |
| `supabase gen types typescript --local` | Generate types from local database |
| `supabase gen types typescript --project-id <ref>` | Generate types from remote project |

### Secrets

| Command | Description |
|---------|-------------|
| `supabase secrets list` | List all secrets |
| `supabase secrets set KEY=value` | Set a secret |
| `supabase secrets unset KEY` | Remove a secret |

### Storage

| Command | Description |
|---------|-------------|
| `supabase storage ls` | List storage buckets |
| `supabase storage ls s3://<bucket>` | List objects in a bucket |
| `supabase storage cp <local> s3://<bucket>/<path>` | Upload a file |
| `supabase storage rm s3://<bucket>/<path>` | Remove a file |

## Global Flags

| Flag | Description |
|------|-------------|
| `--output json` | Output result as JSON |
| `--project-ref <ref>` | Specify remote project reference |
| `--debug` | Enable debug output |
| `--workdir <path>` | Set working directory |
