# Video Streaming Platform - Eureka Server


## Introduction

The `Eureka Server` is a crucial component of the `Video Streaming Platform`, responsible for the registration and discovery of all microservices. This server facilitates the dynamic scaling and management of services, essential for maintaining high availability and resilience within the platform.


## Technologies Used

The project utilises a suite of modern technologies to ensure robust and scalable service discovery:

- **Spring Boot** `3.2.5`:
    - **Actuator**: Monitors and manages the app.

- **Spring Cloud** `2023.0.1`:
    - **Config**: Manages externalised configuration.
    - **Netflix Eureka Server**: Service registry for microservices.

- **Java** `JDK 17`: Essential for secure, portable, high-performance software development.


### Dependency Management

- **Gradle**: Automates build, test, and deployment processes.


### Containerization

- **Docker** (Optional): Automates OS-level virtualization on Windows and Linux.


## Requirements

To successfully set up and run the server, ensure you have the following installed:

- [Java JDK 17](https://www.oracle.com/uk/java/technologies/downloads/#java17)
- [Gradle](https://gradle.org/)
- [Docker](https://docs.docker.com/get-docker/) (optional)


## Installation

Follow these steps to get the Eureka Server up and running:

1. Navigate into the app's directory
```shell
cd vsp-eureka-server
```

2. Clean and build the server

```shell
./gradlew clean build
```

3. Start the server

```shell
./gradlew bootRun
```


## License

This project is private and proprietary. Unauthorised copying, modification, distribution, or use of this software, via any medium, is strictly prohibited without explicit permission from the owner.


## Contact

For any questions or clarifications about the project, please reach out to the project owner via [www.mariuszilinskas.com](https://www.mariuszilinskas.com).

Marius Zilinskas

------

###### All rights are reserved. - Marius Zilinskas, 2024 to present