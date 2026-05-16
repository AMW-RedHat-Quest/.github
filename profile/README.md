
# RHCSA/RHCE DevOps Projects Portfolio

A growing collection of hands-on DevOps projects that progressively build skills from basic Linux administration to advanced automation. Each project focuses on different aspects of system administration, infrastructure as code, and DevOps practices.

---

## 📋 Projects Overview

| # | Project | Status | Key Technologies |
|---|---------|--------|------------------|
| 1 | [Enterprise Linux Basics](#project-1-enterprise-linux-basics) | ✅ Complete | KVM/QEMU, Rocky Linux, Prometheus, Grafana, Bash |
| 2 | [Linux Automation Infrastructure](#project-2-linux-automation-infrastructure) | ✅ Complete | Ansible, Docker, PostgreSQL, NGINX, GitHub Actions |

> **More projects coming soon!** Simpler, focused projects are being planned to cover additional DevOps topics in manageable chunks.

---

## Project 1: Enterprise Linux Basics

**Repository:** [`enterprise-linux-basics-Prjct_01`](./enterprise-linux-basics-Prjct_01/)

### Overview
A comprehensive learning environment simulating a small-scale enterprise server environment with three hosts (web, app, db) configured manually and securely. Designed to practice essential Linux system administration skills aligned with RHCSA objectives.

### Architecture
```
┌─────────────────────────────────────────────────────┐
│                    Host Machine                     │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │
│  │  ServOneVM  │  │ ServTwoVM   │  │ ServThreeVM │  │
│  │   (Web)     │  │   (App)     │  │    (DB)     │  │
│  │  Rocky 9.5  │  │  Rocky 9.5  │  │  Rocky 9.5  │  │
│  │  3GB RAM    │  │  3GB RAM    │  │  3GB RAM    │  │
│  │  1 vCPU     │  │  1 vCPU     │  │  1 vCPU     │  │
│  │  30GB Disk  │  │  30GB Disk  │  │  30GB Disk  │  │
│  └─────────────┘  └─────────────┘  └─────────────┘  │
│         KVM/QEMU Virtualization                     │
└─────────────────────────────────────────────────────┘
```

### Completed Milestones

#### ✅ Milestone A - VM Setup and User Management
- **VMs_installation_Script.sh**: Automates creation of 3 Rocky Linux VMs using KVM/QEMU and virt-install
- **Users_Creatiations_Configurations.sh**: Interactive user creation with shell selection, sudo privileges, and SSH key distribution

#### ✅ Milestone C - Backup and Monitoring
- **BackUpScript.sh**: Automated backup solution for `/etc` with compression, logging, and 60-day retention
- **Monitoring Stack**:
  - Prometheus for metrics collection
  - Node Exporter for system metrics
  - Grafana for visualization dashboards
  - Pre-configured systemd services and prometheus.yml

### Technologies
- **OS**: Rocky Linux 9.5 (RHEL derivative)
- **Virtualization**: KVM/QEMU, virt-install
- **Monitoring**: Prometheus, Node Exporter, Grafana
- **Scripting**: Bash automation
- **Backup**: tar, cron

### Quick Start
```bash
# Create VMs
cd "Milestone A"
sudo ./VMs_installation_Script.sh

# Create users
sudo ./Users_Creatiations_Configurations.sh

# Setup monitoring (on each VM)
cd "Milestone C"
# Install and configure Prometheus, Node Exporter, Grafana
```

---

## Project 2: Linux Automation Infrastructure

**Repository:** [`linux-automation-infrastructure-Prjct_02`](./linux-automation-infrastructure-Prjct_02/)

### Overview
Automates multi-tier application deployment using Ansible with Infrastructure as Code principles. Provisions and configures Linux VMs for complete application infrastructure with CI/CD integration through GitHub Actions.

### Architecture
```
┌─────────────────────────────────────────────────────────────┐
│                    Ansible Control Node                     │
│                    (AnsibleOneVM)                           │
│                           │                                 │
│         ┌─────────────────┼─────────────────┐               │
│         │                 │                 │               │
│    ┌────▼────┐      ┌─────▼─────┐      ┌──────▼──────┐      │
│    │  Web    │      │    App    │      │     DB      │      │
│    │ WebServ │      │  AppServ  │      │  DataServ   │      │
│    │  NGINX  │      │   Docker  │      │  PostgreSQL │      │
│    │ Reverse │      │    App    │      │  Hardened   │      │
│    │  Proxy  │      │ Container │      │             │      │
│    └─────────┘      └───────────┘      └─────────────┘      │
└─────────────────────────────────────────────────────────────┘
```

### Completed Components

#### ✅ Infrastructure
- VM provisioning using KVM/libvirt with cloud-init
- Ansible inventory with host groups (`[web]`, `[app]`, `[db]`, `[infra]`)
- Ansible Vault for secrets management

#### ✅ Ansible Playbooks
| Playbook | Purpose |
|----------|---------|
| `site.yml` | Main orchestration playbook |
| `create-vms.yml` | VM creation with virt-install |
| `db_hardening.yml` | PostgreSQL security hardening |
| `docker_setup.yml` | Docker installation & app deployment |

#### ✅ Ansible Roles
- `db_hardening`: PostgreSQL installation and security configuration
- `docker_setup`: Docker installation and containerized application deployment
- `reverse_proxy`: NGINX reverse proxy configuration

#### ✅ CI/CD (GitHub Actions)
- `lint.yml`: Ansible linting on code changes
- `idempotency.yml`: Playbook idempotency testing
- `docker_deploy.yml`: Automated Docker deployment

### Technologies
- **Configuration Management**: Ansible
- **Containerization**: Docker
- **Database**: PostgreSQL (hardened)
- **Web Server**: NGINX
- **CI/CD**: GitHub Actions
- **Secrets**: Ansible Vault

### Quick Start
```bash
# Install required collections
ansible-galaxy collection install community.postgresql community.general

# Run main playbook
ansible-playbook -i inventories/hosts.ini playbooks/site.yml \
  --vault-password-file .vault_pass.txt
```

---

## 🎯 Learning Path Summary

This project collection follows a progressive learning path:

```
Linux Basics → Automation → More Projects Coming Soon
     │              │              │
     ▼              ▼              ▼
  RHCSA Skills   RHCE Skills   Stay Tuned
     │              │
     ├─ VM Mgmt     ├─ Ansible
     ├─ Users       ├─ Playbooks
     ├─ Bash        ├─ Roles
     ├─ Monitoring  ├─ Docker
     └─ Backups     └─ CI/CD
```

---

## 📊 Skills Demonstrated

| Category | Skills |
|----------|--------|
| **Linux Administration** | User management, systemd services, file permissions, SSH, cron |
| **Virtualization** | KVM/QEMU, virt-install, cloud-init |
| **Configuration Management** | Ansible, Ansible Vault, inventory management |
| **Containerization** | Docker, containerized applications |
| **Web Servers** | NGINX configuration, reverse proxy |
| **Databases** | PostgreSQL installation, hardening, security |
| **Monitoring & Logging** | Prometheus, Grafana, Node Exporter |
| **Scripting** | Bash automation, validation, error handling |
| **CI/CD** | GitHub Actions, linting, idempotency testing |
| **Backup & Recovery** | Automated backups, retention policies |

---

## 📁 Repository Structure

```
RHCSA_RHCE_GitHub/
├── README.md                              # This file
├── RHCSA RHCE Project.md                  # Detailed project documentation
├── enterprise-linux-basics-Prjct_01/      # Project 1
│   ├── Milestone A/                       # VM setup & user management
│   └── Milestone C/                       # Backup & monitoring
└── linux-automation-infrastructure-Prjct_02/  # Project 2
    ├── playbooks/                         # Ansible playbooks
    ├── roles/                             # Ansible roles
    ├── inventories/                       # Inventory files
    └── .github/                           # GitHub Actions workflows
```

---

## 🚀 Getting Started

### Prerequisites
- Linux host with KVM/libvirt support
- Required tools:
  ```bash
  # Core tools
  ansible
  python3-pip
  
  # Virtualization
  qemu-kvm
  libvirt
  virt-manager
  
  # Ansible collections
  ansible-galaxy collection install community.general community.postgresql
  ```

### Recommended Order
1. Start with **Project 1** for Linux fundamentals
2. Move to **Project 2** for automation with Ansible
3. More projects coming soon — follow the repo for updates!

---

## 📜 License

All projects are licensed under the MIT License – free to use and modify for learning purposes.

---

## 🤝 Contributing

These projects are primarily practice labs for learning purposes. Feel free to:
- Fork and experiment
- Suggest improvements via issues
- Extend milestones with additional features

---
