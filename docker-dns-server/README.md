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

## 🔧 Step 2: Build the Docker Image

### 📂 Create a Directory for the Dockerfile  

Next, create a directory for your **Dockerfile**:  

```sh
mkdir -p /dockerfile/centos9-dns
cd /dockerfile/centos9-dns
nano Dockerfile

### 🔹 Create `named.conf` (BIND Configuration)  

Now, create the **BIND configuration file**:  

```sh
nano named.conf
### 📂 Create a Zone File  

### 🔹 Create the Forward Zone File (`doly.vn.zone`)  
To configure **DNS forwarding**, create a `zones/` directory and define the forward zone file:  

```sh
mkdir -p zones/
nano zones/doly.vn.zone

### 🔹 Create the Reverse Zone File (`2.168.192.in-addr.arpa.zone`)  

To configure **DNS reverse**, create a `zones/` directory and define the forward zone file:  

```sh
nano zones/2.168.192.in-addr.arpa.zone

### Build the Docker Image
To build the **Docker image**, run the following command:

```sh
docker build -t centos9-dns .

## ▶️ Step 3: Run the DNS Container
To start the **DNS container** with a **static IP**, run:

```sh
docker run -it --network my-dns-network --ip 192.168.2.11 --dns=192.168.2.11 centos9-dns