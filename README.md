# Microservices Databases Setup

This repository contains the setup for various database services using Docker, including PostgreSQL, pgAdmin, MongoDB, Mongo Express, and MailDev.

## Services

### 1. PostgreSQL

- **Image**: postgres:16.2
- **Container Name**: postgres
- **Environment Variables**:
  - `POSTGRES_USER: engineer25`
  - `POSTGRES_PASSWORD: thewordistheword`
  - `PGDATA: /var/lib/postgresql/data`
- **Volumes**:
  - `postgres:/var/lib/postgresql/data`
- **Ports**:
  - `5432:5432`
- **Networks**:
  - `microservices-network`
- **Restart Policy**: unless-stopped

### 2. pgAdmin

- **Image**: dpage/pgadmin4
- **Container Name**: test_pgadmin
- **Environment Variables**:
  - `PGADMIN_DEFAULT_EMAIL: pgadmin@pgadmin.org`
  - `PGADMIN_DEFAULT_EMAIL_PASSWORD: admin`
  - `PGADMIN_CONFIG_SERVER_MODE: "False"`
- **Volumes**:
  - `pgadmin:/var/lib/pgadmin`
- **Ports**:
  - `5050:80`
- **Networks**:
  - `microservices-network`
- **Restart Policy**: unless-stopped

### 3. MongoDB

- **Image**: mongo:latest
- **Container Name**: mongo_db
- **Environment Variables**:
  - `MONGO_INITDB_ROOT_USERNAME=root`
  - `MONGO_INITDB_ROOT_PASSWORD=password`
- **Volumes**:
  - `mongo:/data/db`
- **Ports**:
  - `27017:27017`

### 4. Mongo Express

- **Image**: mongo-express
- **Container Name**: mongo_express_ctn
- **Environment Variables**:
  - `ME_CONFIG_MONGODB_ADMINUSERNAME=root`
  - `ME_CONFIG_MONGODB_ADMINPASSWORD=password`
  - `ME_CONFIG_MONGODB_SERVER=mongodb`
- **Ports**:
  - `8081:8081`
- **Restart Policy**: always

### 5. MailDev

- **Image**: maildev/maildev
- **Container Name**: mail_dog
- **Ports**:
  - `1080:1080`
  - `1025:1025`

## Networks

- **microservices-network**:
  - **Driver**: bridge

## Volumes

- **postgres**
- **pgadmin**
- **mongo**

## Running the Services

To run the services, use the following commands:

1. Clone the repository:
   git clone https://github.com/AWSandAzureandFullStackEngineer/engineers-social-medial.git
   cd engineers-social-medial
