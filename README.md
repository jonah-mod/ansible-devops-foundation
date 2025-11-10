<!-- # ansible-devops-foundation -->
[![Farsi](https://img.shields.io/badge/Language-Fa-brown.svg?style=flat-square)](https://github.com/younesmod/ansible-devops-foundation/blob/main/README.fa.md)
[![MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://github.com/younesmod/ansible-devops-foundation/blob/main/LICENSE)
[![Ansible](https://img.shields.io/badge/Powered%20By-Ansible-EE0000?style=flat-square)](https://www.ansible.com/)
# 🚀 Ansible DevOps Server Setup
<div align="center">

<!-- ![ansible](https://img.shields.io/badge/Ansible-2.9+-green.svg) -->
<!-- ![Linux](https://img.shields.io/badge/Platform-Linux-blue.svg) -->
<!-- [![ansible](https://img.shields.io/badge/ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white)](https://www.ansible.com/) -->
[![Debian](https://img.shields.io/badge/debian-A81D33?style=for-the-badge&logo=debian&logoColor=white)](https://www.debian.org/)
[![Arch-Linux](https://img.shields.io/badge/Arch%20Linux-1793D1?style=for-the-badge&logo=arch-linux&logoColor=fff)](https://archlinux.org)
[![FreeBSD](https://img.shields.io/badge/FreeBSD-AB2B28?style=for-the-badge&logo=freebsd&logoColor=white)](https://www.freebsd.org/)
[![OpenBSD](https://img.shields.io/badge/OpenBSD-F2CA30?style=for-the-badge&logo=openbsd&logoColor=black)](https://www.openbsd.org/)
[![RedHat](https://img.shields.io/badge/RedHat-EE0000?style=for-the-badge&logo=redhat&logoColor=white)](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux)
[![CentOS](https://img.shields.io/badge/CentOS-262577?style=for-the-badge&logo=centos&logoColor=white)](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux)
[![Suse](https://img.shields.io/badge/Suse-0C322C?style=for-the-badge&logo=suse&logoColor=white)](https://www.suse.com/)
[![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)](https://ubuntu.com/)

Ansible project for rapid and automated DevOps server provisioning.
</div>

## <b>Table Of Content</b>
- [Project Overview](#-project-overview)
- [Quick Start](#-quick-start)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [Notes](#-notes)
- [Sources](#-sources)

### <b>🎯 Project Overview</b>

This project is a collection of Ansible Playbooks for automated and standardized Linux server setup in DevOps environments. Using this project, you can prepare your servers for service in minimal time.

- Prepating-Server: Doing update and upgrade from apt Package Manager
- Docker: Installing Docker and its utilities from apt Package Manager - Add user to Docker user group - Start and enable Docker service
- Adding Soon ...


### <b>🚀 Quick Start</b>

1. Clone the Repository
```bash
git clone https://github.com/younesmod/ansible-devops-foundation.git
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

### <b>🎮 Usage</b>
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

# 3. Security Hardening
ansible-playbook -i inventory/host.yaml -e @vars/server_vars.yaml playbook/hardening.yaml

# 4. Monitoring Setup (in-progress)
ansible-playbook -i inventory/host.yaml -e @vars/server_vars.yaml playbook/monitoring.yaml
```

### <b>📁 Project Structure</b>
```text
ansible-devops-foundation/
├── inventory/
│   └── host.yaml                # Inventory file
├── playbook/
│   ├── preparing.yaml           # Preparing setup
│   ├── hardening.yaml           # Security hardening
│   ├── harden-ssh.yaml          # SSH hardening
│   ├── harden-os.yaml           # OS hardening
│   ├── docker.yaml              # Docker installation
│   ├── nginx.yaml               # Nginx setup + Nginx Hardening 
│   ├── nginx-hardening.yaml     # Nginx Hardening
│   ├── nginx-setup.yaml         # Nginx setup
│   ├── php-setup.yaml           # Php setup
│   └── setup-node.yaml          # Preparing + Docker
├── vars/
│   └── server_vars.yaml         # Main variables
├── roles/                       # Ansible roles
│   ├── docker/                  # Docker role
│   │   └── ...
│   ├── preparing-server/        # Preparing role
│   │   └── ...
│   ├── nginx/                   # Nginx role
│   │   └── ...
│   ├── php/                     # Php role
│   │   └── ...
│   ├── os-hardening/            # OS-Hardening role
│   │   └── ...
│   ├── ssh-hardening/           # SSH-Hardening role
│   │   └── ...
│   └── nginx-hardening/         # Nginx-Hardening role
│       └── ...
├── .gitignore
├── ansible.cfg                  # Ansible config
├── LICENSE                      # License file
├── README.fa.md
└── README.md
```
### <b>📝 Notes</b>

- Preparing-Server
    - FreeBSD and OpenBSD needs python on target OS.
    - Arch Linux may need some extra tweaks.
    - For SUSE needs to activate some of repositories.
    - Packages are optimized for each distros.
- Docker
    - OpenBSD DOESN'T support docker natively.
    - FreeBSD does support docker but there are some limitations.
    - RedHat/CentOS 8+ uses `dnf` package manager instead of `yum`.
    - It's better to use official repository for production areas.
    - ‌Be sure that the `$user` is existed on OS.

### <b>👥 Sources</b>

- [geerlingguy](https://github.com/geerlingguy): [Nginx](https://github.com/geerlingguy/ansible-role-nginx), [Php](https://github.com/geerlingguy/ansible-role-php)
- [Dev-Sec](https://github.com/dev-sec): [OS-Hardening](https://github.com/dev-sec/ansible-collection-hardening), [SSH-Hardening](https://github.com/dev-sec/ansible-ssh-hardening), [Nginx-Hardening](https://github.com/dev-sec/ansible-nginx-hardening)
