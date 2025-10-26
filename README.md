# Streamix – Discovery Service

![Build](https://img.shields.io/github/actions/workflow/status/mzilin/streamix-infra-discovery/build.yml?label=Build&logo=github&logoColor=white&style=flat)
![Status](https://img.shields.io/badge/status-complete-brightgreen?label=Status)


This repository contains the **Discovery** microservice for the **Streamix** (Video Streaming Platform), deployed in the **Infrastructure** cluster. It acts as the service registry, enabling other microservices to dynamically discover and communicate with each other.

For a complete system overview and links to all microservices, please refer to the [Microservices Hub Repository](https://github.com/mzilin/streamix-microservices-hub).


## Table of Contents

* [Introduction](#introduction)
* [Technology Stack](#technology-stack)
* [Dependencies](#dependencies)
* [Setting Up Your Environment](#setting-up-your-environment)
  * [Prerequisites](#prerequisites)
  * [Installation & Running](#installation--running)
  * [Running with Docker](#running-with-docker)
  * [Environment Variables](#environment-variables)
* [CI/CD & Deployment](#cicd--deployment)
* [License](#license)
* [Contact](#contact)


## Introduction

The **Discovery Service** is a core component of the **Video Streaming Platform**. It centralises the registration and discovery of all microservices, enabling dynamic scaling and resilient communication within the platform. It handles key responsibilities like:

- **Service Registration**: Allows microservices to dynamically register themselves with the Eureka Server at runtime, ensuring discoverability.
- **Service Discovery**: Enables each microservice to locate other services through the Eureka registry, facilitating seamless inter-service communication.
- **High Availability**: Supports replication and failover mechanisms to maintain platform resilience and uptime.


## Technology Stack

This service is built using a modern, cloud-native Java stack, optimised for reactive, scalable microservices:

- **Java** `21`: LTS version with enhanced performance and modern language features.
- **Spring Boot** `3.4.5`: Rapid development framework for standalone, production-ready Java apps.
- **Spring Cloud** `2024.0.0`: Provides essential microservice components like config management, service discovery and API routing.
- **Gradle** `8.14`: Powerful build tool with fast incremental builds and powerful dependency management.
- **Docker**: Containerises apps for consistent, portable development and deployment.


## Dependencies

- **Spring Boot**
  - **Actuator**: Exposes app health, metrics, and monitoring endpoints.

- **Spring Cloud**
  - **Netflix Eureka Server**: Enables service registration and discovery for dynamic scaling and resilience.

- **Developer Experience**
  - **DevTools**: Enables hot reloading for faster development iterations.


## Setting Up Your Environment

Follow the steps below to set up your local development environment and run the application.


### Prerequisites

Ensure you have the following installed on your machine:
- [Java JDK 21](https://www.oracle.com/uk/java/technologies/downloads/#java21)
- [Gradle 8.14](https://gradle.org/)
- [Docker](https://docs.docker.com/get-started/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/)


### Installation & Running

1. Clone the repository:
    ```bash
    git clone https://github.com/mzilin/streamix-infra-discovery.git
    ```

2. Switch to the `main` branch:
    ```bash
    cd streamix-infra-discovery
    ```

3. Build the project and run tests:
    ```bash
    ./gradlew clean build
    ```

4. Start the service:
    ```bash
    ./gradlew bootRun
    ```

   The service will start on http://localhost:8761 using the embedded Tomcat web server.


### Running with Docker

1. Build the Docker image:
    ```bash
   docker build -t streamix-infra-discovery:latest .
    ```
3. Run the container:
    ```bash
   docker run --rm --name streamix_discovery -p 8761:8761 streamix-infra-discovery:latest
    ```


### Environment Variables

This microservice requires the following environment variable to be configured:

- **CONFIG_SERVER_URL**: Specifies the URL of the Spring Cloud Config Server. This allows the service to retrieve its configuration dynamically at runtime.


## CI/CD & Deployment

This project uses **GitHub Actions** to automate the build, test and deployment processes, ensuring continuous integration and delivery.

- The **Build** workflow runs on every push and pull request to the `main` and `prod` branches. This step verifies that all commits compile successfully and pass unit tests before they are merged, maintaining code quality.
- Finally, a **Deploy** workflow is triggered when a pull request is merged into the `prod` branch. It builds a Docker image of the microservice, pushes it to the **AWS ECR** container registry and deploys it to the **AWS ECS** environment.

Branch protections and **GitHub Secrets** are used to manage credentials and safeguard the CI/CD pipelines.


## License

This project is private and proprietary. Unauthorised copying, modification, distribution or use of this software, via any medium, is strictly prohibited without explicit written permission from the owner.


## Contact

For any questions or clarifications about the project, please [reach out](https://www.mariuszilinskas.com/contact) to the project owner.


------
###### © 2024–present Marius Zilinskas. All rights reserved.