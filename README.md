# Docker Development Infrastructure

A reusable Docker-based development environment designed to support multiple full-stack projects while maintaining isolated application runtimes and centralized infrastructure services.

## Problem

While working on multiple projects simultaneously, I frequently encountered dependency conflicts caused by different Node.js versions and project requirements. Some projects required different runtime environments, while others depended on PostgreSQL and Redis services running locally.

Managing these dependencies directly on the host machine resulted in:

* Frequent Node.js version switching
* Environment inconsistencies between projects
* Local installation and maintenance of PostgreSQL and Redis
* Increased onboarding and setup time
* Configuration conflicts across projects

## Solution

To address these challenges, I designed a containerized development infrastructure using Docker and Docker Compose.

The solution provides:

* Isolated runtime environments for each project
* Shared PostgreSQL and Redis services
* Persistent data storage using Docker volumes
* Centralized Docker networking
* Consistent development environments across projects
* Minimal host machine dependencies

## Architecture

```text
Shared Docker Network
│
├── PostgreSQL Container
│     └── Named Volume
│
├── Redis Container
│     └── Named Volume
│
├── Project A Container
│
├── Project B Container
│
└── Project C Container
```

All application containers join the same Docker network and communicate with infrastructure services through Docker's built-in DNS resolution.

Example:

```env
DB_HOST=postgres
REDIS_HOST=redis
```

No manual IP configuration is required.

## Features

* Docker Compose based infrastructure management
* Shared PostgreSQL database service
* Shared Redis cache service
* Persistent named volumes
* Centralized Docker network
* Container-to-container communication
* Isolated project dependencies
* Support for multiple Node.js versions across projects
* Portable and reproducible development environments

## Technologies

* Docker
* Docker Compose
* PostgreSQL
* Redis
* Node.js
* Angular
* NestJS
* .NET

## Benefits Achieved

* Eliminated local installation of Node.js, PostgreSQL, and Redis
* Reduced environment setup time significantly
* Enabled simultaneous development across multiple projects with different runtime requirements
* Simplified infrastructure management through Docker Compose
* Improved development environment consistency and portability

## Getting Started

Clone the repository:

```bash
git clone https://github.com/your-username/docker-development-infrastructure.git
```

Start infrastructure services:

```bash
docker compose up -d
```

Verify running containers:

```bash
docker ps
```

Connect your applications to the shared Docker network and use service names for database and cache communication.

## Learning Outcomes

This project helped me gain practical experience with:

* Docker networking
* Docker Compose
* Service discovery
* Persistent storage using volumes
* Multi-container architectures
* Environment standardization
* Infrastructure automation
* Development workflow optimization

```
```
