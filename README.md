# Spanner Docker

This repo it to set up a secure spanner (or hammer) node.

## Prerequisites

* Ubuntu OS
* Docker and Docker Compose
* ufw

## Setup Node
### Setup Validator
Replace `${CHAIN_SPEC}`, `${BOOT_NODE}` and `${NODE_NAME}` in `docker-compose-validator.yml` file and run

```shell
docker-compose -f docker-compose-validator.yml up -d
```

Config firewall by 

```shell
sudo ufw allow 22/tcp
sudo ufw allow 30333/tcp
sudo ufw enable
```

### Setup WebSocket Node
Replace `${CHAIN_SPEC}`, `${BOOT_NODE}` and `${NODE_NAME}` in `docker-compose-wsnode.yml` file and run

```shell
docker-compose -f docker-compose-wsnode.yml up -d
```

Config firewall by

```shell
sudo ufw allow 22/tcp
sudo ufw allow 30333/tcp
sudo ufw allow 80/tcp
sudo ufw enable
```