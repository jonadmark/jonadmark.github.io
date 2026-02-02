# Docker Development Guide

This guide shows you how to run this Jekyll site in a Docker container.

## Prerequisites

- Docker Desktop installed ([download here](https://www.docker.com/products/docker-desktop))
- Docker Compose (included with Docker Desktop)

## Quick Start

### Option 1: Using Docker Compose (Recommended)

This is the easiest way - just run:

```bash
docker-compose up
```

The site will be available at: **http://localhost:4000**

Press `Ctrl+C` to stop the server.

### Option 2: Using Docker Directly

Build the image:
```bash
docker build -t personal-website .
```

Run the container:
```bash
docker run -p 4000:4000 -p 35729:35729 -v $(pwd):/srv/jekyll personal-website
```

## Development Workflow

### Starting the Server

```bash
docker-compose up
```

The site will automatically rebuild when files are edited and saved!

### Stopping the Server

Press `Ctrl+C` or run:
```bash
docker-compose down
```

### Running in Background

```bash
docker-compose up -d
```

View logs:
```bash
docker-compose logs -f
```

Stop:
```bash
docker-compose down
```

### Rebuilding After Dependency Changes

If the `Gemfile` is modified to add/remove dependencies:

```bash
docker-compose down
docker-compose build
docker-compose up
```

## How It Works

- **Port 4000**: This website
- **Port 35729**: LiveReload (auto-refresh browser on changes)
- **Volume Mount**: The local files are mounted, so changes are reflected immediately
- **Bundle Cache**: Dependencies are cached in a Docker volume for faster rebuilds

## Useful Commands

```bash
# View running containers
docker ps

# Execute commands in the container
docker-compose exec jekyll bundle install

# Build the site without serving
docker-compose run jekyll bundle exec jekyll build

# Clean build artifacts
docker-compose run jekyll bundle exec jekyll clean

# Remove all containers and volumes
docker-compose down -v
```

## Troubleshooting

### Port Already in Use

If port 4000 is already taken, edit `docker-compose.yml`:
```yaml
ports:
  - "4001:4000"  # Use port 4001 instead
```

### Changes Not Reflecting

Try:
```bash
docker-compose restart
```

Or rebuild:
```bash
docker-compose down
docker-compose up --build
```

### Permission Issues (Linux/macOS)

If you get permission errors, run:
```bash
docker-compose run --user $(id -u):$(id -g) jekyll bundle install
```

## Production Build

To build the static site for deployment:

```bash
docker-compose run jekyll bundle exec jekyll build
```

The generated site will be in the `_site/` folder.
