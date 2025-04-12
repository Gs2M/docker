# 🐳 Docker Server (CentOS 9)

This repository contains:

- Docker DNS server using **BIND9** on **CentOS 9**.
- Docker Apache server using **Apache** on **CentOS 9**.
- Docker Ununtu 22.04

## 📌 Prerequisites

Before you begin, make sure you have the following installed:

- **Docker**: Check with `docker --version`
- **Docker Compose**: Check with `docker compose version`

## 🚀 Setup Steps

### 🌐 Step 1: Create Docker Network

Create a dedicated **Docker network** for DNS and Apache containers:

```bash
docker network create --subnet=192.168.2.0/24 my-dns-network
```
### 📝 Step 2: Update Configurations for Each Container 

Make sure the configurations are correctly set up:
- DNS Container (BIND9)
- Apache Container

### 🚀 Step 3: Run the Containers 

Once the configurations are updated, you can build and start the containers by running the following command from the directory where your `docker-compose.yml` is located:

```bash
docker compose up --build -d
```
## 🧹 Cleanup
```bash
docker compose down
```