# ollama-docker

## Description
This repository contains configuration files to start two Docker containers: one for [Ollama](https://github.com/ollama/ollama) and one for [Open WebUI](https://github.com/open-webui/open-webui). Both services are based on Docker images with NVIDIA support.

## Prerequisites
- Docker version 20.10.7 or higher.
- Docker Compose version 1.29.2 or higher.
- NVIDIA drivers installed for Docker (if necessary).
- NVIDIA Container Toolkit installed and configured.

## Configuration

### Ollama
The Ollama service uses the `ollama/ollama` image and is exposed on port 11434.

### Open WebUI
The Open WebUI service uses the `ghcr.io/open-webui/open-webui:cuda` image and is exposed on port 3000 (mapped internally to port 8080 in the container).

## Docker Commands

### Start Services
To start the services, run the following command in the directory containing the `docker-compose.yml` file:
```bash
docker compose up -d
```

### Stop Services
To stop the services, run the following command:
```bash
docker compose down
```

### View Logs
You can view the logs of the containers with the following commands:
```bash
docker logs ollama
docker logs open-webui
```

## Directory Structure

- `ollama/`: Local directory for Ollama configuration and data.
- `open-webui/`: Local directory for Open WebUI configuration and data.

## References
- [NVIDIA Container Toolkit Installation Guide](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html)
- [Docker Official Website](https://docs.docker.com/get-docker/)
