# Install Nextcloud All-in-One using Docker

### 1. Update and Upgrade the System
   
   ```
   apt update && apt upgrade -y
   ```

### 2. Install Docker
   
   [Install Docker](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)

### 3. install Docker Compose
   
   ```
   git clone https://github.com/nextcloud/all-in-one.git
   cd all-in-one
   ```

### 4.  Edit ```vim /etc/docker/daemon.json```

   ```
   {
  "default-network-opts": {"bridge":{"com.docker.network.enable_ipv6":"true"}}
   }
   ```

### 5. Restart Docker

   ```
   sudo systemctl restart docker
   sudo docker network create nextcloud-aio
   sudo docker network inspect nextcloud-aio | grep EnableIPv6
   docker compose up
   ```
