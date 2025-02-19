# Install Nextcloud All-in-One using Docker

### 1. Update and Upgrade the System
   
   ```
   apt update && apt upgrade -y
   ```

### 2. Install Docker
   
   [Install Docker](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)

### 3. install Docker Compose

   You may need to download the latest version of Docker Compose from the official GitHub repository
   Once the binary is downloaded, you need to give it executable permissions

   ```
   curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)"    -o /usr/local/bin/docker-compose
   chmod +x /usr/local/bin/docker-compose
   ```

   Check if Docker Compose and Docker was installed successfully by running

   ```
   systemctl is-active docker
   docker-compose --version
   apt update && apt upgrade -y
   ```


### 4. Git clone
   ```
   git clone https://github.com/nextcloud/all-in-one.git
   cd all-in-one
   ```

### 5.  Edit ```vim /etc/docker/daemon.json```

   ```
   {
  "default-network-opts": {"bridge":{"com.docker.network.enable_ipv6":"true"}}
   }
   ```

### 6. Restart Docker

   ```
   sudo systemctl restart docker
   sudo docker network create nextcloud-aio
   sudo docker network inspect nextcloud-aio | grep EnableIPv6
   docker compose up
   ```
