# How to launch a Wordpress Server with ssl certificate using docker-compose and Redis

## Prerequisites

- Docker
- point domain to the server

## Install Docker

Before running the instructions below make sure to check the official [Docker installation guide](https://docs.docker.com/engine/install/ubuntu/) for the latest instructions they may have changed in the meantime.

> As of 20-05-2025 this is the script to install docker on Ubuntu 20.04 - 24.04

1- update the `apt` repository.

```bash
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

2- Install docker engine latest

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

## Setup the server

1- Create a directory for the project

2- Clone this repository there

3- Create a `.env` file by copying the `.env.example` and change the values to your needs

4- Launch the container

```bash
docker compose up -d
```

> Note this is necessary to play with redis : W3 Total Cache to take advantage of Redis Cache
