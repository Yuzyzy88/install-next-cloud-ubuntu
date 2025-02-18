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

### 4. Update server hostname

   [source](https://www.cherryservers.com/blog/install-nextcloud-docker)
   
   Next, update the server hostname to match your Nextcloud domain. If you have a domain pointing to your  server, this step is important for better server management and accessibility. You can skip this if you 
plan to use the server's IP for access.

### 5. Clone the Nextcloud AIO GitHub Repository

    git clone https://github.com/nextcloud/all-in-one.git
    cd all-in-one


Then copy the **sample.conf** to default environment file, e.g. ```cp sample.conf .env```, open the new conf file, e.g. with ```vim .env```, edit all values that are marked with **# TODO!**, close and save the file.

    cd all-in-one/manual-install
    cp sample.conf .env
    vim .env

Now copy the provided yaml file to a compose.yaml file by running:

    cp latest.yml compose.yaml

### 5. Now you should be ready to go with 

    sudo docker compose up
    
