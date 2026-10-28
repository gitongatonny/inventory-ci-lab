# inventory-ci-lab

A student project for practicing CI/CD with Jenkins, Docker, and a Flask inventory API.

## Architecture

Jenkins runs in Docker on macOS, with a separate Docker-in-Docker service for building and running application containers. The pipeline is defined in `Jenkinsfile`.

## Repository structure

- `app/main.py`: Flask inventory API (`/`, `/health`, `/api/items`, `/api/items/<id>`)
- `tests/test_api.py`: pytest tests
- `Dockerfile`: application image using Gunicorn and a non-root user
- `Jenkinsfile`: declarative CI/CD pipeline
- `requirements.txt`: application dependencies
- `requirements-dev.txt`: development and testing dependencies
- `docker-compose.jenkins.yml`: Jenkins and Docker-in-Docker setup
- `jenkins/Dockerfile`: custom Jenkins image with Docker CLI and pipeline plugins

## Prerequisites

- macOS with Docker Desktop
- Git
- Python 3
- A GitHub repository
- Jenkins configured with the suggested plugins and the required Docker Pipeline plugin

## Local verification

Create a Python virtual environment and install the dependencies:

```bash
python3 -m