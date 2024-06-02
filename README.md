# Docker Compose Web Application

This repository contains a Docker Compose setup for a web application stack consisting of PHP, MySQL, Nginx, PHPMyAdmin, and Redis cache. It provides a local development environment for your web application.

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
  - [Configuration](#configuration)
- [Usage](#usage)
- [Docker Compose Services](#docker-compose-services)
- [Customization](#customization)
- [License](#license)

## Introduction

This project simplifies the setup of a local development environment for your web application using Docker Compose. It includes the following services:

- PHP service with PHP-FPM.
- MySQL database service.
- Nginx web server.
- PHPMyAdmin for database management.
- Redis cache service.

## Prerequisites

Before you begin, ensure you have met the following prerequisites:

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Getting Started

To get started with this project, follow these steps:

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/ahrasel/docker-template.git
   ```

2. Navigate to the project directory and add those files to your project:

   ```bash
   cd your-repo
   ```

3. Create a `.env` file in the project root and set the environment variables:

   ```dotenv
   DOCKER_APP_PORT=8080
   DOCKER_APP_SSL_PORT=443
   DOCKER_DB_PORT=3306
   DOCKER_PHPMYADMIN_PORT=8081
   DOCKER_REDIS_PORT=6379
   ```

   Replace the values with the ports you want to use.

4. Start the Docker Compose services:

   ```bash
   docker-compose up -d
   ```

### Configuration

You can customize the project by updating environment variables in the `.env` file or by modifying the Docker Compose configuration in `docker-compose.yml`. Refer to the [Customization](#customization) section for more details.

## Usage

Once the services are up and running, you can access your web application at `http://localhost:8080` (or the port you specified) in your web browser. PHPMyAdmin is available at `http://localhost:8081`.

## Docker Compose Services

This project defines the following Docker Compose services:

### myapp (PHP Service)

- **Description:** PHP service for your web application.
- **Exposed Ports:** None.
- **Configuration:** Environment variables for PHP settings and user information.

### myapp_db (MySQL Service)

- **Description:** MySQL database service.
- **Exposed Ports:** Port 3306 (customize in `.env`).
- **Configuration:** Environment variables for database credentials and settings.

### myapp_nginx (Nginx Service)

- **Description:** Nginx web server service.
- **Exposed Ports:** Port 80 (HTTP) and 443 (HTTPS) (customize in `.env`).
- **Configuration:** Mounts Nginx configuration files and SSL certificates.

### myapp_phpmyadmin (PHPMyAdmin Service)

- **Description:** PHPMyAdmin service for managing the MySQL database.
- **Exposed Ports:** Port 8081 (customize in `.env`).
- **Configuration:** Environment variables for connecting to the database.

### myapp_redis_cache (Redis Cache Service)

- **Description:** Redis cache service.
- **Exposed Ports:** Port 6379 (customize in `.env`).
- **Configuration:** Sets up Redis with a password and data volume.

## Customization

You can customize the project in the following ways:

- Update environment variables in the `.env` file to change port settings, database credentials, and other configuration options.
- Modify the Docker Compose configuration in `docker-compose.yml` to add or customize services.

## License

This project is licensed under the MIT LICENSE - see the [LICENSE.md](LICENSE.md) file for details.
