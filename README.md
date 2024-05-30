
# F&B Data Platform

This repository contains the Docker Compose setup to quickly deploy a PostgreSQL database along with pgAdmin for database management.

### Prerequisites (Assuming Docker and Docker Compose is installed in the system)
- Docker
- Docker Compose


## Services
- Download the docker-compose.yml file to the local folder
- create a postgres folder and copy the file - docker-compose.yml to postgres folder

## Network
- Both services are connected to the `fnb` network with the following subnet: `192.168.1.0/24`.

## Getting Started

###  Steps to Run
-docker-compose up -d
-Access pgAdmin at [http://localhost:8120](http://localhost:8120) with the email `admin@admin.com` and password `admin`.

## Volumes
- PostgreSQL data is persisted in the `./postgres_data` directory on the host machine.
- pgAdmin data is persisted in the `./pgadmin_data` directory on the host machine.

## Notes
- Ensure the IP addresses `192.168.1.29` and `192.168.1.30` are available on your network.
- Modify the environment variables in the `docker-compose.yml` file as needed for your setup.

## Stopping the Services
- docker-compose down


