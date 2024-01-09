# Multi-Architecture Docker Setup for QNAP NAS

This repository contains Docker configurations for deploying Pi-Hole, Home Assistant, AnythingLLM, and Ollama web UIs on a QNAP NAS supporting multiple architectures including Intel 64, AMD 64, and ARM 64.

## Setup

- Ensure Docker and Docker Swarm are installed on your QNAP NAS.
- Clone this repository to your NAS into the `/NAS816579HomeLab` or `/mnt/HomeLab` directory.

## Modifications

- Dockerfiles are provided for each service with multi-architecture support.
- Modifications for no GPU and no AVX instructions are included for compatibility with Raspberry Pi 4 Model B and AMD CPUs.

## Usage

- Deploy the stack using Docker Swarm with the command `docker stack deploy -c docker-compose.yml my_stack`.
- Access the services at the designated ports.

## Backup Strategy

- Regularly backup your Docker volumes to an external drive or cloud storage.
- Use `docker save` to create images of your containers for backup.

For detailed instructions and configurations, refer to the individual service documentation.