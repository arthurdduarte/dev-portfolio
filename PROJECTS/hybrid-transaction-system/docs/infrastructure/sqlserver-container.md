# SQL Server Container

## Overview

This project uses Microsoft SQL Server 2022 running inside a Docker container as the primary relational database environment.

The SQL Server instance is used to support:
- transactional operations,
- relational modeling,
- backend service integration,
- and future legacy batch processing simulations.

---

# Container Information

| Component | Value |
|---|---|
| Database Engine | SQL Server 2022 |
| Image | mcr.microsoft.com/mssql/server:2022-latest |
| Container Name | hts-sqlserver |
| Host Port | 1433 |
| Internal Port | 1433 |
| Operating System | Linux (Ubuntu 22.04 LTS) |

---

# Docker Configuration

The container is orchestrated using Docker Compose.

## Environment Variables

```yaml
ACCEPT_EULA=Y
MSSQL_SA_PASSWORD=YourStrong@Passw0rd
```

---

# Persistent Storage

A Docker volume is used to persist database files:

```yaml
sqlserver_data:/var/opt/mssql
```

This prevents data loss when restarting or recreating containers.

---

# Connection Information

| Property | Value |
|---|---|
| Server | localhost,1433 |
| Authentication | SQL Server Authentication |
| User | sa |
| Password | YourStrong@Passw0rd |

---

# Management Tools

The environment is managed using:

- SQL Server Management Studio (SSMS)

---

# Current Status

## Operational

The SQL Server container is fully operational and validated through:
- direct SQL queries,
- relational joins,
- Northwind database integration,
- and external management connectivity.