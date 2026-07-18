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
Now you have a Docker container ready to run the Open WebUI. Access the Open WebUI application at http://localhost:3000 in your web browser.

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

---

## 🧠 Local AI Lab

[![Local AI Lab](https://img.shields.io/badge/🧠_Local_AI_Lab-core-6e40c9?style=for-the-badge)](https://github.com/manzolo/local-ai-lab)

This project is the **core** of [manzolo's Local AI Lab](https://github.com/manzolo/local-ai-lab) — a family of self-hosted AI projects (LLM, voice, vision & documents) that share the same conventions.

This stack **owns the shared `local-ai-net` Docker network**: start it first, then attach any sibling project with its `docker-compose.local-ai.yml` override. From inside the network, the Ollama API is always at `http://ollama:11434`.

Explore the whole family: [`topic:local-ai`](https://github.com/search?q=user%3Amanzolo+topic%3Alocal-ai&type=repositories)
