# Multi-Environment Docker Project

This repository contains Docker images for various development environments, including Python, Node.js, MySQL, NGINX, and Java. Each directory holds a `Dockerfile` that can be used to build and run a container tailored to the respective technology stack.

## Table of Contents

- [Project Overview](#project-overview)
- [Getting Started](#getting-started)
- [Docker Images](#docker-images)
  - [Python Environment](#python-environment)
  - [Node.js Environment](#nodejs-environment)
  - [MySQL Database](#mysql-database)
  - [NGINX Server](#nginx-server)
  - [Java Environment](#java-environment)
- [License](#license)

## Project Overview

This repository is designed to provide ready-to-use Docker environments for popular technologies. Each environment can be built and run in isolation using Docker, allowing for streamlined development and testing across multiple languages and frameworks.

## Getting Started

### Prerequisites

Ensure you have the following installed on your system:

- **Docker**: [Install Docker](https://docs.docker.com/get-docker/)
- **Git**: [Install Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

### Cloning the Repository

To get started, clone the repository to your local machine:

```bash
git clone https://github.com/yourusername/multi-environment-docker.git
cd multi-environment-docker
```

### Building and Running Docker Images

Each environment has its own directory with a corresponding `Dockerfile`. Follow the instructions for each environment below to build and run the containers.

---

## Docker Images

### Python Environment

This image provides a simple Python environment with dependencies installed from `requirements.txt`.

#### Build the Image

Navigate to the `python-app` directory and build the image:

```bash
cd python-app
docker build -t python-app .
```

#### Run the Container

Run the container in detached mode:

```bash
docker run -d --name python-container python-app
```

#### Customization

- Add your Python application and dependencies to the `requirements.txt` file and the source code to the `python-app` directory.
  
---

### Node.js Environment

This image sets up a Node.js environment with dependencies installed from `package.json`.

#### Build the Image

Navigate to the `nodejs-app` directory and build the image:

```bash
cd nodejs-app
docker build -t nodejs-app .
```

#### Run the Container

Run the container in detached mode:

```bash
docker run -d --name nodejs-container nodejs-app
```

#### Customization

- Add your Node.js application and dependencies to the `package.json` file and the source code to the `nodejs-app` directory.
  
---

### MySQL Database

This image sets up a MySQL 8.0 instance with a pre-configured database.

#### Build the Image

Navigate to the `mysql-db` directory and build the image:

```bash
cd mysql-db
docker build -t mysql-db .
```

#### Run the Container

Run the container with a custom root password and port mapping:

```bash
docker run -d --name mysql-container -e MYSQL_ROOT_PASSWORD=my-secret-pw -p 3306:3306 mysql-db
```

#### Customization

- Modify the `MYSQL_DATABASE` environment variable in the `Dockerfile` to change the default database.
- To persist data, map a volume to `/var/lib/mysql`.

---

### NGINX Server

This image sets up an NGINX web server with a custom configuration.

#### Build the Image

Navigate to the `nginx-server` directory and build the image:

```bash
cd nginx-server
docker build -t nginx-server .
```

#### Run the Container

Run the container with port mapping:

```bash
docker run -d --name nginx-container -p 80:80 nginx-server
```

#### Customization

- Add your NGINX configuration in the `nginx-server/default.conf` file.
- To serve static content, copy it to the appropriate directory in the `Dockerfile`.

---

### Java Environment

This image provides a Java environment for running JAR-based applications.

#### Build the Image

Navigate to the `java-app` directory and build the image:

```bash
cd java-app
docker build -t java-app .
```

#### Run the Container

Run the container in detached mode:

```bash
docker run -d --name java-container java-app
```

#### Customization

- Copy your JAR file into the `java-app/target/` directory and modify the `Dockerfile` to point to it.
