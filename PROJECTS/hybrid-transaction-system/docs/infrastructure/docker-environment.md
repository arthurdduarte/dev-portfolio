# Docker Environment

## Overview

The project infrastructure is based on Docker containerization to provide:
- isolated environments,
- reproducible deployments,
- simplified infrastructure management,
- and future deployment portability.

Docker is used as the foundation for:
- database services,
- backend APIs,
- future distributed services,
- and deployment orchestration.

---

# Current Infrastructure

## Active Services

| Service | Purpose |
|---|---|
| SQL Server 2022 | Relational database |

---

# Docker Compose

Infrastructure orchestration is managed through:

```text
infrastructure/docker/docker-compose.yml
```

---

# Current Compose Structure

```yaml
services:

  sqlserver:
    image: mcr.microsoft.com/mssql/server:2022-latest

    container_name: hts-sqlserver

    environment:
      ACCEPT_EULA: "Y"
      MSSQL_SA_PASSWORD: "YourStrong@Passw0rd"

    ports:
      - "1433:1433"

    volumes:
      - sqlserver_data:/var/opt/mssql

volumes:
  sqlserver_data:
```

---

# Infrastructure Objectives

The Docker environment is designed to support:
- backend service integration,
- local development,
- testing environments,
- future CI/CD pipelines,
- and deployment portability.

---

# Future Expansion

Planned future containerized services include:
- Golang REST API,
- gRPC services,
- batch processing workers,
- monitoring tools,
- and distributed processing components.

---

# Development Environment

Current host environment:
- Windows 11
- Docker Desktop
- Linux-based SQL Server container

Future deployment targets:
- Debian Linux
- OrangePi infrastructure
- containerized production simulations