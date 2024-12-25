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


# 3. Install the Docker Desktop .deb Package

    sudo apt install ./docker-desktop.deb

# 4. Configure Docker Desktop
    systemctl --user start docker-desktop
    systemctl --user enable docker-desktop
    

# 5. Launch Docker Desktop
    docker-desktop

# 6. Verify Installation
    docker version
# 7. Verify Installation
    docker info
# 8. Troubleshooting
If Docker Desktop does not launch, check the logs:

    journalctl --user -u docker-desktop.service

curl -fsSL https://download.docker.com/linux/desktop/debian/dists/bullseye/pool/main/docker-desktop-latest_amd64.deb -o docker-desktop.deb 
curl: (22) The requested URL returned error: 404
curl -fsSL https://desktop.docker.com/linux/main/amd64/docker-desktop.deb -o docker-desktop.deb
curl: (22) The requested URL returned error: 403

# Steps to Resolve
1. Download the Latest Docker Desktop for Linux
   
        curl -fsSL https://download.docker.com/linux/desktop/debian/dists/bullseye/pool/main/docker-desktop-latest_amd64.deb -o docker-desktop.deb 

Troubleshooting Tips:

    sudo apt update
    sudo apt install -y apt-transport-https ca-certificates curl software-properties-common


KVM Virtualization: Docker Desktop requires KVM virtualization support. Verify it's enabled:

    sudo apt install cpu-checker
    kvm-ok

If kvm-ok returns that your system supports KVM, you're good to go. If not, you may need to enable virtualization in your BIOS settings.

 Download is performed unsandboxed as root as file '/home/devops/Downloads/docker-desktop-amd64.deb' couldn't be accessed by user '_apt'. - pkgAcquire::Run (13: Permission denied)

# Solution: Adjust File Permissions
    sudo chown _apt /home/devops/Downloads/docker-desktop-amd64.deb
    sudo chmod 644 /home/devops/Downloads/docker-desktop-amd64.deb
    sudo apt install /home/devops/Downloads/docker-desktop-amd64.deb

# Alternative Solution: Move the File

    sudo mv /home/devops/Downloads/docker-desktop-amd64.deb /tmp/
    sudo apt install /tmp/docker-desktop-amd64.deb
    
# Start Docker Desktop Service
    systemctl --user start docker-desktop
    docker-desktop

Common Issues and Fixes
Error: "KVM virtualization not enabled"

    sudo apt install cpu-checker
    kvm-ok
    
If kvm-ok shows it’s disabled, enable virtualization in your BIOS/UEFI.


# 1 Enable Virtualization in BIOS/UEFI
    *Common keys to access BIOS: F2, F10, F12, Esc, or Del (check your motherboard documentation).
    *Intel VT-x (for Intel processors)

These are typically found under:

    *Advanced Settings
    *CPU Configuration
    *Virtualization

Enable Virtualization:

    *Set Intel VT-x or AMD-V to Enabled.
    *Save and Exit:

