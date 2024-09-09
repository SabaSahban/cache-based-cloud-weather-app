# Cache-Based Cloud Weather Service

This project implements a cloud-based weather service using Docker and Kubernetes. The system retrieves weather data from external APIs, caches the data using Redis for efficiency, and leverages container orchestration with Docker Compose.

## Features
- **Weather Data Retrieval:** Retrieves temperature data for cities from APIs such as WeatherAPI and Ninjas.
- **Caching with Redis:** Uses Redis to store city temperature data, reducing redundant API requests and improving performance.
- **Container Orchestration:** Managed through Docker Compose for setting up multi-container environments.
- **Kubernetes Integration:** Implements Kubernetes for container management, persistent volumes, and networking, allowing for scalability and high availability.

## System Overview
1. **API for Weather Data Retrieval:**  
   - Retrieves city weather data from external APIs. Stores the temperature in both Celsius and Fahrenheit or the max/min temperatures depending on the API used.
2. **Redis for Caching:**  
   - Stores retrieved weather data for cities, with a cache expiration time of 5 minutes.
3. **Docker Containers:**  
   - Each service is containerized using Docker. The system runs a weather service and a Redis container.
4. **Kubernetes Deployment:**  
   - Utilizes Kubernetes for deploying containers in a scalable way, including features like persistent volumes and networking for container communication.

## Installation

### Prerequisites
- Docker installed on your system ([Get Docker](https://docs.docker.com/get-docker/))
- Kubernetes set up on your system (with `minikube` or another platform)
- Redis and DockerHub accounts

## API Endpoints
- **GET /weather/:city**  
   Retrieves the current weather information for a given city from the cache or API if not cached.
- **GET /cache**  
   Returns the cached weather data.

## Files Included
- **Dockerfile:** Builds the Docker images for the weather service and Redis.
- **docker-compose.yml:** Manages multi-container setups for the service and Redis.
- **Kubernetes Deployment Files:** YAML configuration files for deploying the services on a Kubernetes cluster.
- **Redis Configuration:** Defines how Redis handles cached weather data, including expiration time.
