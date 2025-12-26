# rg-tools
Various open soruce tools and products we use at RG

## Current stack

1. Docmost - for Wikis/Documentation
2. Excalidraw - for drawings

## How to use this


1. Server Preparation (One-time)
```
sudo apt update && sudo apt upgrade -y

sudo apt install -y \
  ca-certificates \
  curl \
  gnupg \
  lsb-release \
  git \
  ufw
```
2. Install Docker (Official & Safe)
```
curl -fsSL https://get.docker.com | sudo sh
sudo systemctl enable docker
sudo systemctl start docker
sudo usermod -aG docker $USER
newgrp docker
```
3. Create user for running this code
```
sudo adduser rgtools
<!-- Follow prompts (password, name, etc.). -->
sudo usermod -aG docker rgtools
cd /opt
mkdir rgtool
sudo chown -R rgtools:rgtools /opt/rgtool
chmod 750 /opt/rgtool
```
4. Clone the repository
```
su - rgtools
cd /opt/rgtool
git clone https://github.com/Rotten-Grapes-Pvt-Ltd/rg-tools.git
chown -R rgtools:rgtools /opt/rgtool/rg-tools
cd rg-tools
chmod -R 750 /opt/rgtool/rg-tools

```
1. Create Required Local Folders
```
mkdir data && cd data
mkdir -p postgres-data docmost-data backups
```
1. Configure .env (DO THIS CAREFULLY)
Make copy of `.sample.env` and fill out your details
1. First-Time Startup
```
docker compose pull
docker compose up -d
```
