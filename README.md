
# F&B Data Platform

This repository contains the Docker Compose setup to quickly deploy a PostgreSQL database along with pgAdmin for database management.

## Services
### 1. PostgreSQL
- **Image**: `postgres:latest`
- **Host**: `192.168.1.30`
- **Port**: `5432`
- **Environment Variables**:
  - `POSTGRES_DB`: `fnb`
  - `POSTGRES_USER`: `admin`
  - `POSTGRES_PASSWORD`: `password`
- **Volumes**: 
  - `./postgres_data:/var/lib/postgresql/data`

### 2. pgAdmin
- **Image**: `dpage/pgadmin4`
- **Host**: `192.168.1.29`
- **Port**: `8120`
- **Environment Variables**:
  - `PGADMIN_DEFAULT_EMAIL`: `admin@admin.com`
  - `PGADMIN_DEFAULT_PASSWORD`: `admin`
  - `PGADMIN_LISTEN_PORT`: `8120`
- **Volumes**: 
  - `./pgadmin_data:/var/lib/pgadmin`
- **Dependencies**: Depends on the `postgres` service

## Network

Both services are connected to the `fnb` network with the following subnet: `192.168.1.0/24`.

## Getting Started

### Prerequisites
- Docker
- Docker Compose

### Steps to Run
docker-compose up -d

3. Access pgAdmin at [http://localhost:8120](http://localhost:8120) with the email `admin@admin.com` and password `admin`.

## Volumes
- PostgreSQL data is persisted in the `./postgres_data` directory on the host machine.
- pgAdmin data is persisted in the `./pgadmin_data` directory on the host machine.

## Notes
- Ensure the IP addresses `192.168.1.29` and `192.168.1.30` are available on your network.
- Modify the environment variables in the `docker-compose.yml` file as needed for your setup.

## Stopping the Services
docker-compose down


