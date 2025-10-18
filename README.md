<!-- # ansible-devops-foundation -->

# 🚀 Ansible DevOps Server Setup
<div align="center">

<!-- ![ansible](https://img.shields.io/badge/Ansible-2.9+-green.svg) -->
<!-- ![Linux](https://img.shields.io/badge/Platform-Linux-blue.svg) -->
[![ansible](https://img.shields.io/badge/ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white)](https://www.ansible.com/)
[![Debian](https://img.shields.io/badge/debian-red?style=for-the-badge&logo=debian&logoColor=orange&color=darkred)](https://www.debian.org/)
[![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)](https://ubuntu.com/)
[![MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

Ansible project for rapid and automated DevOps server provisioning.
</div>

<b>🎯 Project Overview</b>

This project is a collection of Ansible Playbooks for automated and standardized Linux server setup in DevOps environments. Using this project, you can prepare your servers for service in minimal time.

- Prepating-Server: Doing update and upgrade from apt Package Manager
- Docker: Installing Docker and its utilities from apt Package Manager - Add user to Docker user group - Start and enable Docker service
- Adding Soon ...


<b>🚀 Quick Start</b> </br>

1. Clone the Repository
```bash
git clone https://github.com/jonah-mod/ansible-devops-foundation.git
cd ansible-devops-foundation
```

2. Configure Servers
```bash
# Copy configuration file
cp vars/server_vars.example.yaml vars/server_vars.yaml

# Edit settings
nano vars/server_vars.yaml
```

3. Run Playbooks
```bash
# Run all playbooks
ansible-playbook -i inventory/host.yaml -e @vars/server_vars.yaml playbook/*

# Or run individually
ansible-playbook -i inventory/host.yaml -e @vars/server_vars.yaml playbook/docker.yml
```

<b>📁 Project Structure</b>
```text
ansible-devops-foundation/
├── inventory/
│   └── host.yaml                 # Inventory file
├── playbook/
│   ├── hardening.yml            # Security hardening
│   ├── docker.yml               # Docker installation
│   └── monitoring.yml           # Monitoring setup
├── vars/
│   ├── server_vars.yaml         # Main variables
│   └── server_vars.example.yaml # Example variables
├── roles/                       # Ansible roles
├── templates/                   # Template files
├── files/                       # Static files
└── README.md
```
<b>🎮 Usage</b></br>
- Full Setup:
```bash
ansible-playbook -i inventory/host.yaml -e @vars/server_vars.yaml playbook/*
```
- Step-by-Step Execution:
```bash

# 1. Docker Installation
ansible-playbook -i inventory/host.yaml -e @vars/server_vars.yaml playbook/docker.yaml

# 2. Security Hardening
ansible-playbook -i inventory/host.yaml -e @vars/server_vars.yaml playbook/preparing.yaml

# 3. Security Hardening (in-progress)
ansible-playbook -i inventory/host.yaml -e @vars/server_vars.yaml playbook/hardening.yaml

# 4. Monitoring Setup (in-progress)
ansible-playbook -i inventory/host.yaml -e @vars/server_vars.yaml playbook/monitoring.yaml
```

<b>👥 Credit</b></br>

- [geerlingguy](https://github.com/geerlingguy): [nginx](https://github.com/geerlingguy/ansible-role-nginx), [php](https://github.com/geerlingguy/ansible-role-php)
- [Dev-Sec](https://github.com/dev-sec): [OS-Hardening](https://github.com/dev-sec/ansible-collection-hardening), [SSH-Hardening](https://github.com/dev-sec/ansible-ssh-hardening), [Nginx-Hardening](https://github.com/dev-sec/ansible-nginx-hardening)