# Docker DNS Server (CentOS 9)

This repository contains a **Docker-based DNS server** using **BIND9** on **CentOS 9**.

## 📌 Prerequisites
- Docker installed (`docker --version` to check)
- A custom Docker network for DNS resolution

---

## 🚀 Step 1: Create Docker Network
Before running the DNS container, create a dedicated **Docker network**:

```sh
docker network create --subnet=192.168.2.0/24 my-dns-network
```

## 🔧 Step 2: Add DNS config file

### 🔹 Update `named.conf` (BIND Configuration) if needed.
### 📂 Update a Zone File  
### 🔹 Updatet the Forward Zone File (`doly.vn.zone`)  
### 🔹 Update the Reverse Zone File (`2.168.192.in-addr.arpa.zone`)  

## ▶️ Step 3: Run the DNS Container
### 🔹 Update `docker-compose.yml` if needed.
To start the **DNS container**, from the same directory where docker-compose.yml is located run:

```sh
docker compose up --build -d
```

