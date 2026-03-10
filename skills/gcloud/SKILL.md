---
name: gcloud
description: "Google Cloud CLI - manage Compute Engine, Cloud Run, Cloud Functions, Cloud SQL, Storage. Use when user mentions 'gcloud', 'google cloud', 'gcp', or wants to interact with Google Cloud Platform."
category: devtools
install_command: "brew install google-cloud-sdk"
---

# gcloud

## Setup

```bash
brew install google-cloud-sdk
```

Verify installation:
```bash
gcloud --version
```

Use `--format=json` for machine-readable output.

## Authentication

```bash
gcloud auth login
```

For application default credentials:
```bash
gcloud auth application-default login
```

## Resources

### Configuration

| Command | Description |
|---------|-------------|
| `gcloud config set project <project-id>` | Set the active project |
| `gcloud config get project` | Get the active project |
| `gcloud config set compute/region <region>` | Set default compute region |
| `gcloud config set compute/zone <zone>` | Set default compute zone |
| `gcloud config list` | List all active configuration properties |
| `gcloud config configurations list` | List all named configurations |
| `gcloud config configurations activate <name>` | Switch to a named configuration |

### Projects

| Command | Description |
|---------|-------------|
| `gcloud projects list` | List all accessible projects |
| `gcloud projects describe <project-id>` | Show project details |
| `gcloud projects create <project-id>` | Create a new project |

### Compute Engine

| Command | Description |
|---------|-------------|
| `gcloud compute instances list` | List all VM instances |
| `gcloud compute instances create <name> --machine-type=e2-medium` | Create a VM instance |
| `gcloud compute instances start <name>` | Start an instance |
| `gcloud compute instances stop <name>` | Stop an instance |
| `gcloud compute instances delete <name>` | Delete an instance |
| `gcloud compute ssh <name>` | SSH into an instance |

### Cloud Run

| Command | Description |
|---------|-------------|
| `gcloud run deploy <service> --source .` | Deploy from source code |
| `gcloud run deploy <service> --image <image>` | Deploy a container image |
| `gcloud run deploy <service> --source . --allow-unauthenticated` | Deploy with public access |
| `gcloud run services list` | List all Cloud Run services |
| `gcloud run services describe <service>` | Show service details |
| `gcloud run services delete <service>` | Delete a service |

### Cloud Functions

| Command | Description |
|---------|-------------|
| `gcloud functions deploy <name> --runtime nodejs20 --trigger-http` | Deploy an HTTP function |
| `gcloud functions deploy <name> --trigger-topic <topic>` | Deploy with Pub/Sub trigger |
| `gcloud functions list` | List all functions |
| `gcloud functions describe <name>` | Show function details |
| `gcloud functions delete <name>` | Delete a function |
| `gcloud functions logs read <name>` | Read function logs |

### Cloud SQL

| Command | Description |
|---------|-------------|
| `gcloud sql instances list` | List all Cloud SQL instances |
| `gcloud sql instances describe <name>` | Show instance details |
| `gcloud sql instances create <name> --database-version=POSTGRES_15` | Create a PostgreSQL instance |
| `gcloud sql databases list --instance=<name>` | List databases in an instance |
| `gcloud sql connect <name> --user=postgres` | Connect to an instance |

### Cloud Storage

| Command | Description |
|---------|-------------|
| `gcloud storage ls` | List all buckets |
| `gcloud storage ls gs://<bucket>` | List objects in a bucket |
| `gcloud storage cp <file> gs://<bucket>/` | Upload a file |
| `gcloud storage cp gs://<bucket>/<object> .` | Download a file |
| `gcloud storage buckets create gs://<bucket>` | Create a bucket |

### App Engine

| Command | Description |
|---------|-------------|
| `gcloud app deploy` | Deploy application to App Engine |
| `gcloud app browse` | Open deployed app in browser |
| `gcloud app logs tail` | Tail application logs |

## Global Flags

| Flag | Description |
|------|-------------|
| `--format=json` | Output as JSON |
| `--format=table` | Output as table |
| `--project <id>` | Override active project |
| `--quiet` | Suppress interactive prompts |
| `--verbosity <level>` | Set log verbosity (debug, info, warning, error) |
