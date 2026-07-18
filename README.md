# Airpay Ansible Infrastructure

This repository contains the configuration management code using Ansible for deploying and managing the Airpay infrastructure on AWS EC2 instances.

## Directory Structure

- `PORT_REGISTRY.md`: Contains the list of allocated and used ports for all services.
- `inventories/`: Contains environment-specific host definitions and variables (`dev`, `prod`).
- `playbooks/`: Entrypoint playbooks (`setup_dev.yml`, `setup_prod.yml`).
- `roles/`: Ansible roles organized by category (`base`, `databases`, `cache`, `messaging`, `orchestration`, `iam`, `security`, `networking`, `observability`).

## Quick Start

1. Install Ansible (if not already installed).
2. Configure your AWS credentials or ensure your machine has proper IAM roles.
3. Run the playbook for the target environment.

Example (Dev Environment):
```bash
ansible-playbook -i inventories/dev/hosts.ini playbooks/setup_dev.yml
```

Run specific roles using tags:
```bash
ansible-playbook -i inventories/dev/hosts.ini playbooks/setup_dev.yml --tags "redis,rabbitmq"
```
