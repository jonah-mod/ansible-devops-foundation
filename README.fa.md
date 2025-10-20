<!-- # ansible-devops-foundation -->
[![MIT](https://img.shields.io/badge/Language-En-skyblue.svg?style=flat-square)](https://github.com/jonah-mod/ansible-devops-foundation/blob/main/README.md)
[![MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://github.com/jonah-mod/ansible-devops-foundation/blob/main/LICENSE)
# 🚀 راه‌اندازی سرور DevOps با Ansible
<div align="center">

[![ansible](https://img.shields.io/badge/ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white)](https://www.ansible.com/)
[![Debian](https://img.shields.io/badge/debian-A81D33?style=for-the-badge&logo=debian&logoColor=white)](https://www.debian.org/)
[![Arch-Linux](https://img.shields.io/badge/Arch%20Linux-1793D1?style=for-the-badge&logo=arch-linux&logoColor=fff)](https://archlinux.org)
[![FreeBSD](https://img.shields.io/badge/FreeBSD-AB2B28?style=for-the-badge&logo=freebsd&logoColor=white)](https://www.freebsd.org/)
[![OpenBSD](https://img.shields.io/badge/OpenBSD-F2CA30?style=for-the-badge&logo=openbsd&logoColor=black)](https://www.openbsd.org/)
[![RedHat](https://img.shields.io/badge/RedHat-EE0000?style=for-the-badge&logo=redhat&logoColor=white)](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux)
[![Suse](https://img.shields.io/badge/Suse-0C322C?style=for-the-badge&logo=suse&logoColor=white)](https://www.suse.com/)
[![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)](https://ubuntu.com/)


پروژه Ansible برای راه‌اندازی سریع و خودکار سرور DevOps.
</div>

<b>🎯 معرفی پروژه</b>

این پروژه مجموعه‌ای از Playbookهای Ansible برای راه‌اندازی استاندارد و خودکار سرورهای لینوکس در محیط‌های DevOps می‌باشد. با استفاده از این پروژه می‌توانید سرورهای خود را در کمترین زمان برای سرویس‌دهی آماده کنید.

#### Preparing-Server:
انجام بروزرسانی و ارتقا از طریق Apt Package Manager
#### Docker:
 نصب Docker و ابزارهای مرتبط از طریق Apt Package Manager - اضافه کردن کاربر به گروه Docker - راه‌اندازی و فعال‌سازی سرویس Docker
#### به زودی اضافه می‌شود ...

<b>🚀 شروع سریع</b> </br>

#### 1. کلون کردن مخزن
```bash
git clone https://github.com/jonah-mod/ansible-devops-foundation.git
cd ansible-devops-foundation
```

#### 2. پیکربندی سرورها
```bash
# Copy configuration file
cp vars/server_vars.example.yaml vars/server_vars.yaml

# Edit settings
nano vars/server_vars.yaml
```

#### 3. اجرای Playbook
```bash
# Run all playbooks
ansible-playbook -i inventory/host.yaml -e @vars/server_vars.yaml playbook/*

# Or run individually
ansible-playbook -i inventory/host.yaml -e @vars/server_vars.yaml playbook/docker.yml
```

<b>📁 ساختار پروژه</b>
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
<b>🎮 نحوه استفاده</b></br>
#### - راه‌اندازی کامل:
```bash
ansible-playbook -i inventory/host.yaml -e @vars/server_vars.yaml playbook/*
```
#### - اجرای مرحله به مرحله:
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

<b>👥 منابع</b></br>

- [geerlingguy](https://github.com/geerlingguy): [Nginx](https://github.com/geerlingguy/ansible-role-nginx), [Php](https://github.com/geerlingguy/ansible-role-php)
- [Dev-Sec](https://github.com/dev-sec): [OS-Hardening](https://github.com/dev-sec/ansible-collection-hardening), [SSH-Hardening](https://github.com/dev-sec/ansible-ssh-hardening), [Nginx-Hardening](https://github.com/dev-sec/ansible-nginx-hardening)