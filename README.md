# docker-setup-ubuntu

# 1. Update your system

    sudo apt update
    sudo apt upgrade -y
    
# 2. Uninstall old versions of Docker (if any)

    sudo apt install -y apt-transport-https ca-certificates curl software-properties-common


# 3. Install prerequisites

    sudo apt install -y apt-transport-https ca-certificates curl software-properties-common

# 4. Add Docker’s official GPG key
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# 5. Add the Docker repository
    echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    

# 6. Install Docker Engine
    sudo apt update
    sudo apt install -y docker-ce docker-ce-cli containerd.io

# 7 sudo docker --version
    sudo docker --version

# Verify by running:
    docker run hello-world

<h1 class="text-center">To install Docker Desktop on Ubuntu, follow these steps:</h1>

# 1. Install Prerequisites
    sudo apt update
    sudo apt upgrade -y
    sudo apt install -y curl wget apt-transport-https software-properties-common ca-certificates

# 2. Alternatively, visit the Docker Desktop for Linux page to get the latest version link.







