# AMW RedHat DevOps 🚀

**Red Hat Linux → Automation → DevOps**

A progressive learning path from Linux system administration fundamentals to advanced DevOps automation. Every project here is built hands-on — real VMs, real commands, real infrastructure.

---

## 📈 The Learning Path

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   Red Hat Linux     →    Automation     →    DevOps
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   RHCSA Skills          Ansible              CI/CD
   System Admin          Playbooks            Containers
   Bash Scripting        Roles                IaC
   Security              Docker               Monitoring
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## 📂 Repositories

### 🟢 [enterprise-linux-basics-Prjct_01](https://github.com/AMW-RedHat-Quest/enterprise-linux-basics-Prjct_01)
**Phase 1: Red Hat Linux — Enterprise Linux Basics**

A hands-on learning environment simulating a small-scale enterprise server setup with 3 Rocky Linux VMs (web, app, db) configured manually and securely. Covers essential RHCSA-aligned skills.

| Milestone | Topics |
|-----------|--------|
| Milestone A | VM provisioning with KVM/QEMU, user/group management, SSH key distribution |
| Milestone C | Automated backups with retention, Prometheus + Node Exporter + Grafana monitoring |

**Tech**: Rocky Linux 9, KVM/QEMU, Bash, systemd, Prometheus, Grafana

---

### 🟡 [linux-automation-infrastructure-Prjct_02](https://github.com/AMW-RedHat-Quest/linux-automation-infrastructure-Prjct_02)
**Phase 2: Automation — Linux Automation Infrastructure**

Ansible-powered multi-tier infrastructure deployment with hardened PostgreSQL, Docker containers, NGINX reverse proxy, and CI/CD integration.

| Component | Tech |
|-----------|------|
| Configuration Management | Ansible, Ansible Vault |
| Containerization | Docker |
| Database | PostgreSQL (hardened) |
| Web Server | NGINX reverse proxy |
| CI/CD | GitHub Actions (lint, idempotency, deploy) |

**Tech**: Ansible, Docker, PostgreSQL, NGINX, GitHub Actions

---

### 🟣 [KVM_Spin_Ups](https://github.com/AMW-RedHat-Quest/KVM_Spin_Ups)
**Utility: KVM Virtualization Scripts**

A collection of scripts for quickly provisioning and managing QEMU/KVM virtual machines. Used as the foundation for all other projects in this organization.

**Tech**: KVM/QEMU, libvirt, virt-install, cloud-init, Bash

---

### 🔵 Phase 3: DevOps (Coming Next)

Projects planned covering:
- Kubernetes / OpenShift
- Terraform / Infrastructure as Code
- Prometheus & Grafana monitoring stacks
- GitOps workflows

---

## 🛠️ Skills Demonstrated

| Category | Technologies |
|----------|-------------|
| **Linux Administration** | RHEL/Rocky Linux, systemd, LVM, SELinux, firewalld, SSH |
| **Virtualization** | KVM/QEMU, libvirt, cloud-init, virt-install |
| **Configuration Management** | Ansible, roles, playbooks, vault |
| **Containers** | Docker, Podman, containerfiles |
| **Web Servers** | NGINX, reverse proxy |
| **Databases** | PostgreSQL, hardening, security |
| **Monitoring** | Prometheus, Node Exporter, Grafana |
| **Scripting** | Bash automation, validation, error handling |
| **CI/CD** | GitHub Actions, linting, idempotency testing |
| **Backup & Recovery** | Automated backups, retention, rsync, tar |

---

## 🎯 Philosophy

**Learn by doing.** No simulated labs, no click-ops. Every project:
- Runs on **real VMs** provisioned with KVM
- Uses **real Linux commands** you'd type in production
- Includes **verification steps** so you know it actually works
- Builds **public evidence** on GitHub for employers to see

---

## 📬 Get In Touch

This organization is a personal learning portfolio. Questions, suggestions, or collaboration? Open an issue or reach out!

---

*Built with Rocky Linux 9, lots of coffee, and the determination to break into Linux administration.*
