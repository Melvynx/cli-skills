---
name: docker
description: "Container platform CLI - build images, run containers, manage compose stacks, volumes, networks. Use when user mentions 'docker', 'container', 'docker compose', or wants to manage containers."
category: devtools
install_command: "brew install docker"
---

# docker

## Setup

macOS:
```bash
brew install docker
```

Or download Docker Desktop from https://docker.com

Verify installation:
```bash
docker --version
```

## Resources

### Containers

| Command | Description |
|---------|-------------|
| `docker run <image>` | Run a container from an image |
| `docker run -d -p 8080:80 --name myapp nginx` | Run detached with port mapping and name |
| `docker run -it --rm ubuntu bash` | Run interactive container and remove on exit |
| `docker run -v $(pwd):/app -w /app node:20 npm start` | Run with volume mount and working directory |
| `docker run --env-file .env <image>` | Run with environment variables from file |
| `docker ps` | List running containers |
| `docker ps -a` | List all containers including stopped |
| `docker stop <container>` | Stop a running container |
| `docker rm <container>` | Remove a stopped container |
| `docker rm -f <container>` | Force remove a running container |
| `docker exec -it <container> bash` | Open a shell in a running container |
| `docker exec <container> <command>` | Execute a command in a running container |
| `docker logs <container>` | View container logs |
| `docker logs -f <container>` | Follow container logs in realtime |
| `docker logs --tail 100 <container>` | Show last 100 lines of logs |

### Images

| Command | Description |
|---------|-------------|
| `docker build -t myapp .` | Build an image from Dockerfile |
| `docker build -t myapp:v1 -f Dockerfile.prod .` | Build with tag and custom Dockerfile |
| `docker images` | List local images |
| `docker pull <image>` | Pull an image from registry |
| `docker push <image>` | Push an image to registry |
| `docker rmi <image>` | Remove a local image |
| `docker tag <image> <new-tag>` | Tag an image |

### Docker Compose

| Command | Description |
|---------|-------------|
| `docker compose up` | Start all services defined in compose file |
| `docker compose up -d` | Start services in detached mode |
| `docker compose up --build` | Rebuild images before starting |
| `docker compose down` | Stop and remove containers, networks |
| `docker compose down -v` | Stop and remove including volumes |
| `docker compose build` | Build or rebuild services |
| `docker compose ps` | List running compose services |
| `docker compose logs -f` | Follow logs for all services |
| `docker compose exec <service> bash` | Open a shell in a service container |
| `docker compose pull` | Pull latest images for services |

### Volumes and Networks

| Command | Description |
|---------|-------------|
| `docker volume ls` | List all volumes |
| `docker volume create <name>` | Create a named volume |
| `docker volume rm <name>` | Remove a volume |
| `docker volume prune` | Remove unused volumes |
| `docker network ls` | List all networks |
| `docker network create <name>` | Create a network |
| `docker network rm <name>` | Remove a network |

### System

| Command | Description |
|---------|-------------|
| `docker system prune` | Remove unused data (containers, images, networks) |
| `docker system prune -a --volumes` | Remove all unused data including volumes |
| `docker system df` | Show disk usage |

## Global Flags

| Flag | Description |
|------|-------------|
| `--format` | Format output using Go templates or json |
| `--quiet` | Only display IDs |
| `--no-trunc` | Do not truncate output |
